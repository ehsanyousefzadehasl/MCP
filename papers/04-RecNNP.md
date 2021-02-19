# RecNMP: Accelerating Personalized Recommendation with Near-Memory Processing

[Reference](https://ieeexplore.ieee.org/document/9138955)

ISCA - 2020

## What is the problem the paper is trying to solve?
The performance of personalized recommendation system, which leverage deep learning models and accunting for the majority of data center AI cycles, is dominated by memory-bound sparse embedding operations with unique irregular memory access patterns posing a fundamental challenge to accelerate. Embedding operations with high model-, operator- and data-level parallelism lead to memory bandwidth saturation limiting recommendation inference performance.

## What are the key ideas of the paper? Key insights?
With their in-depth workload characterization, they show that production recommendation models are constrained by memory bandwidth.

## The solution
Proposing a light-weight commodity DRAM compliant, near-memory processing solution to accelerate the embedding operations for DL-based recommendation. RecNMP performs local lookups and pooling functions near memory, supporting a range of sparse embedding inference operators, which produce the general Gather-Reduce execution pattern. They make a design choice to implement selected lightweight functional units with small memory-side caches to limit the area overhead and power consumption. They combine this light-weight hardware with software optimizations including table-aware packet scheduling and hot entry profiling. This work tries to alleviate the performance bottleneck (because of SLS: Sparse Length Sum) and improve system throughput by devising a novel NMP solution to offload the SLS-family embedding operations thus covering a broad class of recommendation systems.

## Results
- Up to 9.8X memory latency speedup compared to a highly optimized baseline
- 4.2X throughput improvement
- 45.8% memory energy savings
  
## Strenghts
- Their characterization and experimental methodology is modeled after representative productio configurations and is evaluated using real production embedding table traces.
- 
## Weaknesses
## Comment
## New Ideas?

---
## For learning
- Recent analysis reveals that the top recommendation models collectively contribute to more than 79% of all AI inference cycles across Facebook's production datacenters.
- **Direction**: Most research efforts within the architecture community have focused on accelerating the compute-intensive, highly-regular computational patterns found in fully-connected (FC), convolution (CNN), and recurrent (RNN) neural networks.
- **Direction**: Unlike CNNs and RNNs, recommendation models exhibit low compute-intensity and little to no regularity. Existing acceleration technique either do not apply or offer small improvements at least, as they tend to exploit regular reusable dataflow patterns and assume high spatial locality, which are not the main performance bottleneck in recommendation systems.
- Modern recommendation models have an extremely large feature set to capture a range of user behaviour and preferences. These features are typically separated out into dense and sparse features (i.e., vectors, matrices)m sparse features are processed by indexing large embedding tables.
- Generally, embedding table operations exhibit Gather-Reduce pattern: the specific element-wise reduction operation varies between models.
- The SLS (Sparse Length Sum) operator primitive is widely employed by other production-scale recommendation applications (e.g. YouTube, and Fox).