# Experiment 4: Shell Programming

## Theory Concepts

### **BASH (Bourne Again SHell)**

-   Default shell in most Linux distributions.
-   Interprets commands entered in the terminal or written in script
    files.

### **Basics of Shell Scripting**

A shell script is a plain text file containing commands.

By convention, scripts start with a **shebang**:

``` bash
#!/bin/bash
```

This tells the system to execute the script using **bash**.

### **Types of Shell**

Common shells include: - **sh** (Bourne Shell) - **bash** (Bourne Again
Shell) - **zsh** - **ksh** - **csh**

To check your current shell:

``` bash
echo $SHELL
```

### **Shell Variables**

#### **User-defined variables**

``` bash
name="Prateek"
echo "Hello $name"
```

#### **System variables (predefined, always uppercase)**

``` bash
echo $HOME
echo $USER
echo $PWD
```

### **Keywords & Operators**

-   **Keywords:** `if`, `then`, `else`, `fi`, `for`, `while`
-   **Operators:**
    -   **Arithmetic:** `+` `-` `*` `/` `%`
    -   **Comparison:** `-eq` `-ne` `-lt` `-le` `-gt` `-ge`

### **Positional Parameters**

Used to take arguments while executing a script:

``` bash
./script.sh arg1 arg2
```

-   `$0` → script name
-   `$1` → first argument
-   `$2` → second argument

------------------------------------------------------------------------

## **Lab Tasks**

### **i. Hello World Script**

``` bash
#!/bin/bash
echo "Hello, World!"
```

### **ii. Personalized Greeting**

``` bash
#!/bin/bash
echo "Enter your name: "
read name     # 'read' takes user input
echo "Hello, $name! Welcome to Shell Scripting."
```

### **iii. Arithmetic Operations**

``` bash
#!/bin/bash
echo "Enter first number: "
read num1
echo "Enter second number: "
read num2

echo "Addition: $((num1 + num2))"
echo "Subtraction: $((num1 - num2))"
echo "Multiplication: $((num1 * num2))"
echo "Division: $((num1 / num2))"
```

### **iv. Voting Eligibility**

``` bash
#!/bin/bash
echo "Enter your age: "
read age

if [ $age -ge 18 ]
then
    echo "You are eligible to vote."
else
    echo "Sorry, you are not eligible to vote."
fi
```
