*************************
Cerebro Setup
*************************

We provide a Dockerfile that installs all the dependencies required by Cerebro. Running the Dockerfile will build SCALE-MAMBA and EMP-AGMPC. 
	* Create the Dockerfile and requirements.txt.
    	* Dockerfile 
		::

			FROM rdeng2614/cerebro:initial_image
			WORKDIR /root
			RUN git clone https://github.com/mc2-project/cerebro.git
			WORKDIR /root/cerebro
			RUN git submodule update --init --recursive
			WORKDIR /root/cerebro/crypto_backend/emp-toolkit/emp-tool
			RUN git pull origin master && cmake . && make && sudo make install
			WORKDIR /root/cerebro/crypto_backend/emp-toolkit/emp-ot
			RUN cmake . && make && sudo make install
			WORKDIR /root/cerebro/crypto_backend/emp-toolkit/emp-agmpc
			RUN git pull origin master
			RUN cmake . && make
			WORKDIR /root
			RUN apt-get update && apt-get install -y \
				python-gmpy2 \
				python-pip \
				emacs
			COPY requirements.txt /root
			RUN pip install -r requirements.txt

		* requirements.txt
		::

			asn1crypto==0.24.0
			astor==0.8.1
			astunparse==1.6.3
			cryptography==2.1.4
			decorator==4.4.2
			enum34==1.1.6
			gmpy2==2.0.8
			idna==2.6
			ipaddress==1.0.17
			keyring==10.6.0
			keyrings.alt==3.0
			networkx==2.2
			numpy==1.16.6
			ordered-set==3.1.1
			pathlib==1.0.1
			pycrypto==2.6.1
			pygobject==3.26.1
			pyxdg==0.25
			SecretStorage==2.3.1
			six==1.11.0 

	* Place them in the same directory.
	* In that directory, run ``docker build -t name_of_image``.

After creating the image, run it. You should be in ``/root``, the directory Cerebro was installed in. Complete the setup steps for your desired backend.

SCALE-MAMBA
################

Setup Steps for SCALE-MAMBA
*****************************
	* Go to ``cerebro/crypto_backend/SCALE-MAMBA``.
	* Copy ``CONFIG`` into ``CONFIG.mine`` (i.e ``cp CONFIG CONFIG.mine``).
	* Go to ``CONFIG.mine`` and change the entry corresponding with ``ROOT`` to point to the current path of where the SCALE-MAMBA directory is (most likely ``/root/cerebro/crypto_backend/SCALE-MAMBA``). Also, change the entry corresponding with ``OSSL`` to have it point to the installed OpenSSL directory (most likely ``/usr/lib/ssl``)
	* Run ``make progs`` and SCALE-MAMBA should compile.
	* Go to ``cerebro``. Then do ``python Config/gen_cert.py n`` where ``n`` is the number of parties you want to compute with. For the tests (described below) to work, we require ``n`` to be ``2``. 
		* This will generate certificates for the root and the ``n`` parties. The first certificate is the the root's certificate. The following certificates are for the parties. For simplicity, make sure to set the ``Common Name`` of the root as ``RootCA``. Set the ``Common Name`` of the ``i``th party to ``Player(i-1)`` (e.g. ``Player0`` for the first party).
	* Go to ``cerebro/crypto_backend/SCALE-MAMBA`` and run ``./Setup.x``.
  	* First, let's setup ``Certs`` (i.e enter ``1``). 
    	* For the root, enter the name you gave your root (e.g. ``RootCA``). For the number of players, enter ``n`` (e.g. ``2``). Then, for each player, input an IP address (for testing, input ``127.0.0.1``). For the name of certificate, use the common name you gave your parties appended with ``.crt`` (e.g. ``Player0.crt`` and ``Player1.crt``). This should produce ``NetworkData.txt`` under ``Data``.
  	* Next, run ./Setup.x, and setup secret sharing. Choose full threshold. Let it find the prime for LSSS. For the modulus, for simplicity, enter 128. You can choose a different number if you want. The number you can choose is limited by ``MAX_MOD`` in ``CONFIG.mine``; you can't use more than 2 to the ``MAX_MOD`` bits. You can configure ``MAX_MOD`` if you want.
  	* Finally, run .Setup.x, and setup the convversion circuit. 

Testing for SCALE-MAMBA
*************************
	* To run the tests with SCALE-MAMBA, run ``cd mc2/crypto_backend/SCALE-MAMBA`` and then run ``python test_scripts/test_scale_mamba.py``.
	* Troubleshooting
        * Try editing ``test_scripts/test_scale_mamba.py`` such that in ``run_online`` when running ``./Player.x 0 ...`` and ``./Player.x 1 ..``, you add a flag ``-max 5000,5000,5000``. This limits the numbers of triples that can be generated to 5000. 
        * Edit ``Data/NetworkData.txt`` such that the last two lines (which should be zeros) are ones. This uses a fake online phase so it sacrifices security for speed. However, for testing purposes, this is okay.

Resources
**********
	* SCALE-MAMBA repository


EMP-AGMPC
################
			
Setup Steps for EMP-AGMPC
***************************
	* Navigate to ``cerebro/crypto_backend/emp-toolkit/emp-agmpc/emp-agmpc``. Edit the file ``cmpc_config.h``. You can set ``NUM_PARTY_FOR_RUNNING`` to configure the number of parties in your computation. Then, edit ``IP`` such that the ``i``th index holds the IP address of the ``i``th party. For example, ``IP[1]`` holds the IP address for party 1, ``IP[2]`` holds the IP address for party 2, etc. Also, make sure that the 0th index and the last index of ``IP`` contains ``""``. So if ``NUM_PARTY_FOR_RUNNING`` is 3, for example, ``IP[0]`` and ``IP[4]`` hold ``""``.
    	* For the tests, we require ``NUM_PARTY_FOR_RUNNING`` to be 2 and every party's IP address to be ``127.0.0.1``.
	* Run ``cmake . && make``

Testing for EMP-AGMPC
***********************
	* To run the tests with emp-agmpc, run ``cd mc2/crypto_backend/emp-toolkit/emp-agmpc`` and then run ``python test_scripts/test_gc.py``.

Resources
***********
	* emp-agmpc repository
	* emp-tool repository
	* emp-ot repository
