---
title: "Tuga Compiler & Virtual Machine"
description: "Full compilation pipeline for Tuga, an imperative language with Portuguese-based keywords. Includes ANTLR-generated lexer/parser, two-phase semantic analysis (scoped symbol table + type checking), bytecode generation, and a custom stack-based virtual machine (S-VM) supporting functions, locals, control flow, and forward references."
tech_stack:
  - "Java"
  - "ANTLR 4"
live_url: "https://github.com/LuisAPR1/Compiler-For-Tuga-Language"
live_label: "View on GitHub"
group: "Compilers & Programming Languages"
weight: 70
---

<div>

Built for the **Compilers** course (2024/2025), Tuga is a full compilation pipeline from source code to execution — five distinct phases, each a separate, well-bounded module.

## Pipeline

| Phase | Component | What it does |
|---|---|---|
| Lexing | `TugaLexer` | ANTLR-generated, custom error listener |
| Parsing | `TugaParser` | ANTLR grammar (`Tuga.g4`), syntax errors with line numbers |
| Semantic | `DefPhase` + `RefPhase` | Scoped symbol table, reference resolution, type checking |
| Codegen | `CodeGenerationVisitor` | Emits S-VM bytecode + populates the constant pool |
| Execution | `VirtualMachineS` | Stack-based interpreter with IP/FP registers |

## Language features

- Global and local variable declarations with **nested scopes**.
- Function declarations with typed parameters and optional return types (`inteiro`, `real`, `booleano`, `string`, or `vazio` for void).
- Function calls as **statements** (void) or **expressions** (value-returning).
- Control flow: `se ... senao` (if/else), `enquanto` (while), `retorna` (return).
- Arithmetic, relational, logical, and string-concatenation operators.
- **Type checking** with automatic `inteiro` → `real` promotion.
- **Forward references**: a function can be called before its declaration thanks to the two-phase semantic analysis.

## Stack Virtual Machine

I designed a small **stack VM** (`VirtualMachineS`) with:

- Instruction Pointer (`IP`) and Frame Pointer (`FP`) registers.
- A **constant pool** for literals.
- Global memory + an execution stack for locals, arguments, and return addresses.
- Opcodes for arithmetic, comparisons, control flow (`jump`, `jumpf`), function calls (`call`), and returns (`ret`, `retval`).
- Frame-pointer-relative locals: `lalloc n`, `lload addr`, `lstore addr`.

## Sample run

Input (`factorial_test.tuga`):

```
funcao principal()
inicio
  escreve fact(3);
fim

funcao fact(n: inteiro): inteiro
inicio
  se (n igual 0) retorna 1;
  retorna n * fact(n-1);
fim
```

Output (after lexing, parsing, type checking, codegen, and execution):

```
*** Constant pool ***
*** Instructions ***
0: call 2
1: halt
2: iconst 3
3: call 6
4: iprint
5: ret 0
6: lload -1
7: iconst 0
8: ieq
9: jumpf 12
10: iconst 1
11: retval 1
...
*** VM output ***
6
```

</div>
