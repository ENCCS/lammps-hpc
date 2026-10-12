# LAMMPS on HPC

A series of short tutorials for LAMMPS users who want to run molecular dynamics
simulations on EuroHPC systems, with reference notes for GPU software compatibility.

## Before you start

:::{prereq}
- Basic familiarity with Linux shell commands and molecular dynamics.
- Access to an HPC system and an allocation for submitting jobs.
- Familiarity with environment modules and Slurm job submission.
:::

## Short tutorials

Start with installation and compilation, then continue to the MACE workflow.
The examples use specific software versions and cluster environments; adapt
module names, paths, and allocation accounts to your system.

```{toctree}
:caption: Short tutorials
:maxdepth: 1

short-tutorials/s01e01
short-tutorials/s01e02
```

## Reference notes

Use the CUDA reference when choosing a toolkit or Python GPU packages for an
NVIDIA system. It distinguishes driver compatibility from GPU compute capability.

```{toctree}
:caption: Reference notes
:maxdepth: 1

reference/cuda_driver_cuda_cc_mapping
```

## Learning outcomes

After working through these tutorials, you should be able to:

- Inspect the packages available in an installed LAMMPS executable.
- Configure and compile LAMMPS for CPU or GPU execution.
- Prepare the LAMMPS and MACE software environment on Leonardo Booster.
- Submit the example simulations using Slurm.
- Consult the CUDA reference when checking GPU software compatibility.

## Credits and licenses

Site infrastructure is adapted from the ENCCS Sphinx lesson template at commit
`b460ac1af94049533a41abdb03ed4c0cf0177f1e`.

Template license notices are retained in
{download}`LICENSE <../LICENSE>` (CC BY-SA 4.0) and
{download}`LICENSE.code <../LICENSE.code>` (MIT).
