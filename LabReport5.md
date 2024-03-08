# Lab Report 5
## Part 1
* Hey everyone, I've been working on a Java program for my class project, and I'm encountering a weird issue. I've attached a screenshot of the relevant code snippet. 
The problem is that when I run the program, it's not displaying the expected output. Instead, it's giving me some unexpected values. 
I've tried debugging it myself, but I can't seem to figure out what's going wrong.
````
public class Calculator {
    public static void main(String[] args) {
        int result = addNumbers(5, 7);
        System.out.println("Result: " + result);
    }

    public static int addNumbers(int a, int b) {
        return a * b; // I expect the sum, but it's giving me a product
    }
}
````
* Response from TA:

Hey there! It looks like you might be facing an issue with your addNumbers method. The multiplication operation in the return statement seems to be causing the unexpected behavior.
Try checking that part of your code. Maybe a variable got changed unintentionally?
Also, could you run the program with a small adjustment? Before the System.out.println("Result: " + result); line, add a temporary print statement like this:
````
System.out.println("Debug: a=" + a + ", b=" + b);
````
* Response from student:
Thanks for the suggestion, TA! I added the debug print statement as you recommended, and I'm getting some interesting output. Here's the modified code:
````
public class Calculator {
    public static void main(String[] args) {
        int result = addNumbers(5, 7);
        System.out.println("Result: " + result);
    }

    public static int addNumbers(int a, int b) {
        System.out.println("Debug: a=" + a + ", b=" + b);
        return a * b; // Debug output shows correct values, but the result is still unexpected
    }
}
````
And here's the output:
````
Debug: a=5, b=7
Result: 35
````
Bug Explanation:

The bug in this scenario is in the addNumbers method, where the return statement is performing multiplication instead of addition. The student intended to add the numbers, but due to a mistake, the multiplication operation was used.

Setup Information:

1. File & Directory Structure:

* Directory: project
* Files:
* Calculator.java (Java code file)
* run.sh (Bash script to compile and run the Java program)

2. Contents of Each File Before Fixing the Bug:

* Calculator.java:
````
public class Calculator {
    public static void main(String[] args) {
        int result = addNumbers(5, 7);
        System.out.println("Result: " + result);
    }

    public static int addNumbers(int a, int b) {
        return a * b; // Incorrect, multiplication instead of addition
    }
}
````
* run.sh
````
#!/bin/bash
javac Calculator.java
java Calculator
````
3. Full Command Line to Trigger the Bug:
````
./run.sh
````
4. Description of What to Edit to Fix the Bug:

* In Calculator.java, update the addNumbers method to perform addition instead of multiplication:
````
public static int addNumbers(int a, int b) {
    return a + b; // Fix: perform addition
}
````
By making this correction, running the program should produce the correct sum instead of the unintended product.

## Part 2
One of the most interesting things I learned was editing code from the terminal using vim. I found it very useful.Actually, I feel like all the commands that I learned will be quite useful in the future.
