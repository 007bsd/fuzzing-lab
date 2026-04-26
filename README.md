# Fuzzing Lab

Fuzzing research, resources, and trophy case.

---

## Trophy Case

[trophy-case/README.md](trophy-case/README.md)

---

## What is Fuzzing?

Fuzzing (or fuzz testing) is an automated testing technique that generates large volumes of random, malformed, or unexpected inputs and feeds them into a program to find bugs. Unlike hand-written tests, fuzzers explore inputs that developers would never think to try.

The technique was pioneered by Barton Miller at the University of Wisconsin-Madison in 1988. Today it is one of the most effective methods for finding real-world bugs. Google's OSS-Fuzz alone has found over 10,000 bugs in critical open source projects.

---

## How Fuzzing Works

The core fuzzing loop:

1. **Generate** an input, either randomly or by mutating an existing one
2. **Execute** the target with that input
3. **Observe**: did it crash? trigger a sanitizer? violate an invariant?
4. **Feedback**: if the input reached new code, save it to the corpus and mutate it further

Coverage-guided fuzzers (AFL, libFuzzer) use instrumentation to track which code paths each input exercises. Inputs that reach new paths are kept; others are discarded. Over time the fuzzer builds a corpus that covers more and more of the program.

---

## Types of Fuzzing

**Coverage-guided fuzzing** mutates inputs to maximise code coverage. The fuzzer instruments the target binary and uses coverage feedback to guide exploration. Best for finding crashes, memory corruption, and panics in native code.
Tools: libFuzzer, AFL++, cargo-fuzz, Honggfuzz.

**Property-based fuzzing** generates inputs to break user-defined invariants: round-trips, oracle comparisons, no unexpected exceptions. The tester describes what must always be true; the fuzzer finds a counterexample. Best for libraries and parsers where correctness can be precisely stated.
Tools: Hypothesis (Python), QuickCheck (Haskell), fast-check (JS).

**Continuous fuzzing** runs fuzzers at scale, permanently, against a project's main branch. New bugs are filed automatically.
Tools: OSS-Fuzz, ClusterFuzz.

---

## What Fuzzing Finds

- **Unhandled exceptions**: inputs the program was never designed to handle
- **Silent wrong results**: incorrect output with no error or warning, the hardest class to catch with traditional tests
- **Hangs and infinite loops**: inputs that cause the program to never return
- **Error handling gaps**: internal errors leaking to callers instead of clean, meaningful messages
- **Long-dormant bugs**: code paths that have never been exercised accumulate bugs over years; fuzzers reach them

---

## References

- [Wikipedia - Fuzzing](https://en.wikipedia.org/wiki/Fuzzing)
- [google/fuzzing](https://github.com/google/fuzzing): guides and tutorials
- [AFLplusplus/AFLplusplus](https://github.com/AFLplusplus/AFLplusplus): coverage-guided fuzzer for native code
- [LLVM libFuzzer](https://llvm.org/docs/LibFuzzer.html): in-process, coverage-guided fuzzing engine
- [google/clusterfuzz](https://github.com/google/clusterfuzz): scalable fuzzing infrastructure
- [google/clusterfuzzlite](https://github.com/google/clusterfuzzlite): CI-integrated continuous fuzzing for individual projects
- [google/oss-fuzz](https://github.com/google/oss-fuzz): continuous fuzzing for open source
- [antonio-morales/Fuzzing101](https://github.com/antonio-morales/fuzzing101): hands-on fuzzing exercises
- [Trail of Bits Testing Handbook - Fuzzing](https://appsec.guide/docs/fuzzing/)
