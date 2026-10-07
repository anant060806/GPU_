## ⚡ CUDA

**CUDA (Compute Unified Device Architecture)** is NVIDIA's parallel computing platform that allows programs to use the GPU for general-purpose computation.

A simple CUDA kernel:

```cpp
__global__ void add(int *a, int *b, int *c)
{
    int i = blockIdx.x * blockDim.x + threadIdx.x;
    c[i] = a[i] + b[i];
}
```

The kernel can be executed by many GPU threads simultaneously:

```cpp
add<<<blocks, threads>>>(a, b, c);
```

This allows the GPU to perform the same operation on many data elements in parallel.

**In simple terms:**

```text
CPU → Sequential / Few powerful cores
GPU → Massive parallel execution
CUDA → Programming interface to use NVIDIA GPU parallelism
```
