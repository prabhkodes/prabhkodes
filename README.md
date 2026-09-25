<h1 align="center">Prabhsharan Singh</h1>

<p align="center">
  <b>I make science code go brrrrrr.</b><br>
  <sub>Master's in High Performance Computing · ICTP &amp; SISSA, Trieste, Italy</sub>
</p>

<p align="center">
  <a href="mailto:prabhsharan84@gmail.com"><img alt="Email" src="https://img.shields.io/badge/prabhsharan84@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/prabhsharan-singh"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white"></a>
  <img alt="Location" src="https://img.shields.io/badge/Trieste,%20Italy-555?style=flat-square&logo=googlemaps&logoColor=white">
  <img alt="Open to relocation" src="https://img.shields.io/badge/open%20to%20relocation-2ea44f?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/prabhkodes/miniWeather-mpi-openacc"><img alt="Fortran" src="https://img.shields.io/badge/Fortran-734F96?style=for-the-badge&logo=fortran&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/jacobi-poisson-solver"><img alt="C++" src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/gpu-kernel-profiling"><img alt="CUDA" src="https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/fft-gpu-programming-models"><img alt="OpenACC" src="https://img.shields.io/badge/OpenACC-FF6200?style=for-the-badge&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/matrix-multiplication-parallel"><img alt="MPI" src="https://img.shields.io/badge/MPI-364d6e?style=for-the-badge&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/jacobi-poisson-solver"><img alt="OpenMP" src="https://img.shields.io/badge/OpenMP-006DB8?style=for-the-badge&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/low_level_optimisations"><img alt="LLVM" src="https://img.shields.io/badge/LLVM-262D3A?style=for-the-badge&logo=llvm&logoColor=white"></a>
  <a href="https://github.com/prabhkodes/gpu-kernel-profiling"><img alt="Nsight" src="https://img.shields.io/badge/Nsight-76B900?style=for-the-badge&logo=nvidia&logoColor=white"></a>
</p>

---

## Outside the terminal

I like computers, jazz, yoga, writing, my friends, and being silly.

- **Currently listening to:** [Kosmochoojuwa](https://www.youtube.com/watch?v=dq2YeAw9dTw) by Kosmonauci
- **Currently reading:** *Letters to Milena* by Kafka
- **Currently obsessing over:** distributed LLM training

---

Currently finishing a **fully funded Master's in High Performance Computing** at the
[**Abdus Salam International Centre for Theoretical Physics (ICTP)**](https://www.ictp.it/) — a UNESCO
research centre in Trieste — run jointly with [SISSA](https://www.sissa.it/), the International School
for Advanced Studies. Thesis defends December 2026.

Before that, four years building production platforms — distributed compute, CI/CD and data pipelines —
at AI startups. These days I spend my time porting and profiling scientific codes for heterogeneous
CPU/GPU systems.

Most of what's here was run on **Leonardo** at CINECA, up to 1792 cores or 40 A100s.
Each badge above links to a project that uses it.

**Right now**

- **Master's thesis with [OGS](https://www.ogs.it/)**, the National Institute of Oceanography and Applied Geophysics — taking [`gmrecords`](https://github.com/usgs/groundmotion-processing)
  ground-motion processing to the **edge**, so a seismological network processes records on the
  accelerometers themselves instead of shipping raw waveforms to a central server.
- **Ongoing research on [xFFL](https://github.com/alpha-unito/xffl) with the University of Turin** —
  cross-facility federated learning, training across HPC sites that cannot pool their data.

## Finding out why code is slow — then making it go brrrr

| Project | What it is | Result |
|---|---|---|
| **[low_level_optimisations](https://github.com/prabhkodes/low_level_optimisations)** | An out-of-tree **LLVM pass** that classifies loop memory access by stride and predicts vectorisability before the code runs | In a DRAM-bound loop, **traffic beats codegen** — shown with a control |
| **[gpu-kernel-profiling](https://github.com/prabhkodes/gpu-kernel-profiling)** | Reading Nsight Systems traces on A100 — plus tooling to extract kernel timings straight from the trace databases | **11% of peak**, traced to uncoalesced writes |
| **[fft-gpu-programming-models](https://github.com/prabhkodes/fft-gpu-programming-models)** | Six implementations of one FFT — hand-written CUDA, OpenACC and cuFFT — benchmarked head to head | cuFFT **~12×** over the best verified kernel |
| **[matrix-multiplication-parallel](https://github.com/prabhkodes/matrix-multiplication-parallel)** | Dense GEMM four ways, with roofline analysis | **45 TFLOP/s** on 16 nodes |

## Scientific codes, ported and optimised (not just about going brrrr)

| Project | What it is | Result |
|---|---|---|
| **[miniWeather-mpi-openacc](https://github.com/prabhkodes/miniWeather-mpi-openacc)** | Fortran atmospheric model taken to MPI + OpenMP + OpenACC, with NetCDF output, CMake and containerised CI | **190 s → 2.1 s** on 256 cores, then **≈4×** on 8 A100s |
| **[quantum-espresso-ks-scaling](https://github.com/prabhkodes/quantum-espresso-ks-scaling)** | Profiling and GPU-porting the Davidson eigensolver inside Quantum ESPRESSO — plane-wave DFT | FFT **11.3×**, solver only **2.4×** |
| **[jacobi-poisson-solver](https://github.com/prabhkodes/jacobi-poisson-solver)** | One Laplace problem in three parallel models — MPI+OpenMP, HDF5 parallel I/O, OpenACC — plus NVIDIA's NVSHMEM sample | **94%** node-to-node efficiency, 1→10 nodes |
| **[fisher-kpp-rumour-diffusion](https://github.com/prabhkodes/fisher-kpp-rumour-diffusion)** | Reaction-diffusion PDE solved in parallel with PETSc — `DMDA`, Runge-Kutta time integration | Matches the analytic wave speed |

## Making it run anywhere, and at scale (partially about going brrrr)

| Project | What it is |
|---|---|
| **[hpc_containers](https://github.com/prabhkodes/hpc_containers)** | One MPI+OpenACC solver shipped four ways — native, InfiniBand-forced, Singularity, Docker — including the UCX/PMIx configuration that makes MPI work over InfiniBand *inside* a container |
| **[federated-learning-nextflow](https://github.com/prabhkodes/federated-learning-nextflow)** | FedAvg as a real Nextflow/SLURM workflow, one GPU per client, model weights exchanged as files |
| **[python-hpc-interop](https://github.com/prabhkodes/python-hpc-interop)** | What Python actually costs in HPC — pybind11 runs **4–17%** behind native C++, depending on scale |

## How I report numbers

Every performance figure in these repos is re-derived from the committed logs and source rather than
quoted from memory, and each one is published with the things that make it mean something — the
baseline it's measured against, the build flags, and what was held constant between the runs being
compared.

Where a figure doesn't survive that check, I change it and write up the reasoning in the repo. The
[LLVM pass](https://github.com/prabhkodes/low_level_optimisations/tree/main/llvm_pass_profiling#corrections)
is the one I'd point at: I built a control experiment to test my own published conclusion, and it
overturned it — three static instruments had agreed with each other because none of them can see
memory traffic. The control, the measurements and the revised result are all in the repo.

## HPC stack

| | |
|---|---|
| **Languages** | Fortran · C · C++20 · Python · Bash |
| **Parallel programming** | MPI (OpenMPI, HPC-X) · OpenMP · OpenACC · CUDA · NVSHMEM · NCCL |
| **GPU libraries** | cuBLAS · cuFFT · CuPy · NVIDIA HPC SDK |
| **Performance analysis** | Nsight Systems · NVTX · `perf` · llvm-mca · LLVM analysis passes · roofline modelling |
| **Scientific I/O** | NetCDF · HDF5 · collective MPI-IO · ParaView / VisIt |
| **Numerical libraries** | PETSc · ScaLAPACK · OpenBLAS · FFTW · LAPACK |
| **Build &amp; test** | CMake · CTest · Make · Git · GitHub Actions |
| **Clusters &amp; containers** | SLURM · UCX / InfiniBand · NUMA-aware pinning · Docker · Singularity / Apptainer |
| **Machines** | Leonardo (CINECA) · JUPITER (JSC) · COKA (INFN) · ICTP / SISSA / Ferrara clusters |

## ML stack

| | |
|---|---|
| **Frameworks** | PyTorch · TensorFlow · scikit-learn |
| **Scientific Python** | NumPy · SciPy · Pandas · Matplotlib · Numba · pybind11 · mpi4py |
| **Distributed &amp; federated** | FedAvg · Nextflow · Kubeflow · Argo Workflows |
| **Tracking** | Weights &amp; Biases |

## Platform engineering stack

| | |
|---|---|
| **Cloud** | AWS · GCP (Cloud Run, GKE) |
| **Orchestration** | Kubernetes · Docker · Ansible |
| **Backend** | Django · FastAPI · Flask · REST / SOAP integrations |
| **Data stores** | PostgreSQL · MongoDB · Redis · ChromaDB |
| **Observability** | Prometheus · Grafana · Loki · OpenTelemetry · Sentry |
| **Reliability** | Load testing · autoscaling · capacity planning · CI/CD · on-call automation |

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
    <a href="mailto:prabhsharan84@gmail.com">prabhsharan84@gmail.com</a> ·
    <a href="https://www.linkedin.com/in/prabhsharan-singh">LinkedIn</a>
  </sub>
</p>
