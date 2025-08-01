# 0x03. Shell, init files, variables and expansions

## 📚 Description

This project is part of the ALX System Engineering track. It focuses on shell variable handling, environment configuration, command expansion, arithmetic operations, and the use of aliases.

You'll learn about:
- Local vs global variables
- Shell initialization files
- Environment variables
- Variable expansion
- Command substitution
- Arithmetic using the shell
- Aliases and how to use them safely

---

## 🚀 How to Execute the Scripts

All scripts are written in Bash and tested on Ubuntu 20.04 LTS.

> Before running any script:
```bash
chmod +x <script_name>
````

> Then run with:

```bash
./<script_name>
```

> For scripts that affect environment variables (e.g. alias, path changes), use:

```bash
source <script_name>
# or
. <script_name>
```

---

## 📄 Scripts

| File                       | Description                                                                                |
| -------------------------- | ------------------------------------------------------------------------------------------ |
| `0-alias`                  | Creates an alias `ls` with the value `rm *`. Dangerous and for learning only.              |
| `1-hello_you`              | Prints "hello" followed by the current Linux user.                                         |
| `2-path`                   | Appends `/action` to the current `PATH` variable.                                          |
| `3-paths`                  | Counts the number of directories listed in the `PATH`.                                     |
| `4-global_variables`       | Displays all environment (global) variables.                                               |
| `5-local_variables`        | Displays all shell variables (local, environment, and functions).                          |
| `6-create_local_variable`  | Creates a local variable `BEST` with the value `School`.                                   |
| `7-create_global_variable` | Creates a global variable `BEST` with the value `School`.                                  |
| `8-true_knowledge`         | Adds `128` to the value of the `TRUEKNOWLEDGE` environment variable and prints the result. |
| `9-divide_and_rule`        | Divides the value of `POWER` by the value of `DIVIDE`, both environment variables.         |
| `10-love_exponent_breath`  | Raises `BREATH` to the power of `LOVE` (both from env vars) and prints the result.         |
| `11-binary_to_decimal`     | Converts a binary number stored in `BINARY` env var to its decimal equivalent.             |
| `12-combinations`          | Prints all possible 2-letter lowercase combinations except `oo`. One per line.             |
| `13-print_float`           | Prints the value of `NUM` environment variable as a float with 2 decimal places.           |

---

## 🔧 Example Usage

```bash
export TRUEKNOWLEDGE=1209
./8-true_knowledge   # Output: 1337

export POWER=42784
export DIVIDE=32
./9-divide_and_rule  # Output: 1337

export BINARY=10100111001
./11-binary_to_decimal  # Output: 1337
```

---

## ✅ Requirements

* Files must have exactly 2 lines (`wc -l` should output `2`)
* First line must be: `#!/bin/bash`
* No use of `awk`, `sed`, `bc`, `&&`, `||`, or `;`
* All scripts must be executable (`chmod +x script`)
* Files must end with a new line (`\n`)

---

## 📁 Project Structure

```
0x03-shell_variables_expansions/
├── 0-alias
├── 1-hello_you
├── 2-path
├── 3-paths
├── 4-global_variables
├── 5-local_variables
├── 6-create_local_variable
├── 7-create_global_variable
├── 8-true_knowledge
├── 9-divide_and_rule
├── 10-love_exponent_breath
├── 11-binary_to_decimal
├── 12-combinations
├── 13-print_float
└── README.md
```

---

## 🧠 Tips

* Test your scripts often with `source` or `./` depending on the task
* Use `env` and `printenv` to inspect global variables
* Use `set` to see both local and environment variables
* Don’t forget to remove extra lines or trailing whitespace

---


