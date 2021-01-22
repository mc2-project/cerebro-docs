.. _artifact:

**********************************
Artifact Evaluation Guide
**********************************

Before running the artifact, due to the nature of the frameworks, we will assign each machine with a specific ID. We will 0-index the IDs (the first party is party 0). There is a script ``run_all.sh`` provided in the instances which details every
command. Here we provide brief explanations on how to execute the scripts. The key, called ``artifact_eval.pem`` to access the scripts should have already been provided.

For figure 6 and 7, when benchmarking the offline phase, the rate at which triples/matrices are produced should be outputted onto the terminal at the end of execution. This will later be used to estimate the offline time for various benchmarks using arithmetic circuits.

For the remaining figures, when executing arithmetic circuits, the online time is outputted at the end of execution, while obtaining the offline time is explained in the report. When executing boolean circuits, the total (non-setup) time is displayed at the end of execution.

- Figure 6a: We provide scripts for the data points for 2, 4, 6 parties for both the quadratic and linear protocols in the LAN 
  setting with a throughput of 2Gbit/s, for a total of 6 experiments.
  To run the linear protocol, run ``./artifact_eval_scripts/fig_6a/fig_6a_linear.sh N p`` in which `N` is the number of parties and `p` is the party id (0-indexed).

  To run the linear protocol for two parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_linear.sh 2 0`` for party 0 and 
  run ```./artifact_eval_scripts/fig_6a/fig_6a_linear.sh 2 1`` for party 1.

  For 4 parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_linear.sh 4 0`` for party 0 and similarly for the other parties.

  For 6 parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_linear.sh 6 0`` for party 0 and similarly for the other parties.


  Similarly, for the quadratic protocol for two parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_quadratic.sh 2 0`` for party 0 and run ``./artifact_eval_scripts/fig_6a/fig_6a_quadratic.sh 2 1`` for party 1.

  For 4 parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_quadratic.sh 4 0`` for party 0 and similarly for the other parties.

  For 6 parties, run ``./artifact_eval_scripts/fig_6a/fig_6a_quadratic.sh 6 0`` for party 0 and similarly for the other parties.

- Figure 6b: We provide scripts for the data points for 2, 4, 6 parties for both n=100 and n=10 in the LAN setting with a 
  throughput of 2Gbit/s, for a total of 6 experiments. To run it for n=100, run 
  ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh N p n`` in which N
  is the number of parties and p is the party id and n refers to the value in the graph which dictates the
  number of columns in the vectorized triple.

  For the n=100 data point, for 2 parties, run ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 2 0 100`` for party 0
  and ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 2 1 100`` for party 1.

  For the n=10 data point, for 2 parties, run ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 2 0 10`` for party 0
  and ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 2 1 10`` for party 1.

  For 4 parties and n=10, run ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 4 0 10`` for party 0 and similarly for the other parties.

  For 6 parties and n=10, run ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh 6 0 10`` for party 0 and similarly for the other parties.

- Figure 6d: We provide scripts for the data points for 2, 4, 6 parties for both the quadratic and linear protocols in the WAN 
  setting with a throughput of 100Mbit/s, for a total of 6 experiments.
  To run the linear protocol, run ``./artifact_eval_scripts/fig_6d/fig_6d_linear.sh N p`` in which `N` is the number of parties and `p` is the party id (0-indexed).

  To run the linear protocol for two parties, run ``./artifact_eval_scripts/fig_6d/fig_6d_linear.sh 2 0`` for party 0 and 
  run ```./artifact_eval_scripts/fig_6d/fig_6d_linear.sh 2 1`` for party 1.

  For 4 parties, run ``./artifact_eval_scripts/fig_6d/fig_6d_linear.sh 4 0`` for party 0 and similarly for the other parties.

  For 6 parties, run ``./artifact_eval_scripts/fig_6d/fig_6a_linear.sh 6 0`` for party 0 and similarly for the other parties.


  Similarly, for the quadratic protocol for two parties, run ``./artifact_eval_scripts/fig_6d/fig_6d_quadratic.sh 2 0`` for party 0 and run ``./artifact_eval_scripts/fig_6d/fig_6d_quadratic.sh 2 1`` for party 1.

  For 4 parties, run ``./artifact_eval_scripts/fig_6d/fig_6d_quadratic.sh 4 0`` for party 0 and similarly for the other parties.

  For 6 parties, run ``./artifact_eval_scripts/fig_6d/fig_6d_quadratic.sh 6 0`` for party 0 and similarly for the other parties.

- Figure 6e: We provide scripts for the data points for 2, 4, 6 parties for both n=100 and n=10 in the LAN setting with a 
  throughput of 2Gbit/s, for a total of 6 experiments. To run it for n=100, run 
  ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh N p n`` in which `N` is the number of parties and `p` is the party id 
  (0-indexed) and `n` refers to the value in the graph which dictates the number of columns in the vectorized triple.

  For the n=100 data point, for 2 parties, run ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 2 0 100`` for party 0
  and ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 2 1 100`` for party 1.

  For the n=10 data point, for 2 parties, run ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 2 0 10`` for party 0
  and ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 2 1 10`` for party 1.

  For 4 parties and n=10, run ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 4 0 10`` for party 0 and similarly for the other parties.

  For 6 parties and n=10, run ``./artifact_eval_scripts/fig_6e/fig_6e_quadratic.sh 6 0 10`` for party 0 and similarly for the other parties.


- Figure 7: We provide scripts for the hierarchical network layout and flat layout on 4 parties. 
  
  For the flat scenario, for parties 0, 1, 2, run ``./artifact_eval_scripts/flat_fast.sh p`` where p is the party index (For example: party 0 executes ``./artifact_eval_scripts/flat_fast.sh 0``). For party 3, run 
  ``./artifact_eval_scripts/flat_slow.sh 3``.

  For the hierarchical scenario, for parties 0, 1, 2, run ``./artifact_eval_scripts/two_layer_fast.sh p`` where p is the party index (For example: party 0 executes ``./artifact_eval_scripts/two_layer_fast.sh 0``). For party 3, run 
  ``./artifact_eval_scripts/two_layer_slow.sh 3``.


- Figure 8a: We provide scripts for running decision trees of 2, 4, 6, 8, 10, 12 layers for two parties for both arithmetic 
  and boolean circuits, for a total of 12 experiments. 

  The script format is ``./artifact_eval_scripts/fig_8a/fig_8a_dt_2layer_boolean.sh num_layers p`` where 
  num_layers (2, 4, 6, 8, 10 or 12) is the number of layers in the decision tree and p is the party number.

  For running the boolean circuit of a decision tree with 2 layers, run
  ``./artifact_eval_scripts/fig_8a/fig_8a_dt_2layer_boolean.sh 2 0`` for party 0 and 
  ``./artifact_eval_scripts/fig_8a/fig_8a_dt_2layer_boolean.sh 2 1`` for party 1.

  For running the arithmetic circuit of a decision tree with 2 layers, run
  ``./artifact_eval_scripts/fig_8a_dt_2layer_arithmetic.sh 2 0`` for party 0 and 
  ``./artifact_eval_scripts/fig_8a_dt_2layer_arithmetic.sh 2 1`` for party 1.

  For the other layers, run the corresponding scripts.

  Note that with the arithmetic backend, compiling a 12-layer decision tree takes quite a long time (1-2 hours).


- Figure 8b: We provide scripts for running decision trees of 10 layers for 2, 4, 6 parties for both arithmetic and boolean 
  circuits. 

  The script format is ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_boolean.sh N p`` where N is the number of parties
  and p is the party index.

  For running the boolean circuit of a decision tree with 2 parties, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_boolean.sh 2 0`` for party 0 and
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_boolean.sh 2 1`` for party 1.

  For running the arithmetic circuit of a decision tree with 2 parties, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 2 0`` for party 0 and
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 2 1`` for party 1.

  For 4 parties and boolean circuits, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 4 0`` for party 0 and similarly for the other parties.

  For 4 parties and arithmetic circuits, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 4 0`` for party 0 and similarly for the other parties.

  Similarly, you can run the same script for 6 parties by changing the first argument.

- Figure 8c: We provide scripts to run logistic regression for 6 parties for both arithmetic and boolean circuits in a LAN 
  setting.

  For arithmetic, we run both the semihonest and malicious versions of the protocol. 

  To run the semihonest version, run ``./artifact_eval_scripts/fig_8c/fig_8c_lr_arithmetic_semihonst.sh 0`` for party 0 and
  similarly for the other parties.

  To run the malicious version, run ``./artifact_eval_scripts/fig_8c/fig_8c_lr_arithmetic_malicious.sh 0`` for party 0 and
  similarly for the other parties.

  For boolean, we run both the semihonest and malicious versions of the protocol.

  To run the semihonest version, run ``./artifact_eval_scripts/fig_8c/fig_8c_lr_boolean_semihonest.sh 1`` for party 0 and
  similarly for the other parties. (Note again the parties for the boolean framework are 1-indexed).

  To run the malicious version, run ``./artifact_eval_scripts/fig_8c/fig_8c_lr_boolean_malicious.sh 1`` for party 0 and
  similarly for the other parties. (Note again the parties for the boolean framework are 1-indexed).


- Figure 8d: We run a scaled down version of ADMM with 100 samples per party instead of 10000 as in the paper. We vary the
  number of features from 5 to 20 with and without precomputation.

  For 5 features, to run the optimized version, run ``./artifact_eval_scripts/fig_8d/5_optimized.sh 0`` for party 0 and
  similarly for the other parties.

  For features, to run the unoptimized version, run ``./artifact_eval_scripts/fig_8d/5_unoptimized.sh 1`` for party 0 
  and similarly for the other parties.

  For 10 and 20 features, you can run the other scripts in the folder ``./artifact_eval_scripts/fig_8d/`` with the same
  argument format as above.

  Note that for 20 features, the compilation and offline phase take a significant amount of time for the unoptimized version
  (up to 8-10 hours). Therefore, we turn them off by default, but they can be enabled by running
  ``./artifact_eval_scripts/fig_8d/20_unoptimized.sh p 1`` where p is the party number as stated above. Simply add another
  argument to the end of this script to enable the slow flag.
  We provide the numbers we got for the offline/online time for every experiment here as well in the report.


- Logistic Regression DP Policy: We provide a script to run the DP policy as described in the paper. 

  To run the script, run ``./artifact_eval_scripts/dp_policy/dp_policy.sh 0`` for party 0 and similarly for the other parties.


- Logistic Regression Validation Policy. We provide a script to run the validation policy as described in the paper.

  To run the script for 1000 training samples and 100 test samples, run 
  ``./artifact_eval_scripts/lr_validation/lr_validation_100.sh 0`` for party 0 and similarly for the other parties.

  To run the script for 5000 training samples and 500 test samples, run 
  ``./artifact_eval_scripts/lr_validation/lr_validation_500.sh 0`` for party 0 and similarly for the other parties.

  Run the corresponding script for 15000 training samples and 1500 test samples.


- Auditing generating commitment: We provide a script to run the subset sum commitment scheme used for auditing. The scripts
  generate commitments for 10, 50 and 100 samples.

  For 10 samples, run ``./artifact_eval_scripts/subset_sum/subset_sum_10.sh 0`` for party 0 and similarly for the other parties.

  For 50 and 100 samples, run the corresponding scripts with the same argument format.

  The time reported is merely the online phase. The malicious offline phase for the arithmetic framework is integrated with the
  online phase. To benchmark the offline phase, you can run the script and it will print out the rate at which malicious triples
  are generated in the offline phase.

  Run ``./artifact_eval_scripts/malicious_offline_benchmark/benchmark.sh 0`` for party 0 and similarly for the other parties
  to obtain the amortized number for the offline phase. The terminal will output the number of seconds it takes to generate a
  triple. The script generates around 2,000,000 triples, at which point, we can get a good estimate of the amortized cost of generating offline triples which is also stated in the report.



If anything inconsistent shows up, please do not hesitate to contact us.


