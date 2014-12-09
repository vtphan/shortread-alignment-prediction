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


```
    python cross_validation.py complexity.txt 1 perf-samples/ Prec-100 Rec-100
```

Compute prediction errors based on 50% training 50% testing
```
    python cross_validation.py complexity.txt 0.5 perf-samples/ Prec-100 Rec-100
```

To compute different measures of genome complexity, go here: https://github.com/vtphan/sequence-complexity