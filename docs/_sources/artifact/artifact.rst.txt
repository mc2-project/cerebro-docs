.. _artifact:

**********************************
Artifact Evaluation Guide
**********************************

Before running the artifact, due to the nature of the frameworks, we will assign each machine with a specific ID. We will 0-index the IDs (the first party is party 0). While the framework we use for arithmetic circuits 0-indexes party ids, the framework for boolean circuits 1-indexes party ids, which explains any potential inconsistencies with executing the scripts.

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
  throughput of 2Gbit/s, for a total of 6 experiments. To run it for n=100, run ``./artifact_eval_scripts/fig_6b/fig_6b_quadratic.sh N p n`` in which `N`
  is the number of parties and `p` is the party id (0-indexed) and `n` refers to the value in the graph which dictates the
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

  For running the boolean circuit of a decision tree with 2 layers, run
  ``./artifact_eval_scripts/fig_8a/fig_8a_dt_2layer_boolean.sh 1`` for party 0 and 
  ``./artifact_eval_scripts/fig_8a/fig_8a_dt_2layer_boolean.sh 2`` for party 1.

  For running the arithmetic circuit of a decision tree with 2 layers, run
  ``./artifact_eval_scripts/fig_8a_dt_2layer_arithmetic.sh 0`` for party 0 and 
  ``./artifact_eval_scripts/fig_8a_dt_2layer_arithmetic.sh 1`` for party 1.

  For the other layers, run the corresponding scripts.


- Figure 8b: We provide scripts for running decision trees of 10 layers for 2, 4, 6 parties for both arithmetic and boolean 
  circuits. 

  For running the boolean circuit of a decision tree with 2 parties, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_boolean.sh 1`` for party 0 and
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_boolean.sh 2`` for party 1.

  For running the arithmetic circuit of a decision tree with 2 parties, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 0`` for party 0 and
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 1`` for party 1.

  For 4 parties and boolean circuits, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 1`` for party 0 and similarly for the other parties.

  For 4 parties and arithmetic circuits, run
  ``./artifact_eval_scripts/fig_8b/fig_8b_dt_2party_arithmetic.sh 0`` for party 0 and similarly for the other parties.

  Run the corresponding script for 6 parties.

- Figure 8c: We provide scripts to run logistic regression for 6 parties for both arithmetic and boolean circuits in a LAN 
  setting.

  For arithmetic, 


- Logistic Regression DP Policy: We provide a script to run the DP policy as described in the paper. 


- Logistic Regression Validation Policy. We provide a script to run the validation policy as described in the paper.


- Auditing generating commitment: We provide a script to run the subset sum commitment scheme used for auditing. The scripts
  generate commitments for 10, 50 and 100 samples.




