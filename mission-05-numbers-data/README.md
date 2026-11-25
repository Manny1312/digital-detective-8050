# Mission 5 — Numbers & Data Representation

## Task
Explore how computers store numbers and text using binary, hexadecimal, and ASCII/Unicode encoding, and build an interactive Python converter script (`number_converter.py`).

## Work Completed

### Number Base Conversions
Converted sample decimal integers into Binary (Base 2), Octal (Base 8), and Hexadecimal (Base 16) to verify manual calculations against Python output:

| Decimal (Base 10) | Binary (Base 2) | 8-Bit Binary | Hexadecimal (Base 16) |
| :--- | :--- | :--- | :--- |
| `10` | `1010` | `00001010` | `0x0A` |
| `42` | `101010` | `00101010` | `0x2A` |
| `128` | `10000000` | `10000000` | `0x80` |
| `255` | `11111111` | `11111111` | `0xFF` |

### Character Encoding (ASCII / Unicode)
Inspected how plain text characters map to integer code points and binary bytes using Python's `ord()` function:

| Character | Decimal Code | Binary (8-Bit) | Hexadecimal |
| :--- | :--- | :--- | :--- |
| `'H'` | `72` | `01001000` | `0x48` |
| `'i'` | `105` | `01101001` | `0x69` |
| `'0'` | `48` | `00110000` | `0x30` |
| `' '` (Space) | `32` | `00100000` | `0x20` |

### Running `number_converter.py`
Tested the script in the terminal with sample inputs (`42` and `Hi`):

```text
\$ python3 number_converter.py
Enter a positive integer (e.g., 42): 42

--- Number System Conversion for 42 ---
Decimal (Base 10)     : 42
Binary (Base 2)       : 101010 (8-bit: 00101010)
Octal (Base 8)        : 52
Hexadecimal (Base 16) : 0x2A

Enter a short word to see its binary/ASCII breakdown (e.g., Hi): Hi

--- Character Encoding Trace for 'Hi' ---
'H' -> ASCII/Unicode: 72   | Binary: 01001000 | Hex: 0x48
'i' -> ASCII/Unicode: 105  | Binary: 01101001 | Hex: 0x69
```

## Commands / Tools Used
* **VS Code** to write `number_converter.py` and format `README.md`.
* **Python 3** (`bin()`, `oct()`, `hex()`, `ord()`, and string formatting) for base and character conversions.
* **Git** (`git add`, `git commit`, `git push`) to save and upload Mission 5 separately.

## My Understanding
At the hardware level, computers only store electrical states (`0`s and `1`s). Number bases like hexadecimal are simply compact shorthand for reading long binary strings (1 hex digit = 4 bits), and standards like ASCII and UTF-8 give every text character a consistent numeric code so any device displays the exact same text.

## Difficulties Faced
Python's built-in `bin()` and `hex()` functions include `0b` and `0x` prefixes by default, and binary strings drop leading zeros.

## How I Resolved Them
Used string slicing (`[2:]`) to strip default prefixes when needed and Python format specifiers (`{num:08b}` and `{code:02X}`) to display padded 8-bit binary and uppercase hex cleanly.

## Evidence / Files
* `mission-05-numbers-data/number_converter.py`
* `mission-05-numbers-data/README.md`

## Commit Details
* **Commit Message**: `Complete numbers and data mission with number_converter.py`