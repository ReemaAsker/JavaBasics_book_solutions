# 📘 Java Book – Exercises & Solutions with Output

This document provides all the exercises from the book along with their solutions, grouped by topic and includes example outputs.

---

## 🗂 Table of Contents

- [🔤 Input, Variables & Parsing](#-input-variables--parsing)
- [🔁 Loops](#-loops)
- [📦 Arrays](#-arrays)
- [🔧 Methods](#-methods)
- [🔁 Recursion](#-recursion)
- [🛍 Final Project (Product Management System)](#-final-project-product-management-system)

---

## 🔤 Input, Variables & Parsing

### 📝 Exercise
1. Print your name
2. Store age in a String, convert to integer
3. Add 5 years and print

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
