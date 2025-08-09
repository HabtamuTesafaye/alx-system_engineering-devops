# Project Overview

Welcome to this repository, which contains projects focused on **Shell Scripting** and **Web Infrastructure Design**. Each directory is dedicated to a specific topic, providing scripts, diagrams, and documentation to enhance your understanding of system engineering and DevOps concepts.

---

## 📂 Directory Structure

### 1. `0x03-shell_variables_expansions/`
This directory contains **Bash scripts** that demonstrate the use of shell variables, environment configuration, command expansion, arithmetic operations, and more.

#### 📄 Key Files:
| File                          | Description                                                                 |
| ----------------------------- | --------------------------------------------------------------------------- |
| `0-alias`                     | Creates an alias `ls` with the value `rm *`. **For learning purposes only.** |
| `1-hello_you`                 | Prints "hello" followed by the current Linux user.                          |
| `2-path`                      | Appends `/action` to the current `PATH` variable.                           |
| `3-paths`                     | Counts the number of directories listed in the `PATH`.                      |
| `4-global_variables`          | Displays all environment (global) variables.                                |
| `5-local_variables`           | Displays all shell variables (local, environment, and functions).           |
| `6-create_local_variable`     | Creates a local variable `BEST` with the value `School`.                    |
| `7-create_global_variable`    | Creates a global variable `BEST` with the value `School`.                   |
| `8-true_knowledge`            | Adds `128` to the value of the `TRUEKNOWLEDGE` environment variable.        |
| `9-divide_and_rule`           | Divides the value of `POWER` by the value of `DIVIDE`.                      |
| `10-love_exponent_breath`     | Raises `BREATH` to the power of `LOVE` and prints the result.               |
| `11-binary_to_decimal`        | Converts a binary number in `BINARY` env var to its decimal equivalent.     |
| `12-combinations`             | Prints all possible 2-letter lowercase combinations except `oo`.            |
| `13-print_float`              | Prints the value of `NUM` as a float with 2 decimal places.                 |
| `100-decimal_to_hexadecimal`  | Converts a decimal number in `DECIMAL` env var to hexadecimal.              |
| `101-rot13`                   | Encodes input using the ROT13 cipher.                                       |
| `102-odd`                     | Prints every other line of input.                                           |
| `103-water_and_stir`          | Performs a custom base conversion and transformation.                       |
| `README.md`                   | Documentation for this directory.                                           |

---

### 2. `0x09-web_infrastructure_design/`
This directory focuses on **web infrastructure design**, providing blueprints and documentation for building scalable, secure, and monitored web systems.

#### 📄 Key Files:
| File                                   | Description                                                                 |
| -------------------------------------- | --------------------------------------------------------------------------- |
| `0-simple_web_stack`                   | Diagram and explanation of a simple web stack with one server.              |
| `1-distributed_web_infrastructure`     | Blueprint for a distributed web infrastructure with load balancing.         |
| `2-secured_and_monitored_web_infrastructure` | Blueprint for a secured and monitored web infrastructure.            |
| `README.md`                            | Documentation for this directory, including detailed explanations of tasks. |

---

## 🚀 How to Use

### For Shell Scripts:
1. Ensure the script is executable:
   ```bash
   chmod +x <script_name>