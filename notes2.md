- A processor is an instruction interpreter

# Von-Neumann Machine

Program counter: a register that holds the address of the next instruction to be fetched and executed
Memory address register: a register that holds where to look in RAM
Memory data register: stores/loads info from memory (can be either an instruction or a number)
Decoder: takes code and decides which instruction to execute

1. Instruction Cycle
   1. Fetch: instruction is retrieved from memory
      1. Load PC into MAR
      1. Increment PC (this can happen in parallel)
      1. Load the proper piece of memory (indexed via MAR) into MDR
      1. Load MDR into IR
      1. Load IR.OP into the decoder
   2. Execute: instruction is executed

FETCH: 00 "hidden instruction"
LOAD: 
1. IR.address -> MAR
1. MEM[MAR] -> MDR
1. MDR -> A
1. 00 -> DECODER
ADD: 
TODO
STORE: 
TODO
HALT: immediately stops execution
