# Near Memory Computing: Past, Present, and Future
[reference](https://www.researchgate.net/publication/335028505_Near-Memory_Computing_Past_Present_and_Future)

The reason mentioned in this paper for moving toward these technologies is that conventional way of moving data to the CPU has become a significant performance bottleneck. Processing in the home of the data can significantly diminish the data movement problem at data-intensive applications.

Three dimensional stacking is considered as the true enabler of processing close to the memory. It allows stacking logic and memory together using TSVs (Through-Silicon Vias). Some of these technologies:
- Micron's HMC (Hybrid Memory Cube)
- High bandwidth memory (HBM) of AMD and Hynix
- Samsung's wide I/O

The following figure show the evolution of computing systems through time from left to right.

![computing systems evolution](../img/computing_systems_evolution.png)

**NOTE**: Conceptually, the approach of near-memory computing can be applied to any level or type of memory to improve the overall system performance.

There were some work on in-disk computation, but because of its negligible performance imporvement it is not considered serious.

## Background
First Near-Memory computing system was developed in 1990: Vector IRAM (VIRAM), a vector processor with a on-chip embedded DRAM to exploit data parallelism in multimedia applications. Although the performance obtained with this system was obtained, they did not pervail because of technological limits (the amount of the on-chip memory that could be integrated with the vector processor was limited due to the difference in logic and memory technology processes.). However, nowadays has changed completely.

## Processing Near Main Memory
- Programmable Unit (CPU, GPU)
- Fixed-Function Unit (ASIC)
- Reconfigurable Unit (FPGA)


## Processing Near Storage Class Memory
- Programmable Unit (CPU, GPU)
- Fixed-Function Unit (ASIC)
- Reconfigurable Unit (FPGA)
- 
## Challenges of Near-Memory Computing
- virtual memory support
  - software or hardware (hardware can be optimal instead of OS)
- Cache Coherence (which the architect's choice on this matter is going to influence the performance drastically)
  - Restricted region: dividing the memory into two parts: one for host processor (cachable), and another for the accelerator that is uncachable, or just caching in one block of the LLC to invalidate or write-back on the monitoring.
  - Non-restricted region: leading to a significant amount of memory traffic. A work proposed keeping a memory coherent between a host GPU and near-memory compute units, flushing the L2.
  - My point here is that keeping the memory consistent and coherent lies in the realm of coherence and consistency for heterogeneous systems. 
- Proramming Model
  - Compiler
  - Programmer
  - Sophisticated mechanisms touching from the application to instruction selection in compiler to invoke NMC logic units. Profiling applications to identify the potential for NMC acceleration

- Data Mapping


## Design Space Exploration for Near-Memory Computation


## Practicalities of Near-Memory Computation
