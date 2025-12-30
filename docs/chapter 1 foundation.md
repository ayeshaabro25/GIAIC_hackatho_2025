# Foundation

Introduction

Computing is built on a small set of deep, reusable ideas. This chapter — "Foundation" — introduces those ideas and the mental models you will return to throughout this book: representation, abstraction, algorithm, complexity, correctness, and architecture. Understanding these fundamentals gives you the tools to reason about problems, choose appropriate techniques, and communicate precisely with other practitioners.

1. Representation: How Information Is Encoded

At the lowest level, computing is the representation and manipulation of information. Representation choices affect what is easy or hard to compute.

- Binary and number systems: Bits, bytes, integers, floating point — each has precision, range, and performance trade-offs.
- Text and encoding: character sets and encodings (ASCII, UTF-8) determine how text is stored and transmitted.
- Structured data: lists, trees, tables, graphs — choosing the right structure clarifies what operations are efficient.

Key idea: pick representations that make the important operations simple.

2. Abstraction: Managing Complexity by Hiding Details

Abstraction lets us reason at higher levels without being bogged down by lower-level mechanics.

- Layers: hardware, machine code, operating system, runtime, languages, libraries — each layer exposes a simpler interface to the layer above.
- Interfaces and contracts: specify what a module promises to do and what it requires from others.
- Encapsulation: group data and operations so internal invariants are easier to maintain.

Practice: design clear interfaces, prefer orthogonality, and resist leaking internal details across module boundaries.

3. Algorithm: Recipes for Transforming Data

An algorithm is a finite, well-defined sequence of steps for performing a task.

- Correctness: an algorithm should meet its specification for all valid inputs.
- Termination: prove or reason that the algorithm completes.
- Determinism vs. nondeterminism: some algorithms behave predictably; others use randomness or concurrency.

Examples: sorting (insertion, quicksort, mergesort), searching (linear, binary), graph traversal (BFS, DFS), and dynamic programming.

4. Complexity: Measuring Cost and Scalability

Complexity analyzes resource usage — time, memory, energy — as input size grows.

- Asymptotic notation (O, Θ, Ω) describes growth rates abstractly.
- Trade-offs: faster algorithms can use more memory; simpler code can be slower but easier to maintain.
- Empirical vs. theoretical: benchmarks are useful but must be interpreted alongside algorithmic analysis.

Rule of thumb: prefer algorithms with better asymptotic guarantees for large inputs; for small or constrained cases, constant factors and simplicity matter more.

5. Correctness and Testing: Reducing Uncertainty

Correctness is the degree to which software meets its specification.

- Specifications: write clear, testable requirements.
- Testing: unit tests, property-based tests, integration tests, and fuzzing uncover bugs at different scopes.
- Formal methods: proofs, model checking, and type systems can provide stronger guarantees when needed.

Balance: combine pragmatic testing with stronger techniques on critical components.

6. Architecture and Systems Thinking

Where algorithms and data meet hardware, architecture governs non-functional properties: performance, reliability, and scalability.

- Concurrency and parallelism: threads, processes, message passing — understand synchronization, races, and coordination.
- Storage and retrieval: trade-offs between latency, throughput, consistency, and durability.
- Fault tolerance: detect, isolate, and recover from failures; design for graceful degradation.

Architectural patterns: client-server, layered systems, event-driven, microservices — choose patterns that fit your constraints and team.

7. Computational Thinking: A Problem-Solving Mindset

Computational thinking combines decomposition, pattern recognition, abstraction, and algorithm design.

- Decomposition: split problems into independent pieces.
- Pattern recognition: map new problems to known solutions.
- Generalization and parameterization: identify the variables and make solutions reusable.

This mindset applies beyond programming: formalizing problems and seeking automatable steps clarifies many domains.

8. Trade-offs and Ethical Considerations

Every design involves trade-offs: speed vs. memory, correctness vs. development time, centralization vs. distribution.

Also consider ethics: privacy, bias, accessibility, and environmental cost. Foundations of computing include responsibility for how technology affects people.

9. Example: From Idea to Implementation

Problem: build a simple address book that supports add, remove, search by name.

- Representation: store each entry as a record (name, phone, email). Use an array for small sets, a hash table for faster lookup.
- Abstraction: expose an interface with `add(entry)`, `remove(id)`, `find(name)`.
- Algorithm: for search, use hashing or keep a sorted array and apply binary search.
- Complexity: hashing yields average O(1) lookup; sorted array gives O(log n) search but O(n) insertion.
- Correctness: write unit tests for edge cases (duplicate names, empty fields).

Choosing the right combination depends on expected size and operations; document assumptions and revise as usage becomes clearer.

10. Exercises

Exercise 1 — Representation Choice: For storing sensor data that arrives in bursts, which representation and storage strategy would you pick? Explain trade-offs.

Exercise 2 — Algorithm Selection: You must sort 1,000 small records on an embedded device. Which sorting algorithm would you choose and why?

Exercise 3 — Design for Failure: Sketch an approach for making a simple web service resilient to transient network failures.

11. Further Reading

- "Structure and Interpretation of Computer Programs" — Harold Abelson and Gerald Jay Sussman.
- "Introduction to Algorithms" — Cormen, Leiserson, Rivest, and Stein.
- "Computer Organization and Design" — Patterson and Hennessy.

Closing

This chapter established the lens you will use across the book: represent problems clearly, design clean abstractions, choose algorithms with an eye to complexity and correctness, and consider architectural trade-offs and responsibility. The next chapters build on these foundations with concrete techniques and worked examples.
