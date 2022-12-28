---
title: "5 Tips for Creating Clean Code"
date: 2022-12-29T05:39:10+07:00
draft: false
tags: ["Programming", "Technical Skill"]
---

Clean code is code that is easy to read, understand, and maintain. It follows a set of coding standards and principles that aim to make the code as readable and maintainable as possible.

Clean code is important because it helps reduce the time and effort required to understand and modify the codebase, and it makes it easier to add new features or fix bugs. It also promotes collaboration and reduces the risk of introducing new issues when modifying the code.

To achieve clean code, it's important to follow best practices for naming variables and functions, using clear and consistent formatting, keeping functions small and focused, avoiding unnecessary complexity, and writing self-documenting code. It's also important to follow established coding standards and to consistently apply these principles throughout the codebase.

Here are five important principles of clean code, along with some example code to illustrate each principle:

## Use Searchable Names

Good names are easy to search for and make it easy to understand the purpose of the code. Use descriptive and meaningful names that accurately reflect the purpose of the variable or function.

Bad:

```java
int computeTotalCost(int quantity, int pricePerItem)
{
    return quantity * pricePerItem + 5;
}
```

In this example, the additional cost of $5 is added directly to the computation, without any context or explanation. This makes it harder to understand the purpose of the code and to modify it if necessary.

A better way to implement this code would be to use a descriptive constant to represent the additional cost:

Good:

```java
int computeTotalCost(int quantity, int pricePerItem)
{
    final int SHIPPING_COST = 5;
    return quantity * pricePerItem + SHIPPING_COST;
}
```

This version of the code is easier to understand and modify, because the purpose of the additional cost is clearly explained with the use of a descriptive constant.

## Function Name Should Be Verb and Function Should Do One Thing in One Thing Only

Functions should have descriptive names that reflect the action they perform, and they should do one thing only. A function that does more than one thing is harder to understand and maintain.

Bad:

```java
int calc(int x, int y)
{
    int z = x + y;
    int w = x * y;
    return z - w;
}
```

Good:

```java
int add(int x, int y)
{
    return x + y;
}

int multiply(int x, int y)
{
    return x * y;
}

int subtract(int x, int y)
{
    return add(x, y) - multiply(x, y);
}
```

## Three or Less Arguments in a Function

Functions with too many arguments are hard to understand and maintain. Aim to keep the number of arguments in a function to three or less. If a function requires more than three arguments, consider refactoring the code to use an object or a data structure to pass the arguments.

Bad:

```java
void printInvoice(int customerId, int invoiceNumber, int itemNumber, int quantity, int pricePerItem, int discountPercent, int taxPercent)
{
    // code to print invoice
}
```

Good:

```java
class Invoice
{
    int customerId;
    int invoiceNumber;
    int itemNumber;
    int quantity;
    int pricePerItem;
    int discountPercent;
    int taxPercent;
}

void printInvoice(Invoice invoice)
{
    // code to print invoice
}
```

## Avoid Passing Boolean Value as Arguments in a Function

Passing a boolean value as an argument to a function can make the code harder to understand, because it is not immediately clear what the boolean value represents. Instead, consider using a descriptive name for the argument or refactoring the code to use a function with a more descriptive name.

Bad:

```java
void printMessage(string message, bool isError)
{
    if (isError)
    {
        Console.WriteLine("ERROR: " + message);
    }
    else
    {
        Console.WriteLine(message);
    }
}
```

In this example, the boolean value `isError` is passed as an argument to the function, which requires an additional if statement to determine how to print the message.

A better way to implement this code would be to use a function with a more descriptive name that reflects the purpose of the function:

Good:

```java
void printErrorMessage(string message)
{
    Console.WriteLine("ERROR: " + message);
}

void printMessage(string message)
{
    Console.WriteLine(message);
}
```

This version of the code is easier to understand, because the purpose of the functions is clear from their names, and there is no need for an additional if statement inside the function.

## Avoid Using Letter Names

Using single-letter names for variables and functions can make the code hard to understand, because it is not immediately clear what the letters represent. Instead, use descriptive names that accurately reflect the purpose of the code.

Bad:

```java
int[][] data = new int[5][5];
for (int i = 0; i < 5; i++)
{
    for (int j = 0; j < 5; j++)
    {
        data[i][j] = i + j;
    }
}
```

In this example, the variables `i` and `j` are used as indexes for the multidimensional array data, but it is not immediately clear what these letters represent.

A better way to implement this code would be to use descriptive names for the indexes:

Good:

```java
int[][] data = new int[5][5];
for (int row = 0; row < 5; row++)
{
    for (int col = 0; col < 5; col++)
    {
        data[row][col] = row + col;
    }
}
```

This version of the code is easier to understand, because the purpose of the variables `row` and `col` is clear from their names.

---

In conclusion, clean code is code that is easy to read, understand, and maintain. It follows a set of coding standards and principles that aim to make the code as readable and maintainable as possible. 

Some important principles of clean code include using meaningful and descriptive names, using clear and consistent formatting, keeping functions small and focused, avoiding unnecessary complexity, and writing self-documenting code. 

By following these principles, you can create code that is easier to understand and modify, and that promotes collaboration and reduces the risk of introducing new issues when modifying the code.

**Source:**

{{< youtube Jz8Sx1XYb04 >}}
