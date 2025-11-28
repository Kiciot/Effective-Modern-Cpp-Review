## 简介 (Introduction)

本复习笔记基于 Scott Meyers 的经典著作《Effective Modern C++》，旨在提炼 C++11 和 C++14 的核心特性与最佳实践。与仅仅介绍新语法的教程不同，本书更关注如何**高效**、**正确**地使用这些新特性来编写可移植、可维护的代码。

**核心目标**：

- **掌握新特性**：深入理解 `auto`、智能指针、移动语义、Lambda 表达式、并发 API 等 C++11/14 的关键机制。
- **理解背后的原理**：不仅仅是“怎么做”，更重要的是“为什么”。理解每个条款（Item）背后的设计哲学和潜在陷阱。
- **区分不同版本**：明确 C++98、C++11 和 C++14 之间的差异，以及废弃特性（如 `std::auto_ptr`）的替代方案。

**术语约定**：

- **C++**：指代所有版本。
- **C++11**：包含 C++11 和 C++14（因为 C++14 是 C++11 的超集）。
- **C++14**：特指 C++14 版本。
- **左值 (Lvalue) 与 右值 (Rvalue)**：
  - **左值**：通常可取地址，对应于具名对象。形参（即使是右值引用类型）本身也是左值。
  - **右值**：通常不可取地址，对应于临时对象，是移动操作的候选者。
- **副本 (Copy)**：指通过拷贝构造或移动构造产生的新对象。
- **移动语义**：利用右值引用的特性，将资源从一个对象转移到另一个对象，而非深拷贝。
- **完美转发 (Perfect Forwarding)**：保持参数的左值/右值属性不变地传递给另一个函数。

本笔记将按照原书的章节结构，对每个条款进行精炼总结，帮助你快速回顾和巩固现代 C++ 的知识体系。

### Introduction



These review notes are based on Scott Meyers' classic book *"Effective Modern C++"*, aiming to distill the core features and best practices of C++11 and C++14. Unlike tutorials that merely introduce new syntax, this book focuses on how to use these new features **effectively** and **correctly** to write portable, maintainable code.

**Core Goals:**

- **Mastering New Features:** Deeply understand key mechanisms of C++11/14, such as `auto`, smart pointers, move semantics, Lambda expressions, and the Concurrency API.
- **Understanding the Underlying Principles:** It's not just about "how," but more importantly, "why." Understand the design philosophy and potential pitfalls behind each Item.
- **Distinguishing Between Versions:** Clarify the differences between C++98, C++11, and C++14, as well as alternatives for deprecated features (like `std::auto_ptr`).

**Terminology Conventions:**

- **C++**: Refers to all versions.
- **C++11**: Includes both C++11 and C++14 (since C++14 is a superset of C++11).
- **C++14**: Specifically refers to the C++14 version.
- **Lvalues vs. Rvalues**:
  - **Lvalue**: Typically addressable, corresponding to named objects. Parameters (even those of rvalue reference types) are themselves lvalues.
  - **Rvalue**: Typically not addressable, corresponding to temporary objects; they are candidates for move operations.
- **Copy**: Refers to a new object created via either copy construction or move construction.
- **Move Semantics**: Utilizing rvalue references to transfer resources from one object to another, rather than performing a deep copy.
- **Perfect Forwarding**: Passing arguments to another function while preserving their original lvalue/rvalue nature.

These notes follow the chapter structure of the original book, providing concise summaries for each Item to help you quickly review and consolidate your knowledge of modern C++.
