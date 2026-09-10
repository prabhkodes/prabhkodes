<h1 align="center">Prabhsharan Singh</h1>

<p align="center">
  <b>I make scientific code run faster on bigger machines.</b><br>
  <sub>Master in High Performance Computing · ICTP &amp; SISSA, Trieste</sub>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Fortran-734F96?style=flat-square&logo=fortran&logoColor=white">
  <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white">
  <img src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/MPI-364d6e?style=flat-square">
  <img src="https://img.shields.io/badge/OpenMP-006DB8?style=flat-square">
  <img src="https://img.shields.io/badge/OpenACC-FF6200?style=flat-square">
  <img src="https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white">
  <img src="https://img.shields.io/badge/LLVM-262D3A?style=flat-square&logo=llvm&logoColor=white">
  <img src="https://img.shields.io/badge/SLURM-46a2f1?style=flat-square">
</p>

---

Currently finishing an **MHPC at ICTP/SISSA** (thesis December 2026) after four years building
production platforms — distributed compute, CI/CD and data pipelines — at AI startups. These days I
spend my time porting and profiling scientific codes for heterogeneous CPU/GPU systems.

Most of what's here was run on **Leonardo** at CINECA, up to 1792 cores or 40 A100s.

## Scientific codes, ported and optimised

| Project | What it is | Result |
|---|---|---|
| **[miniWeather-mpi-openacc](https://github.com/prabhkodes/miniWeather-mpi-openacc)** | Fortran atmospheric model taken to MPI + OpenMP + OpenACC, with parallel NetCDF, CMake and containerised CI | **190 s → 2.1 s** on 256 cores, another **8.2×** on GPU |
| **[quantum-espresso-ks-scaling](https://github.com/prabhkodes/quantum-espresso-ks-scaling)** | Profiling and GPU-porting the Davidson eigensolver inside Quantum ESPRESSO — plane-wave DFT | FFT scales **11.3×**, the solver only **2.4×** — the bottleneck isn't where you'd guess |
| **[jacobi-poisson-solver](https://github.com/prabhkodes/jacobi-poisson-solver)** | One Laplace problem in four parallel models — MPI+OpenMP, HDF5 parallel I/O, OpenACC, NVSHMEM | **94% efficiency to 1120 cores**; checkpointing changes which config is fastest |
| **[fisher-kpp-rumour-diffusion](https://github.com/prabhkodes/fisher-kpp-rumour-diffusion)** | Reaction-diffusion PDE solved in parallel with PETSc — `DMDA`, Runge-Kutta time integration | Validated against the analytic travelling-wave speed |

## Finding out why code is slow

| Project | What it is | Result |
|---|---|---|
| **[low_level_optimisations](https://github.com/prabhkodes/low_level_optimisations)** | An out-of-tree **LLVM pass** that classifies loop memory access by stride and predicts vectorisability before the code runs | Isolated **30% pure lost vectorisation** with cache behaviour held constant |
| **[gpu-kernel-profiling](https://github.com/prabhkodes/gpu-kernel-profiling)** | Reading Nsight Systems traces on A100 — plus tooling to extract kernel timings straight from the trace databases | Traced a kernel at **11% of peak** to a 32-way shared-memory bank conflict |
| **[fft-gpu-programming-models](https://github.com/prabhkodes/fft-gpu-programming-models)** | Six implementations of one FFT — hand-written CUDA, OpenACC and cuFFT — benchmarked head to head | OpenACC came in **≈5× slower** than hand-tuned CUDA |
| **[matrix-multiplication-parallel](https://github.com/prabhkodes/matrix-multiplication-parallel)** | Dense GEMM four ways, with roofline analysis | **45 TFLOP/s on 16 nodes** at N = 224,000 |

## Making it run anywhere, and at scale

| Project | What it is |
|---|---|
| **[hpc_containers](https://github.com/prabhkodes/hpc_containers)** | One MPI+OpenACC solver shipped four ways — native, InfiniBand-forced, Singularity, Docker — including the UCX/PMIx configuration that makes MPI work over InfiniBand *inside* a container |
| **[federated-learning-nextflow](https://github.com/prabhkodes/federated-learning-nextflow)** | FedAvg as a real Nextflow/SLURM workflow, one GPU per client, model weights exchanged as files |
| **[python-hpc-interop](https://github.com/prabhkodes/python-hpc-interop)** | What Python actually costs in HPC — pybind11 lands within **5%** of native C++ |

## Toolchain

| | |
|---|---|
| **Languages** | Fortran · C · C++20 · Python · Bash |
| **Parallel** | MPI · OpenMP · OpenACC · CUDA · NVSHMEM · cuBLAS / cuFFT |
| **Performance** | Nsight Systems · NVTX · `perf` · llvm-mca · LLVM analysis passes · roofline |
| **Scientific I/O** | NetCDF · HDF5 · collective MPI-IO · PETSc |
| **Build &amp; ship** | CMake · CTest · GitHub Actions · Docker · Singularity |
| **Clusters** | SLURM · UCX / InfiniBand · NUMA-aware pinning · Kubernetes |
| **Machines** | Leonardo (CINECA) · JUPITER (JSC) · COKA (INFN) · ICTP / SISSA clusters |

## Elsewhere

Smaller collections that the projects above grew out of —
[cuda_stuff](https://github.com/prabhkodes/cuda_stuff) ·
[open_mpi_openmp_stuff](https://github.com/prabhkodes/open_mpi_openmp_stuff) ·
[file_io_stuff](https://github.com/prabhkodes/file_io_stuff) ·
[fortran](https://github.com/prabhkodes/fortran) ·
[petsc](https://github.com/prabhkodes/petsc) ·
[quantum_computing](https://github.com/prabhkodes/quantum_computing)

<p align="center">
  <sub>
    Trieste, Italy ·
    <a href="mailto:prabhsharan84@gmail.com">prabhsharan84@gmail.com</a> ·
    <a href="https://www.linkedin.com/in/prabhsharan-singh">LinkedIn</a> ·
    open to relocation
  </sub>
</p>
