# vmachine [![Build Status](https://travis-ci.org/faineance/vmachine.svg)](https://travis-ci.org/faineance/vmachine) [![Coverage Status](https://coveralls.io/repos/faineance/vmachine/badge.svg?branch=master)](https://coveralls.io/r/faineance/vmachine?branch=master)
A virtual machine 

## Building
You'll need a pretty up to date version of rust nightly.

```cargo build``` to build.

```cargo test``` to run tests.
## Usage
```cargo run repl``` to run repl.

```cargo run -- run example/factorial.vm``` to run factorial.vm.
## Instruction Set
#### Stack Operations
Where ``s1`` is the TOS and ``s2`` is the element on the stack below the TOS.

| Instruction | Usage     | Function                                                                  |
|-------------|-----------|---------------------------------------------------------------------------|
| psh         | psh ``n`` | push ``n`` onto the TOS                                   |
| pop         | pop       | pop the stack                                                 |
| add         | add       | replace top two elements of the stack with their sum (``s1 + s2``)       |
| sub         | sub       | replace top two elements of the stack with their difference (``s1 - s2``)|
| mul         | mul       | replace top two elements of the stack with their product (``s1 * s2``)   |
| div         | div       | replace top two elements of the stack with their product (``s1 / s2``)   |
#### Register Operations
| Instruction | Usage     | Function                                                                  |
|-------------|-----------|---------------------------------------------------------------------------|
| set         | set ``r``  ``n``  | set register ``r`` to value ``n``                                            |
| mov         | mov ``r1`` ``r2`` | move the value in register ``r1`` to register ``r2``                      |
| ldr         | ldr ``r`` | push value in ``r`` to TOS                    |
| str         | str ``r`` | pop and store TOS to ``r``                    |
#### Jump Operations
| Instruction | Usage     | Function                                                                  |
|-------------|-----------|---------------------------------------------------------------------------|
| jmp         | jmp ``label``     | jump to  ``label`` if not pop stack and continue                    |
| jz          | jz  ``label``     | jump if TOS is zero   ``label`` if not pop stack and continue   |
| jnz         | jnz ``label``     | jump if TOS is nonzero  ``label`` if not pop stack and continue |
#### Other Operations
| Instruction | Usage     | Function                                                                  |
|-------------|-----------|---------------------------------------------------------------------------|
| out         | out       | print top of stack                                                       |
| hlt         | hlt       | halt the program                                                          |
| nop         | nop       | do nothing                                                                |

## License
vmachine is licensed under the [MIT License](/LICENSE).
