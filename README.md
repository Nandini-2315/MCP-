# ⚡ MCP-Powered Python Tool Integration Framework

**Name:** Vallapu Nandini  
**Roll No:** 261FB04046

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-blue?logo=python" />
  <img src="https://img.shields.io/badge/MCP-Python%20SDK-purple" />
  <img src="https://img.shields.io/badge/AI-GitHub%20Copilot-black?logo=githubcopilot" />
  <img src="https://img.shields.io/badge/Transport-stdio-green" />
</p>

### Building and Integrating Custom AI-Accessible Tools Using the Model Context Protocol

A Python-based MCP server that exposes seven custom tools for mathematical computation, number analysis, and personalized greeting generation. Integrated with VS Code and GitHub Copilot Agent mode to demonstrate structured AI-to-tool communication.

## 📌 Project Overview

The Model Context Protocol (MCP) is a standard that allows AI applications to communicate with external tools and services.

In this project, a Python MCP server named **HelloMCP** is created using the MCP Python SDK. It exposes multiple Python functions as tools, allowing an MCP-compatible AI client to execute them.

### 🎯 Project Objectives

- Understand the basics of Model Context Protocol (MCP).
- Create an MCP server using Python.
- Register Python functions as MCP tools.
- Perform mathematical operations through MCP tools.
- Connect the MCP server with VS Code and GitHub Copilot.
- Learn how AI applications interact with external tools.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.12.7 | Programming language |
| MCP Python SDK 2.x | Creating the MCP server |
| VS Code | Development environment |
| GitHub Copilot | AI client for testing MCP tools |
| MCP stdio | Communication transport |
| Git & GitHub | Version control and project hosting |

## ⚙️ Features

This project implements seven MCP tools.

### 1. get_greeting(name)

Returns a personalized greeting message for a student.

**Example:**
```python
get_greeting("Students")
```

**Output:**
```text
Hello, Students! Your first MCP tool works.
```

### 2. add_numbers(a, b)

Adds two integers and returns their sum.

**Example:**
```python
add_numbers(10, 20)
```

**Output:**
```text
30
```

### 3. multiply_numbers(a, b)

Multiplies two integers and returns the result.

**Example:**
```python
multiply_numbers(5, 4)
```

**Output:**
```text
20
```

### 4. subtract_numbers(a, b)

Subtracts the second number from the first number.

**Example:**
```python
subtract_numbers(20, 10)
```

**Output:**
```text
10
```

### 5. divide_numbers(a, b)

Divides the first number by the second number. It also handles division by zero by raising a ValueError.

**Example:**
```python
divide_numbers(20, 5)
```

**Output:**
```text
4.0
```

### 6. check_prime(number)

Checks whether a given number is prime or not.

**Example:**
```python
check_prime(7)
```

**Output:**
```text
7 is a prime number.
```

### 7. check_even_odd(number)

Checks whether a given integer is even or odd.

**Example:**
```python
check_even_odd(8)
```

**Output:**
```text
8 is an even number.
```

## 📂 Project Structure

```text
HelloMCP/
│
├── server.py
│
├── requirements.txt
│
├── .vscode/
│   └── mcp.json
│
└── .gitignore
```

**File descriptions:**

- `server.py` – Contains the MCP server implementation and all seven tools.
- `requirements.txt` – Contains the Python package dependencies.
- `.vscode/mcp.json` – Configures the MCP server in VS Code.
- `.gitignore` – Excludes unnecessary files and virtual environment folders from GitHub.

## 🚀 Installation and Setup

### Step 1: Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/HelloMCP.git
```

Navigate into the project directory:

```bash
cd HelloMCP
```

### Step 2: Create a virtual environment

```bash
py -3.12 -m venv .venv
```

Activate the virtual environment:

**Windows:**
```bash
.venv\Scripts\activate
```

### Step 3: Install dependencies

```bash
python -m pip install "mcp[cli]" --default-timeout=120
```

### Step 4: Run the MCP server

```bash
python server.py
```

The server starts and waits for connections from an MCP-compatible client.

**Note:** The server uses standard input/output (stdio) communication, so it is intended to be launched by an MCP client rather than used as a standalone HTTP service.

## 🔗 VS Code MCP Configuration

Create a folder named `.vscode` in the project directory and add a file named `mcp.json`.

Add the following configuration:

```json
{
  "servers": {
    "helloMcp": {
      "type": "stdio",
      "command": "${workspaceFolder}\\.venv\\Scripts\\python.exe",
      "args": ["server.py"]
    }
  }
}
```

This configuration connects the Python MCP server to VS Code using the Python interpreter inside the virtual environment.

### Starting the MCP Server in VS Code

1. Open the project in VS Code.
2. Open GitHub Copilot Chat.
3. Switch to Agent mode.
4. Press `Ctrl + Shift + P`.
5. Search for `MCP: List Servers`.
6. Select `helloMcp`.
7. Start or restart the server.
8. Verify that the server is running and its tools are discovered.

## 🧪 Testing the MCP Tools

You can test the tools through GitHub Copilot Agent mode.

**Example prompts:**

```text
Use the get_greeting tool with the name Students.
```

```text
Use the add_numbers tool with a = 10 and b = 20.
```

```text
Use the multiply_numbers tool with a = 5 and b = 4.
```

```text
Use the subtract_numbers tool with a = 20 and b = 10.
```

```text
Use the divide_numbers tool with a = 20 and b = 5.
```

```text
Use the check_prime tool with number = 7.
```

```text
Use the check_even_odd tool with number = 8.
```

## 📊 Expected Results

| MCP Tool | Input | Expected Output |
|---|---|---|
| get_greeting | Students | Hello, Students! Your first MCP tool works. |
| add_numbers | 10, 20 | 30 |
| multiply_numbers | 5, 4 | 20 |
| subtract_numbers | 20, 10 | 10 |
| divide_numbers | 20, 5 | 4.0 |
| check_prime | 7 | Prime number |
| check_even_odd | 8 | Even number |

## ⚠️ Error Handling

The project includes basic error handling for division by zero.

For example:

```python
divide_numbers(10, 0)
```

Raises:

```text
ValueError: Cannot divide by zero.
```

The prime number checker also handles numbers less than or equal to 1 as non-prime numbers.

## 🌟 Learning Outcomes

Through this project, I learned:

- How to create an MCP server using Python.
- How to register Python functions using the `@mcp.tool()` decorator.
- How MCP tools expose functionality to AI applications.
- How to configure MCP servers in VS Code.
- How to use GitHub Copilot Agent mode to interact with custom MCP tools.
- How to perform mathematical operations through MCP tools.

## 🧠 Technical Highlights

This project demonstrates the following MCP concepts and implementation details:

- **MCP Server Initialization:** Creates a server instance using the Python MCP SDK.
- **Tool Registration:** Exposes Python functions as discoverable MCP tools using the `@mcp.tool()` decorator.
- **Function-Based Tool Execution:** Each registered tool performs a specific operation and returns its result to the MCP client.
- **Type Annotations:** Uses Python type hints to define tool input and output types.
- **Input Validation:** Handles division-by-zero errors and correctly identifies non-prime numbers.
- **Standard I/O Transport:** Uses the stdio communication mechanism to connect the MCP server with compatible AI clients.
- **AI Client Integration:** Configures the server in VS Code and enables interaction through GitHub Copilot Agent mode.

## 📌 Conclusion

The **HelloMCP – Python MCP Server** project demonstrates the practical implementation of the Model Context Protocol using Python.

By leveraging the MCP Python SDK, this project successfully defines and exposes seven custom tools through a single MCP server. These tools cover personalized greeting generation, arithmetic operations, prime number identification, and even-or-odd checking.

The implementation illustrates how traditional Python functions can be transformed into accessible tools for AI applications through the MCP architecture.

It also demonstrates the integration workflow involving Python, virtual environments, VS Code, MCP server configuration, stdio communication, and GitHub Copilot Agent mode.

Overall, this project provides a practical understanding of how MCP enables AI applications to interact with external functionality through structured, tool-based communication.

**Key Achievement:** Designed and implemented a Python MCP server with seven registered tools, demonstrating tool discovery, function execution, and AI-client integration.

## 👨‍💻 Author

Vallapu Nandini

- GitHub: https://github.com/Nandini-2315
- Project: Python MCP Server – HelloMCP

---

⭐ If you find this project useful, consider giving the repository a star!

**Technologies:** Python · MCP SDK · VS Code · GitHub Copilot · Model Context Protocol
