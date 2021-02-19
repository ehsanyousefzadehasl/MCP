# iPIM: Programmable In-Memory Image Processing Accelerator Using Near-Bank Architecture
[Reference](https://ieeexplore.ieee.org/document/9138985)

## What is the problem the paper is trying to solve?
GPU, which is the state-of-the-art accelerator for image processing, suffers from the memory bandwidth bottlenck.

## What are the key ideas of the paper? Key insights?
To tackle the memory bandwidth bottleneck of GPUs, near-bank architecture provides a promising solution due to its enormous bank-internal bandwidth and low-energy memory accesses. However, previous work lacks hardware programability, while image processing workloads contain numerous heterogeneous pipeline stages with diverse computation and memory access patterns. Enbaling programmable near-bank architecture with low hardware overhead remain challenging.

## The solution
A programmable in-memory image processing accelerator using near-bank architecture (3D-stacking near-bank architecture).
- First, Designing a decoupled cintrol-execution architecture to provide lightweight programmability support.
- Second, Designing a single-instruction-multiple-bank (SIMB) ISA to enable flexible control flow and data access.
- Thrid, Presenting an end-to-end compilation flow based on **Halide** supporting a wide range of image processing applications and mapping them to the designed ISA.
- Then, developing iPIM-aware compiler optimizations, including register allocation, instruction reordering, and memory order enforcement to improve performance.

## Results
- 11.02X acceleration over an NVIDIA Tesla V100 GPU
- 79.49% energy saving over an NVIDIA Tesal V100 GPU

## Strenghts
- The proposed architecture not only enables lightweight programmability to control heterogeneous pipeline stage (base logic die) but also supports parallel execution to provide abundant memory bandwidth for data-intensive image processing operations (PIM dies).

## Weaknesses

## Comment

## New Ideas?

---
## For learning
- Image processing workloads usually involve a large amount of data-intensive computations, thus motivating the design of domain-specific accelerators for both high performance and energy efficiency.
- The memory wall impedes GPU's further performance improvement as a result of both the characteristics of image processing and the limited bandwidth provided by the compute-centric architecture.
- Image processing applications require high memory bandwidth, since most of their pipeline stages have low arithmetic intensity. Even worse, its heterogeneous pipeline stages can hardly be joined due to the introduction of redundant computations and the degradation of parallelism.
- The scaling of memory bandwidth provided by compute-centric architecture is hindered by both the limited number of off-chip pins and costly data movement energy.
- 3D PIM have been shown that provides bandwidth advantages over GPU.
- To further unleash the bank-level bandwidth of 3D-PIM, the near-bank solution is proposed, which closely integrates compute-logic to each bank in the DRAM dies. It can provide 10X peak bandwidth improvement compared with the 3D-PIM because compute-logic directly accesses the local bank without going through limited TSVs (Through Silicon Vias).
- Challenges of near-bank architecture despite its potential:
    1. Heterogeneous image processing pipelines exhibit various computation and memory access patterns. Thus, requiring programmable hardware support. However, directly attaching control cores to each DRAM bank introduces large area overhead. So, it is challenging to design a lightweight architecture supporting diverse image processing pipelines.
    2. The design of ISA needs to be concise and poweful avoiding complex hardware support while enabling flexible computation, data movement, and control flow operations at the same time.
    3. End-to-end compilation support for this accelerator requires easy programming interfaces to enable the near-bank architecture, as well as backend optimizations to fully exploit the hardware potential.

