# Near Memory Computing
## Introduction
Nowadays, The technology trend is toward memory-centric chip technologies promising to solve the bandwidth bottleneck issues in today's systems. The idea behind these technologies is to bring the memory closer to the processing units to speed up the system. 

Memory-centric is a broad term which can be dived in with two concepts:
- **In-Memory Computing**: Bringing the processing tasks near or inside the memory.
- **Near-Memory Computing**: incorporating memory and logic in an advanced IC package.

In today's computing systems data moves between the memory and the processor causing latency and power consumption (~ 60% of modern computing systems) referred to as the memory wall.

**Steve Pawlowski**: "Everbody is striving for a chip that has 100 TeraOPS of performance, but to get that efficiency you must have several things going on simultaneously, meaning having to bring data into the chip and get it out of the chip as fast as possible."

Today's computing systems' need is not only large memories but also fast ones, for example we are moving toward mobile devices with AI applications, high-resolution screens etc.

One approach to provide what we need is to integrate processors, memory, and devices in a traditional Von Neumann architecture, but this adds much cost and complexity. Another one is to move toward adopting in- and near-memory architectures.

For years, Oracle, SAP, and others have used in-memory computation in the database world. Accessing to a database that is stored in the disk can be slow. So, database vendors have developed ways to process the data in the main memory in a server or subsystem, not the disk drive, which results in boosting the transactions. What happens in database realm is following Von Neumann model, but trying to co-locate the data to that process to make it faster. What happens here is that, these systems try to keep the databases in RAMs instead of the disks to enbale fast reads and writes.

In semi-conductor/ systems world, in-memory computing is bringing memory closer or inside the processing units. Recently, there are some chips from some companies like what UPMEM introduced in 2019. The point here is not to confuse these chip with what is going on in the database field[1](https://www.anandtech.com/show/14750/hot-chips-31-analysis-inmemory-processing-by-upmem)/ [2](https://www.upmem.com/video-upmem-presenting-its-true-processing-in-memory-solution-hot-chips-2019/).

Many of the these chip are designed to drive neural networks because there are lots of weights have to be brought into the procesing system which they are not going to reused soon again. Doing this job with GPU cost so power consumption because involving RF and shared memory. Even if we build a traditional system with a large SRAM that can keep the entire application, we still have to read from that and send them to the right processing unit (for example the right SP on a SM in a GPU).

Another way is neuromorphic computing trying to mimic the brain on the silicon, which is so close to what in-memory or near-memory tries to do.

Near-memory tries to incorporate memory and computing units on a single IC package, such as 2.5D/ 3D. The main goal of putting memory layers on the processing unit is to increase the bandwidth of data movement between the memory and the processor.

I think it is enough for an introduction. Now, we have a basic view of what is happening in this research line. So, we move to the papers published in this area.

## Research Papers
[1 - Near-Memory Computing: Past, Present, and Future (Survey)](papers/01-near_memory_computing.past_present_and_future.md) |  [Paper reference Link]()

[2 - PM: Power Modeling and Power Management for Processing-in-Memory (Modeling)](papers/02-PM.md)

[03 - RC-NVM: Enabling Symmetric Row and Column Memory Accesses for In-Memory Databases (In-Memory Databases)](papers/03-RC-NVM.md)

[04 - RecNMP - Accelerating Personalized Recommendatin with Near-Memory Processing](papers/04-RecNNP.md)

[05 - iPIM: Programmable In-Memory Image Processing Accelerator Using Near-Bank Architecture](papers/05-iPIM.md)

[06 - FloatPIM: In-Memory Acceleration of Deep Neural Network Training with High Precision](papers/06-FloatPIM.md)

[07- Impala: Algorithm/Architecture Co-Design for In-Memory Multi-Stride Pattern Matching](papers/07-Impala.md)

[08 - NAND-Net: Minimizing Computational Complexity of In-Memory Processing for Binary Neural Networks](papers/08-NAND-Net.md)

[09 - PIM-Enabled Instructions: A low-Overhead, locality-Aware Processing-in-Memory Architecture](papers/09-PIM-Enable_Instructions.md)

[10 - Processing-in-Memory Enabled Graphics Processors for 3D Rendering](papers/10-Processing-in-memory_enabled_graphics_for_3D_rendering.md)

[11 - A Scalable Processing-in-Memory Accelerator for Parallel Graph Processing](papers/11-a_scalable_processing_in_memory_accelerator_for_parallel_graph_processing.md)

[12 - PRIME - A Novel Processing-in_Memory Architecture for Neural Network Computation in ReRAM-based Main Memory](PRIME.md)