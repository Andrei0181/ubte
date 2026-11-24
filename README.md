# UBTE — Universal Binary Transformation Engine

UBTE is a systems-programming project focused on low-level binary transformation and lookup operations, with an emphasis on correctness, predictable behavior, and performance-aware implementation.

## Project direction

The intended system is being developed around:

- deterministic byte-oriented transformations;
- lookup and mapping primitives;
- a portable scalar implementation as a correctness baseline;
- architecture-specific acceleration only where the instruction semantics support the required operation;
- repeatable correctness tests and benchmarks.

## Current repository status

**Early scaffold / work in progress.**

The public repository currently contains the initial CMake project scaffold. It does not yet contain the complete transformation engine, production SIMD kernels, a validated benchmark suite, or a release-ready API.

This distinction is intentional: the repository records the project direction without presenting planned functionality as already implemented.

## Build the current scaffold

Requirements:
- CMake 3.15+
- A C++ compiler supported by CMake

```bash
git clone https://github.com/Andrei0181/ubte.git
cd ubte
cmake -S . -B build
cmake --build build
```

The current build only verifies that the CMake scaffold configures and builds. It is not yet a functional UBTE engine test.

## Development roadmap

1. Define and document the byte-transformation API and correctness contract.
2. Implement a portable scalar reference path.
3. Add exhaustive tests for all byte values and boundary cases.
4. Benchmark representative workloads with reproducible methodology.
5. Evaluate SIMD paths against the scalar reference; retain an accelerated path only when it is correct for the full input domain.
6. Publish performance results together with compiler, CPU, and test details.

## Engineering principle

Correctness comes before acceleration. SIMD implementations must respect the actual lane and instruction semantics of the target architecture; performance claims will be published only with reproducible measurements.

## Status

Experimental project. Not intended for production use yet.
