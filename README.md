---

# Foothread Multithreading Tree Computation Project

## Overview

This project is a simple multithreaded application implemented in C, utilizing a custom threading library (`foothread`). The project involves creating and managing threads that operate on a tree structure, where each node is handled by a separate thread. The application computes the sum of user-provided integers at the leaf nodes and propagates these sums up the tree to determine a total sum at the root node.

## Features

- **Custom Threading Library**: Implements basic thread management, mutexes for mutual exclusion, and barriers for synchronization using Linux system calls.
- **Tree Structure Computation**: Each node in a tree is processed by a separate thread, either by gathering user input (leaf nodes) or computing partial sums (internal nodes).
- **Random Tree Generation**: Generates a random tree structure to serve as input for the computation.
- **Build Automation**: Utilizes a `Makefile` to automate the compilation, linking, and execution processes.

## Project Structure

- `foothread.h` - Header file declaring the custom threading functions and data structures.
- `foothread.c` - Implementation of the `foothread` library, providing threading, mutex, and barrier functionalities.
- `computesum.c` - Main application file that initializes the tree structure, creates threads, and computes the sum at the root node.
- `gentree.c` - Generates a random tree structure and outputs it to `tree.txt`.
- `Makefile` - Automates the compilation of the library and the application, tree generation, and cleanup.

## Getting Started

### Prerequisites

- GCC (GNU Compiler Collection)
- Make

### Compilation and Execution

1. **Compile the Project**
   ```bash
   make app
   ```
   This command compiles the `foothread` library and the `computesum` application.

2. **Run the Application**
   ```bash
   make run
   ```
   This command runs the `computesum` application using an existing `tree.txt` file.

3. **Generate a New Tree and Run the Application**
   ```bash
   make newrun
   ```
   This command generates a new random tree and then runs the `computesum` application.

4. **Clean Up**
   ```bash
   make clean
   ```
   This command removes all compiled files and the generated `tree.txt`.

### Tree Structure

The tree structure is represented in a text file (`tree.txt`), which contains the following:

- The first line contains the number of nodes in the tree.
- Each subsequent line represents a node and its parent in the format: `node_id parent_id`.

### User Interaction

When running the application, you will be prompted to enter a positive integer for each leaf node in the tree. The program will then calculate the sum at each internal node based on the values of its children and propagate this sum up the tree.

### Example

Given the following `tree.txt`:

```
5
0 0
1 0
2 1
3 1
4 2
```

The program will prompt the user for input at nodes `3` and `4` (the leaf nodes). The sums will be propagated up the tree, and the total sum will be displayed at the root node (`0`).

## Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request with your changes. Issues and bug reports are welcome!

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments

- **Linux System Programming**: The project is built on top of Linux system calls and IPC mechanisms.
- **Multithreading Concepts**: Basic principles of threading and synchronization are applied in this project.

---
