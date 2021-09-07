# Virtual Machines as Instruction Interpreters

- A virtual machine is a program that implements an ISA (real or not)
  - It is not hardware
- The P-code machine is a software virtual machine that implements the ISA
  - Ex: Pascal, Java
- The PM/0 instruction set architecture has 3 components per instruction:
  1. OP: the opcode
  1. L: the lexicographical level
  1. M: different meaning based on opcode (could be value, address)
- 2 parts:
  1. Stack
  1. Text (program instructions and compile time variables)
- 4 registers:
  1. bp: base pointer points to current base of activation record
  1. sp: stack pointer points to the top of the stack
  1. pc: program counter
  1. ir: instruction register for next instruction to be placed in
- What is the activation record?
  - A data structure that contains information that controls subroutine linkage
  - Space for information about a function:
    1. Parameters
    1. Local Variables
    1. Return Address: stored program counter from previous stack frame
    1. Dynamic Link: stored base pointer from previous stack frame
    1. Static Link: pointer to stored stack frame of statically enclosing function (used for closures)
    1. Functional Value: return value of function

# P-machine

- Fetch cycle
  1. Copy `text[pc]` to `ir`
  1. `pc <- pc + 1`
- Execute Cycle
  1. Read from `ir.op` to determine opcode and `ir.m` to do proper behavior
- (see the ISA in slides)
