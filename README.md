# SIC/XE Assembler

A two-pass SIC/XE assembler implemented in Python from scratch, generating **100% accurate object code** with full Location Counter, Symbol Table, and HTE Record output. Applies low-level compiler design and computer architecture principles to translate SIC/XE assembly source into standard object code format.

---

## ⚙️ What It Does

- Parses SIC/XE assembly source files and symbol/literal tables
- Performs two-pass assembly: resolves symbols in Pass 1, generates object code in Pass 2
- Outputs correctly structured Header (H), Text (T), and End (E) records
- Handles all SIC/XE addressing modes and instruction formats

---

## 🧩 Components

### Input Files

**Instructions File**
Contains the SIC/XE assembly source — Header (`H`), Text (`T`), and End (`E`) records. Each line specifies opcodes, operand addresses, and data in structured format.

**Table File**
Provides the symbol table and literal table with resolved addresses and object codes. Used to correlate all symbolic references during code generation.

### Processing Pipeline

**Table Parsing**
Extracts addresses and object codes from the table file to resolve all symbolic references before code generation begins.

**Instruction Parsing**
Reads and decodes each record type — Header, Text, End — converting symbolic operands into machine-readable addresses using the resolved symbol table.

### Output: Object Code Records

| Record | Purpose |
|--------|---------|
| **H (Header)** | Program name, starting address, total object code length |
| **T (Text)** | Starting address, segment length, and machine code for each program segment |
| **E (End)** | Execution start address; marks the end of the object program |

---

## 🛠️ Tech Stack

- **Language:** Python
- **Concepts:** Two-pass assembly, Location Counter, Symbol Table, SIC/XE instruction formats, HTE record generation
