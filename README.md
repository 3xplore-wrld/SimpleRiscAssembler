# Simple RISC Assembler

A Python-based assembler for the Simple RISC instruction set architecture with a modern GUI interface.

## Features

- Modern graphical user interface with syntax highlighting
- Real-time assembly and error reporting
- Multiple output formats (binary and hexadecimal)
- Support for labels and comments
- Comprehensive error checking and validation

## Installation

1. Ensure you have Python 3.6+ installed.
2. Install required dependencies:
   ```bash
   pip install tkinter
   ```

## Usage

Run the GUI application:
```bash
python GUI.py
```

Use the toolbar buttons to:
- Create a new file
- Open an existing assembly file
- Save the current file
- Assemble the code

## Assembly Language Syntax

### Comments
- Single-line comments start with `@` or `#`
- Multi-line comments are enclosed in `/* */`

### Labels
- Must start with a letter or underscore
- Can contain letters, numbers, and underscores
- End with a colon (`:`)

**Example:**
```assembly
loop:
    add r1, r2, r3
```

### Registers
- General-purpose registers: `r0` to `r15`
- Special registers: `sp` (stack pointer), `ra` (return address)

### Instructions

#### Register Format (3-address ALU instructions):
```assembly
add rd, rs1, rs2
sub rd, rs1, rs2
mul rd, rs1, rs2
div rd, rs1, rs2
mod rd, rs1, rs2
and rd, rs1, rs2
or rd, rs1, rs2
lsl rd, rs1, rs2
lsr rd, rs1, rs2
asr rd, rs1, rs2
```

#### Two-Address Instructions:
```assembly
cmp rs1, rs2
not rd, rs1
mov rd, imm
```

#### Branch Instructions:
```assembly
nop
ret
beq label
bgt label
b label
call label
```

#### Memory Operations:
```assembly
ld rd, imm[rs1]
st rs2, imm[rs1]
```

### Immediate Values
- Signed immediate range: `-32768 to 32767`
- Unsigned immediate range: `0 to 65535`
- Memory offset range: `-32768 to 32767`

## Error Handling
The assembler provides detailed error messages for:
- Invalid register numbers
- Out-of-range immediate values
- Invalid memory offsets
- Undefined labels
- Syntax errors
- Invalid instruction formats

## Output Formats

### Binary Output:
- Shows memory address and 32-bit binary instruction
- Format: `address: binary_instruction`

### Hexadecimal Output:
- Shows assembled instructions in hexadecimal format
- One instruction per line

## Contributing
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

