# Experiment 6: Shell Programming

## 1. Shell Loops

### For Loop

``` bash
for i in 1 2 3 4 5
do
    echo "Number: $i"
done
```

### While Loop

``` bash
i=1
while [ $i -le 5 ]
do
    echo "Count: $i"
    i=$((i+1))
done
```

### Until Loop

``` bash
i=1
until [ $i -gt 5 ]
do
    echo "Count: $i"
    i=$((i+1))
done
```

For loops iterate over items, while continues while condition is true,
until runs until condition becomes true.

------------------------------------------------------------------------

## 2. Loop Control

-   `break` → exit loop\
-   `continue` → skip current iteration

Example:

``` bash
for i in {1..5}
do
    if [ $i -eq 3 ]; then
        continue
    fi
    echo "Number: $i"
done
```

------------------------------------------------------------------------

## 3. I/O Redirection

-   `>` overwrite output\
-   `>>` append\
-   `<` redirected input\
-   `2>` redirect errors

Examples:

``` bash
echo "Hello" > file.txt
echo "World" >> file.txt
cat < file.txt
ls /notexist 2> error.log
```

------------------------------------------------------------------------

## 4. Shell Functions

``` bash
greet() {
    echo "Hello $1"
}
greet "User"
```

`$1` → first argument.

------------------------------------------------------------------------

## 5. Regular Expressions

Regular expressions are used for pattern matching.

Example:

``` bash
echo "hello123" | grep -E "[a-z]+[0-9]+"
```

------------------------------------------------------------------------

## 6. Script Debugging and Troubleshooting

Enable debugging:

``` bash
bash -x script.sh
```

Manual debug:

``` bash
echo "Debug: variable=$var"
```

------------------------------------------------------------------------

# Lab Exercises

## i. Palindrome Check

``` bash
#!/bin/bash
echo "Enter a number: "
read num
rev=0
temp=$num

while [ $temp -gt 0 ]
do
    digit=$((temp % 10))
    rev=$((rev * 10 + digit))
    temp=$((temp / 10))
done

if [ $num -eq $rev ]
then
    echo "$num is a palindrome."
else
    echo "$num is not a palindrome."
fi
```

------------------------------------------------------------------------

## ii. GCD and LCM

``` bash
#!/bin/bash
echo "Enter two numbers: "
read a b

x=$a
y=$b
while [ $y -ne 0 ]
do
    temp=$y
    y=$((x % y))
    x=$temp
done
gcd=$x
lcm=$(( (a * b) / gcd ))

echo "GCD: $gcd"
echo "LCM: $lcm"
```

------------------------------------------------------------------------

## iii. Sorting Numbers

``` bash
#!/bin/bash
echo "Enter numbers separated by space:"
read -a arr

echo "Ascending Order:"
printf "%s
" "${arr[@]}" | sort -n

echo "Descending Order:"
printf "%s
" "${arr[@]}" | sort -nr
```

------------------------------------------------------------------------

# Assignment

1.  Write a function to calculate factorial using a loop.\
2.  Script to count occurrences of a word in a file.\
3.  Generate first N Fibonacci numbers using while loop.\
4.  Validate email using regex.\
5.  Create script with error, run using `bash -x`, explain output.

------------------------------------------------------------------------

# Summary

-   Loops: for, while, until\
-   Loop control: break, continue\
-   Redirection: \>, \>\>, \<, 2\>\
-   Functions for modular code\
-   Regex for pattern matching\
-   Debugging with `bash -x`\
-   Lab covered palindrome, GCD/LCM, sorting
