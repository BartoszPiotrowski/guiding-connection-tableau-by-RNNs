This repository contains data for experiments on applying recurrent neural
networks for internal guidance for connection tableau proofs; the experiments
were described in the paper
"Guiding Inferences in Connection Tableau by Recurrent Neural Networks"
submitted to CICM 2020.

- the directory `leancop_proofs` contains 13818 connection tableau proofs of
  Mizar theorems obtained with use of leanCoP
- the file `clauses` contains an enumeration of all clauses appearing in the
  proofs; before enumerating, all the clauses were simplified / made more
  uniform by putting a symbol `VAR` in place of all variables and `SKLM` in
  place of all Skolem symbols; in the training files we use the numbers of
  clauses instead of clauses themselves
- in `training_and_testing_files` there are directories containing training,
  validation and testing data for training the NMT model for the task of
  predicting good subsequent clauses in the proof from a sequence of preceding
  literals or clauses on the current branch in the proof tree. There are 6
  folders and the data in them differ depending on whether the source / input
  sequence consists of `literals` or `clauses`, and how many clauses are to
  predict (1, 2 or 3). Each of the folders contains files:
  - `train.in`, `train.out`
  - `dev.in`, `dev.out`
  - `test.in`, `test.out`
  These are input and output sequences for NMT, split into training, validation
  and testing. Additionally, files `vocab.in`, `vocab.out` contain vocabulary
  of the input and output sequences, which are required for NMT models.
  (Some large training files are compressed.)
