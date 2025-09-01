# Kernel Compiler Tuning: Optimization-Level Impact on Performance

## Project Overview

This project demonstrates how compiler optimization levels (-Os, -O2, -O3) impact kernel performance through a reference kernel driver implementation. The driver executes identical workloads compiled with different optimization flags and measures performance differences in real-time.

## Problem Statement

The Linux Kernel is compiled with conservative defaults (mostly -O2) for stability across diverse hardware. Modern compiler optimizations like -O3, LTO, and architecture-specific tuning can significantly improve performance in scheduling, memory operations, and syscalls, but the kernel community remains hesitant due to regression concerns.

## Technical Approach

- **Kernel Driver**: Implements parameterizable workload (memory + arithmetic operations)
- **Multi-Object Compilation**: Same workload compiled with -Os, -O2, -O3 flags
- **Runtime Benchmarking**: CPU-pinned execution with nanosecond timing
- **Procfs Interface**: Userspace interaction for triggering benchmarks
- **Performance Metrics**: ns/iteration timing and relative speedup analysis

## Project Structure

```
├── src/                      # Source
├── docs/                     # Documentation
├── README.md                 # This file
└── LICENSE                   # Project license
```

## Building and Usage

### Prerequisites
- Linux kernel headers (`linux-headers-$(uname -r)`)
- GCC or Clang compiler
- Root access for module operations

> [!NOTE]
> Educational Purpose and Reference Implementation
