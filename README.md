# PiNNAcLe: activated learning with PiNN

PiNNAcLe (**PiNN** **Ac**tivated **Le**arning) is a collection of workflows
built for activated learning and sampling of interatomic potentials. The
workflows are implemented in the [nextflow] language to enable their scalable
execution.

[nextflow]: https://nextflow.io

<img src="/docs/figure/schematics.png" alt="pinn_toc" style="height: 180px; width:360px;"/>

## Quick start

By default, PiNNAcLe workflows are executed with containerized environments, so
the only dependencies required are [singularity] and [nextflow]:

[singularity]: https://docs.sylabs.io/guides/latest/user-guide/

``` bash
nextflow run teoroo-cmc/pinnacle -entry h2o-demo
```

PiNNAcLe also collects workflow configurations for known supercomputer centres
that the developers have access. For those resources, profiles are provided that
can be easily used:

``` bash
nextflow run teoroo-cmc/pinnacle -entry h2o-demo -profile dardel
```

See a complete list in the documentation, along with guides to build your own
profile.

## Use your own dataset

The default workflow in PiNNAcLe is called [acle] (activated learning). Each
implemented workflow has its set of parameters that can be set at runtime:

[acle]: docs/recipe/acle.md

```
nextflow run yqshao/pinnacle --proj=testrun --initDs=myDs.{yml,tfr} --initModel=myModel.yml
```

The job history is automatically logged by nextflow, which one can recover by
`nextflow log`. For a better record of setup, you may also chose to use a
parameter file. Available parameters, along with parameter templates are given
for each workflow entry in the [documentation][entries].

[entries]: docs/profiles/overview.md


## Extending the workflow

The workflows in PiNNAcLe are modularized such that extension of the workflow is
possible. If you wish to use PiNNAcLe as a starting point for your own project,
use the copier template:

``` bash
copier gh:teoroo-cmc/pinnacle
```

## See also

- [PiNN]: Interatomic potential supported by PiNNAcLe;
- [tips]: Python/CLI utility for potential sampling.

[PiNN]: https://github.com/Teoroo-CMC/PiNN
[tips]: https://github.com/Teoroo-CMC/tips

## About and reference

PiNNAcLe is developed by [Yunqi Shao][yqshao] at the [TeC group][tec] in Uppsala
University, Sweden.

Shao, Y. and Zhang, C. PiNNAcLe: Adaptive Learn-On-The-Fly Algorithm for Machine-Learning Potential, arXiv preprint arXiv:2409.08886


[yqshao]:https://github.com/yqshao
[tec]:https://tec-group.github.io/
