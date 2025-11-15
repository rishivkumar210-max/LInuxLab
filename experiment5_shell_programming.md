# Experiment 5: Shell Programming

## Slide 1: Experiment 5 – Shell Programming

---

## Slide 2: Lab Tasks
A structured set of shell scripting tasks demonstrating decision-making, loops, and arithmetic operations in Bash.

---

## Slide 3: Summary
- **Shebang** (`#!/bin/bash`) specifies the shell interpreter.
- **Variables:** User-defined (`name="abc"`) and system variables (`$HOME`).
- **Input/Output:** `read`, `echo`.
- **Arithmetic:** `$((...))` for calculations.
- **Conditionals:** `if-then-else`, operators (`-eq`, `-ge`, etc.).
- **Loops:** `for`, `while`.
- **Positional Parameters:** `$1`, `$2`, `$#`, `$@`.
- **Arrays:** `arr=(10 20 30)`.
- Practical scripts include: Prime check, Digit sum, Armstrong number.

---

## Slide 4: Tasks to be Performed
Hands-on tasks based on core scripting concepts.

---

## Task 1: First Script
**Goal:** Print "Hello, World!"  
**Hint:** Use `echo` with shebang.  
**Output:**
```
Hello, World!
```

---

## Task 2: Personalized Greeting
**Goal:** Take user name as input and greet them.  
**Hint:** Use `read` and variable substitution.  
**Example:**
```
Enter your name: Rahul
Hello, Rahul! Welcome to Shell Scripting.
```

---

## Task 3: Arithmetic Operations
**Goal:** Input 2 numbers and perform basic arithmetic.

**Example Input:** 12 and 4

**Output:**
```
Addition: 16
Subtraction: 8
Multiplication: 48
Division: 3
```

---

## Task 4: Voting Eligibility
**Goal:** Check if age ≥ 18.

**Test Cases:**
- Input: 20 → Eligible
- Input: 15 → Not Eligible

---

## Experiment 5 (Decision Making)

### Task 5: Prime Number Check
Loop from 2 to `num/2` and check divisibility.

**Test Cases:**
- 7 → Prime
- 10 → Not Prime

**Code:**
```bash
#!/bin/bash
echo "Enter a number: "
read num
flag=0

for ((i=2; i<=num/2; i++))
do
    if [ $((num % i)) -eq 0 ]
    then
        flag=1
        break
    fi
done

if [ $flag -eq 0 ]
then
    echo "$num is a prime number."
else
    echo "$num is not a prime number."
fi
```

---

### Task 6: Sum of Digits
Extract digits using `% 10` and reduce using `/ 10`.

**Test Case:** 1234 → Output: 10

**Code:**
```bash
#!/bin/bash
echo "Enter a number: "
read num
sum=0

while [ $num -gt 0 ]
do
    digit=$((num % 10))
    sum=$((sum + digit))
    num=$((num / 10))
done

echo "Sum of digits: $sum"
```

---

### Task 7: Armstrong Number Check
An **Armstrong number** is equal to the sum of the digits raised to the power of number of digits.

**Test Cases:**
- 153 → Armstrong
- 123 → Not Armstrong

**Code:**
```bash
#!/bin/bash
echo "Enter a number: "
read num
temp=$num
n=${#num}
sum=0

while [ $temp -gt 0 ]
do
    digit=$((temp % 10))
    sum=$((sum + digit**n))
    temp=$((temp / 10))
done

if [ $sum -eq $num ]
then
    echo "$num is an Armstrong number."
else
    echo "$num is not an Armstrong number."
fi
```

---

## Evaluation Hints
- **Change Inputs:** Try different numbers and boundary cases.
- **Predict Outputs:** Guess before running.
- **Modify Scripts:** Add more conditions, remainders, etc.
- **Use Command Line Arguments:**
```
./script.sh 12 5
```
Use `$1`, `$2` inside script.

---
