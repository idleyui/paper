AUTOSEM: Automatic Task Selection and Mixing in Multi-Task Learning



problems of MTL:

- correct choice of auxiliary tasks
- balanced mixing ratio

old solutions of the problems:

- manual intuitoin
- hyper-parameter tuning over all combinatorial task choices

problems of old solutions:

- introduces human inductive bias
- not scalable when number of candidate auxiliary tasks is considerable

so 👇

AUTOSEM

- stage one: automatic task selection

    use a non-stationary multi-armed bandit controller

- 