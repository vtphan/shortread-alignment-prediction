This Python script does two things:

(1) compute correlations between aligners' performance and genome complexity.  To do this, users must provide (a) the performance of aligners on a set of genomic sequences and (b) the complexity of the sequnces.
Several measures of genome complexity, including D_k, can be computed using this script: https://github.com/vtphan/sequence-complexity

(2) train and predict aligners' performance based on complexity.  Users must also specify the
fraction of training set (between 0 and 1).  The set of genomic sequences will be used for training
and testing.

## Predict performance of short-read aligners

    usage: cross_validation.py [-h]
                               complexity training_portion dir performance_keys
                               [performance_keys ...]

    Train and predict short-read alignment performance using different complexity
    measures.

    positional arguments:
      complexity        file containing complexity values of genomes
      training_portion  fraction of data used for training
      dir               directory containing text files storing aligner
                        performance
      performance_keys  Prec-100, Rec-100, Prec-75, Rec-75, Prec-50, Rec-50, ...

    optional arguments:
      -h, --help        show this help message and exit


Example 1: compute correlations of aligners to different measures of complexity.
```
    python cross_validation.py complexity.txt 1 perf-samples/ Prec-100 Rec-100
```

Example 2: compute prediction errors of aligners' prediction of alignment accuracy,
based on 50% training 50% testing.
```
    python cross_validation.py complexity.txt 0.5 perf-samples/ Prec-100 Rec-100
```

