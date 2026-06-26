# Unix Shell in C

A feature-rich **Unix Shell** implemented in **C**, built from scratch as part of an Operating Systems project. The shell supports process management, job control, piping, redirection, environment variable management, and several built-in Linux commands.

---

## Features

### Shell Interface

* Interactive shell prompt displaying:

  * Username
  * Hostname
  * Current Working Directory
* Persistent command history
* Multiple commands separated by `;`

### Built-in Commands

| Command              | Description                              |
| -------------------- | ---------------------------------------- |
| `cd`                 | Change current directory                 |
| `pwd`                | Print current working directory          |
| `echo`               | Display text                             |
| `ls [-a] [-l] [-al]` | List directory contents                  |
| `history`            | Display previously executed commands     |
| `pinfo`              | Display process information              |
| `setenv`             | Create or modify environment variables   |
| `unsetenv`           | Remove environment variables             |
| `jobs`               | List running background jobs             |
| `kjobs`              | Send a signal to a background job        |
| `fg`                 | Bring a background job to the foreground |
| `bg`                 | Resume a stopped background job          |
| `overkill`           | Terminate all background jobs            |
| `nightswatch`        | Monitor system information periodically  |
| `cronjob`            | Execute commands at fixed intervals      |
| `quit`               | Exit the shell                           |

---

## Process Management

* Foreground process execution
* Background process execution (`&`)
* Process creation using `fork()`
* Program execution using `execvp()`
* Job control implementation
* Process status tracking
* Foreground ↔ Background switching

---

## Input/Output Features

### Pipes

Supports Unix-style command piping.

Example:

```bash
ls -l | grep ".c" | wc -l
```

### Input/Output Redirection

Supports:

* Input Redirection (`<`)
* Output Redirection (`>`)
* Append Output (`>>`)

Examples:

```bash
cat < input.txt
ls > files.txt
echo Hello >> output.txt
```

---

## Signal Handling

Implemented handling for common Unix signals including:

* `SIGINT` (Ctrl+C)
* `SIGTSTP` (Ctrl+Z)

Ensures proper control over foreground processes without terminating the shell itself.

---

## Command History

* Stores previously executed commands
* Allows users to view command history
* Persistent across shell sessions using `history.txt`

---

## Project Structure

```text
.
├── commands
│   ├── bg.c
│   ├── cd.c
│   ├── commands.h
│   ├── echo.c
│   ├── env.c
│   ├── fg.c
│   ├── history.c
│   ├── jobs.c
│   ├── Kjobs.c
│   ├── ls.c
│   ├── nightswatch.c
│   ├── other_commands.c
│   ├── overkill.c
│   ├── pinfo.c
│   ├── Piped.c
│   ├── pwd.c
│   ├── quit.c
│   └── Redirection.c
├── history.txt
├── makefile
├── readme.md
├── shell.c
├── utils.c
└── utils.h
```

---

## Technologies Used

* C
* POSIX System Calls
* Linux System Programming
* GCC
* Makefile

---

## Build Instructions

Clone the repository:

```bash
git clone <repository-url>
cd <repository-name>
```

Compile the project:

```bash
make
```

Run the shell:

```bash
./shell
```

Clean the executable:

```bash
rm shell
```

---

## Sample Usage

```bash
$ pwd
/home/user

$ ls -l

$ echo Hello World

$ sleep 20 &

$ jobs

$ fg 1

$ cat file.txt | grep shell > output.txt

$ quit
```

---

## Concepts Demonstrated

* Operating Systems
* Process Creation (`fork`)
* Program Execution (`execvp`)
* Process Synchronization (`wait`, `waitpid`)
* Signal Handling
* Job Control
* Pipes
* File Descriptors
* I/O Redirection
* Environment Variables
* System Calls
* Shell Parsing

---

## Future Improvements

* Command auto-completion
* Alias support
* Shell scripting support
* Wildcard expansion
* Better parser for quoted strings
* Tab completion
* Syntax highlighting

---

## Author

**Anuj Tiwari**

If you found this project useful, consider giving it a ⭐ on GitHub.
