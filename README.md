# Text Formatter

A command-line tool written in Go that reads a text file, applies a series of transformations, and writes the formatted output into a new file.  
This project is part of a peer-review workflow, where students audit each other's code.

## Overview

The tool scans the text for special markers like `(hex)`, `(up)`, punctuation spacing issues, or grammar cases such as incorrect use of *a/an*, and automatically fixes them.  
It serves as a practical exercise in file handling, string manipulation, and clean Go coding practices.

## Features

### Number Conversion
- Converts hexadecimal values before `(hex)` into decimal.  
- Converts binary values before `(bin)` into decimal.

### Text Case Transformations
- `(up)` → Converts the previous word to UPPERCASE.  
- `(low)` → Converts the previous word to lowercase.  
- `(cap)` → Capitalizes the previous word.  
- Multi-word support: `(up, n)`, `(low, n)`, `(cap, n)` apply to the previous **n** words.

### Grammar & Punctuation Fixes
- Normalizes spacing around `. , ! ? : ;` so punctuation is attached to the previous word and spaced correctly after.  
- Handles grouped punctuation like `...` or `!?` as a single unit.  
- Fixes single quotes by attaching them directly to the enclosed words: `'word'` or `'multiple words'`.  
- Corrects the article `a` → `an` when the next word begins with a vowel or an **h**.

## Usage

```bash
go run . <input_file> <output_file>

