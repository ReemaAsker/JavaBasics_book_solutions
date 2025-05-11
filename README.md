# 📘 Java Book – Exercises & Solutions (Eng.Reema Ali Asker)

This document provides all the exercises from the book along with their solutions, grouped by topic and includes example outputs.

---

## 🗂 Table of Contents
- [✅ Basic Tasks](#-basic-tasks)
- [🔤 Input, Variables & Parsing](#-input-variables--parsing)
- [🔧 Operations](#-operations)
- [🔁 Loops](#-loops)
- [📦 Arrays](#-arrays)
- [🔧 Methods](#-methods)
- [🔁 Recursion](#-recursion)
- [🛍 Final Project (Product Management System)](#-final-project-product-management-system)

---

## ✅ Basic Tasks

### 📝 Exercise
Create a class FirstLecture, add a main method 

### ✅ Solution
```java
public class FirstLecture {
    public static void main(String[] args) {
   
    }
}
```

### 📝 Exercise
Write suitable import statements to use Arrays and JOptionPane.

### ✅ Solution
```java
import java.util.Arrays;
import javax.swing.JOptionPane;
}
```

### 📝 Exercise
what is the Suitable type for storing the following values :
(10 : ------------------ , -200 :------------------ , 57.6879: --------------- ,2,147,483,699 : ‘$’:------------“My name is Reema”: ------------------, 
the value of the answer "Are you a student? ------------------     ) 

### ✅ Solution

1. **10**  
   - **Suitable type**: `byte`  
   - **Memory usage**: 1 byte  
   - **Reasoning**: The value `10` fits within the `byte` range (-128 to 127), making it the most memory-efficient choice.  
   - Example: `byte num = 10;`

2. **-200**  
   - **Suitable type**: `short`  
   - **Memory usage**: 2 bytes  
   - **Reasoning**: The value `-200` fits within the `short` range (-32,768 to 32,767), making `short` more suitable than `int`.  
   - Example: `short num = -200;`

3. **57.6879**  
   - **Suitable type**: `float`  
   - **Memory usage**: 4 bytes  
   - **Reasoning**: Since the value is a floating-point number, `float` is the appropriate choice for less precision and reduced memory consumption.  
   - Example: `float num = 57.6879f;` (Note the `f` suffix for `float`)

4. **2,147,483,699**  
   - **Suitable type**: `long`  
   - **Memory usage**: 8 bytes  
   - **Reasoning**: The value exceeds the `int` range, so `long` is required to store this large number.  
   - Example: `long num = 2_147_483_699L;` (Note the `L` suffix for `long`)

5. **'$'**  
   - **Suitable type**: `char`  
   - **Memory usage**: 2 bytes  
   - **Reasoning**: A single character can be efficiently stored using the `char` type, which is 2 bytes.  
   - Example: `char symbol = '$';`

6. **"My name is Reema"**  
   - **Suitable type**: `String`  
   - **Memory usage**: Depends on string length (2 bytes per character in UTF-16 encoding)  
   - **Reasoning**: A sequence of characters is best stored as a `String`.  
   - Example: `String name = "My name is Reema";`

7. **"Are you a student?"**  
   - **Suitable type**: `String`  
   - **Memory usage**: Depends on string length (2 bytes per character in UTF-16 encoding)  
   - **Reasoning**: The question should be stored as a `String`.  
   - Example: `String question = "Are you a student?";`

### Summary of Memory Usage:

| Value                    | Suitable Type | Memory Usage |
|--------------------------|---------------|--------------|
| **10**                   | `byte`        | 1 byte       |
| **-200**                  | `short`       | 2 bytes      |
| **57.6879**               | `float`       | 4 bytes      |
| **2,147,483,699**         | `long`        | 8 bytes      |
| **'$'**                   | `char`        | 2 bytes      |
| **"My name is Reema"**    | `String`      | Variable (2 bytes per character) |
| **"Are you a student?"**  | `String`      | Variable (2 bytes per character) |
---
### 📝 Exercise
How can we store Reema Asker in Java?
How can we store 1999.6 with best data type in Java?
How can we store true in Java?
### ✅ Solution
1. **Storing "Reema Asker" in Java:**
   - **Suitable type**: `String`
   - **Reasoning**: A sequence of characters is best stored as a `String` in Java.
   - **Example**:
     ```java
     String name = "Reema Asker";
     ```

2. **Storing 1999.6 in Java:**
   - **Suitable type**: `double`
   - **Reasoning**: For storing decimal values with the best precision, `double` is typically the best choice as it uses 8 bytes and provides more precision than `float`.
   - **Example**:
     ```java
     double value = 1999.6;
     ```

3. **Storing `true` in Java:**
   - **Suitable type**: `boolean`
   - **Reasoning**: The `boolean` type is used for binary values such as `true` or `false`.
   - **Example**:
     ```java
     boolean isTrue = true;
     ```

### Summary:

| Value         | Suitable Type | Example Code                         |
|---------------|---------------|--------------------------------------|
| "Reema Asker" | `String`      | `String name = "Reema Asker";`       |
| 1999.6        | `double`      | `double value = 1999.6;`            |
| true          | `boolean`     | `boolean isTrue = true;`             |
---
### 🔤 Input, Variables & Parsing

### 📝 Exercise
Make a simple program that has the following:
1. print your name
2. create a variable called my age with string data type and put your age .
3. convert the age as number (int)
4. print your age with added 5 years.

### ✅ Solution
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("My name is Reema");
        String myAge = "23";
        int age = Integer.parseInt(myAge);
        System.out.println("My age after 5 years: " + (age + 5));
    }
}
```
📤 **Output:**
```
My name is Reema
My age after 5 years: 28
```

---

## 🔁 Loops

### 1. Print numbers from 1 to 10
```java
for (int i = 1; i <= 10; i++) {
    System.out.println(i);
}
```
📤 **Output:**
```
1
2
3
4
5
6
7
8
9
10
```

### 2. Sum numbers from 1 to 10
```java
int sum = 0;
for (int i = 1; i <= 10; i++) {
    sum += i;
}
System.out.println("Sum = " + sum);
```
📤 **Output:**
```
Sum = 55
```

### 3. Sum all positive numbers until a negative is entered
```java
Scanner sc = new Scanner(System.in);
int sum = 0, num;
do {
    System.out.print("Enter number: ");
    num = sc.nextInt();
    if (num > 0) sum += num;
} while (num >= 0);
System.out.println("Sum = " + sum);
```
📤 **Output (Example):**
```
Enter number: 4
Enter number: 10
Enter number: -1
Sum = 14
```

---
### 🔧 Operations

1. **Initialization:**
     ```java
      int num = 25;
     ```
2. **Decrement:**
     ```java
      num--;
     ```
  The num-- operation reduces the value of num by 1. So, now num = 24.
 3. **Add 5:**
 ```java
   num += 5;
 ```
4. **Subtract 2:**
 ```java
   num -= 2;
 ```
This subtracts 2 from num. Now num = 29 - 2 = 27.
5.  **Increment :**
 ```java
   num++;
 ```
The num++ operation increases num by 1. Now num = 27 + 1 = 28.
6.  **Divide by 2 :**
 ```java
   num /= 2;
 ```
The num /= 2 operation divides num by 2. Now num = 28 / 2 = 14.

 **Final Value: :**
After all these operations, the value of num is 14.
 ```java
14
 ```
---
### 🔍🔁 Program Analysis and Flowcharts
Exercise : Analysis and draw the flow chart of the following program:
The program will take the user's age as input and calculates their date of birth (DOB) .

Exercise :
Analyze and draw the flow chart of the following program:
The program will take an integer number as input and check if its even or odd . 


## 1. Age to DOB Program

### 🔍 Analysis
- Takes the user's **age** as input.
- Uses the current year (e.g., 2025) to calculate the **year of birth**.
- Displays the estimated **Date of Birth**.

### 🔁 Flowchart Steps
1. Start
2. Get current year
3. Input user's age
4. Calculate `DOB = current year - age`
5. Display DOB
6. End

---

## 2. Even or Odd Checker

### 🔍 Analysis
- Takes an **integer input**.
- Checks if the number is divisible by 2.
- If `number % 2 == 0` → Even  
  Else → Odd

### 🔁 Flowchart Steps
1. Start
2. Input a number
3. Check `number % 2 == 0`
4. If Yes → Display "Even"
5. If No → Display "Odd"
6. End

---

## 🧩 Flowchart Image

(path/to/your/image.png)




---

## 📦 Arrays

### Count even and odd in an array
```java
int[] arr = {1,2,3,4,5};
int even = 0, odd = 0;
for (int n : arr) {
    if (n % 2 == 0) even++;
    else odd++;
}
System.out.println("Even: " + even + ", Odd: " + odd);
```
📤 **Output:**
```
Even: 2, Odd: 3
```

### Reverse an array
```java
int[] arr = {1,2,3,4,5};
for (int i = arr.length - 1; i >= 0; i--) {
    System.out.print(arr[i] + " ");
}
```
📤 **Output:**
```
5 4 3 2 1
```

---

## 🔧 Methods

### Check even or odd
```java
public static void checkEvenOdd(int n) {
    if (n % 2 == 0) System.out.println("Even");
    else System.out.println("Odd");
}
```
📤 **Output (checkEvenOdd(7)):**
```
Odd
```

### Sum of digits
```java
public static int sumDigits(int n) {
    int sum = 0;
    while (n != 0) {
        sum += n % 10;
        n /= 10;
    }
    return sum;
}
```
📤 **Output (sumDigits(123)):**
```
6
```

---

## 🔁 Recursion

### Sum 1 to n
```java
public static int sum(int n) {
    if (n == 1) return 1;
    return n + sum(n - 1);
}
```
📤 **Output (sum(5)):**
```
15
```

### Staircase Problem
```java
public static int waysToClimb(int n) {
    if (n == 0 || n == 1) return 1;
    return waysToClimb(n - 1) + waysToClimb(n - 2);
}
```
📤 **Output (waysToClimb(4)):**
```
5
```

---

## 🛍 Final Project (Product Management System)

### Add, Display, Search, Delete Products (Using Arrays Only)

```java
int[] ids = new int[100];
String[] names = new String[100];
double[] prices = new double[100];
int count = 0;

// Example of copying for deletion
int[] newIds = new int[100];
String[] newNames = new String[100];
double[] newPrices = new double[100];
int newCount = 0;
for (int i = 0; i < count; i++) {
    if (ids[i] != idToDelete) {
        newIds[newCount] = ids[i];
        newNames[newCount] = names[i];
        newPrices[newCount] = prices[i];
        newCount++;
    }
}
```
📤 **Output (after deleting ID 2):**
```
Product with ID 2 deleted successfully.
```

---

## 🛍 Final Project (Product Management System)

This solution uses **arrays only**, no advanced Java features, and follows your book's covered topics.

---

### ✅ Full Java Code

```java
import java.util.Scanner;

public class ProductApp {
    static int[] ids = new int[100];
    static String[] names = new String[100];
    static double[] prices = new double[100];
    static int count = 0;
    static Scanner input = new Scanner(System.in);

    public static void main(String[] args) {
        int choice;
        do {
            showMenu();
            choice = input.nextInt();
            switch (choice) {
                case 1: addProducts(); break;
                case 2: showAllProducts(); break;
                case 3: showMostExpensive(); break;
                case 4: showTotalPrice(); break;
                case 5: searchById(); break;
                case 6: deleteById(); break;
                case 7: System.out.println("Exiting..."); break;
                default: System.out.println("Invalid choice!");
            }
        } while (choice != 7);
    }

    static void showMenu() {
        System.out.println("\nProduct Management System");
        System.out.println("1. Add Products");
        System.out.println("2. Show All Products");
        System.out.println("3. Show Most Expensive Product");
        System.out.println("4. Show Total Price");
        System.out.println("5. Search by Product ID");
        System.out.println("6. Delete by Product ID");
        System.out.println("7. Exit");
        System.out.print("Choose an option: ");
    }

    static void addProducts() {
        System.out.print("How many products do you want to add? ");
        int n = input.nextInt();
        input.nextLine(); // clear buffer
        for (int i = 0; i < n; i++) {
            System.out.println("Product " + (count + 1) + ":");
            System.out.print("ID: ");
            ids[count] = input.nextInt();
            input.nextLine(); // clear buffer
            System.out.print("Name: ");
            names[count] = input.nextLine();
            System.out.print("Price: ");
            prices[count] = input.nextDouble();
            count++;
        }
    }

    static void showAllProducts() {
        if (count == 0) {
            System.out.println("No products in the system.");
            return;
        }
        System.out.println("\nProduct List:");
        for (int i = 0; i < count; i++) {
            System.out.println("ID: " + ids[i] + ", Name: " + names[i] + ", Price: " + prices[i]);
        }
    }

    static void showMostExpensive() {
        if (count == 0) {
            System.out.println("No products available.");
            return;
        }
        int maxIndex = 0;
        for (int i = 1; i < count; i++) {
            if (prices[i] > prices[maxIndex]) {
                maxIndex = i;
            }
        }
        System.out.println("Most Expensive Product:");
        System.out.println("ID: " + ids[maxIndex] + ", Name: " + names[maxIndex] + ", Price: " + prices[maxIndex]);
    }

    static void showTotalPrice() {
        double total = 0;
        for (int i = 0; i < count; i++) {
            total += prices[i];
        }
        System.out.println("Total Price of All Products: " + total);
    }

    static void searchById() {
        System.out.print("Enter ID to search: ");
        int id = input.nextInt();
        for (int i = 0; i < count; i++) {
            if (ids[i] == id) {
                System.out.println("Product Found:");
                System.out.println("ID: " + ids[i] + ", Name: " + names[i] + ", Price: " + prices[i]);
                return;
            }
        }
        System.out.println("Product not found.");
    }

    static void deleteById() {
        System.out.print("Enter ID to delete: ");
        int idToDelete = input.nextInt();

        int[] newIds = new int[100];
        String[] newNames = new String[100];
        double[] newPrices = new double[100];
        int newCount = 0;
        boolean found = false;

        for (int i = 0; i < count; i++) {
            if (ids[i] != idToDelete) {
                newIds[newCount] = ids[i];
                newNames[newCount] = names[i];
                newPrices[newCount] = prices[i];
                newCount++;
            } else {
                found = true;
            }
        }

        if (found) {
            for (int i = 0; i < newCount; i++) {
                ids[i] = newIds[i];
                names[i] = newNames[i];
                prices[i] = newPrices[i];
            }
            count = newCount;
            System.out.println("Product deleted.");
        } else {
            System.out.println("Product ID not found.");
        }
    }
}
```

---

### 📤 Sample Output (Example Session)

```
Product Management System
1. Add Products
2. Show All Products
3. Show Most Expensive Product
4. Show Total Price
5. Search by Product ID
6. Delete by Product ID
7. Exit
Choose an option: 1

How many products do you want to add? 2
Product 1:
ID: 101
Name: Laptop
Price: 1500
Product 2:
ID: 102
Name: Mouse
Price: 50

Choose an option: 2
Product List:
ID: 101, Name: Laptop, Price: 1500.0
ID: 102, Name: Mouse, Price: 50.0

Choose an option: 3
Most Expensive Product:
ID: 101, Name: Laptop, Price: 1500.0

Choose an option: 4
Total Price of All Products: 1550.0

Choose an option: 5
Enter ID to search: 101
Product Found:
ID: 101, Name: Laptop, Price: 1500.0

Choose an option: 6
Enter ID to delete: 101
Product deleted.

Choose an option: 2
Product List:
ID: 102, Name: Mouse, Price: 50.0

Choose an option: 7
Exiting...
```

---
