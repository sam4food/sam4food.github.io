---
layout: project
type: project
image: img/binaryadd/squarebinary.png
title: "Binary Addition"
date: 2023-04
published: false
labels:
  - Pycharm
  - Python
summary: "A program that performs binary addition from ICS-141."
---

<img class="img-fluid" src="../img/binaryadd/binarypic.jpg">

Binary Addition is a program that takes two integers as an input and then it will return the binary representation of the sum of the two numbers as a string. 

Binary Addition was created on Pycharm (an IDE) using Python. The program is simple but is quite helpful when binary addition is needed. Furthermore, due to the simplistic nature of this, it makes the code very easy to understand. The code created was done by myself and the help of a TA who helped answer questions that I had regarding this assignment.

In this assignment, I learned how to better utilize Python in order to accomplish a task. Addiionally, I developed a better understanding of Python rules and how Python works in general which deepened my understanding of the language. This assignment also helped me develop a better understanding of how binary addition works which was definitely needed when completing this assignment. 

Source:

```py
def decimal_to_binary(number):
    result = ""
    while number != 0:
        remainder = number % 2
        result += str(remainder)
        number = number // 2
    return result[::-1]

def binary_addition(x, y):
    xBinary = decimal_to_binary(x)
    yBinary = decimal_to_binary(y)

    if len(xBinary) != len(yBinary):
        if len(xBinary) > len(yBinary):
            yBinary = yBinary.zfill(len(xBinary))
        else:
            xBinary = xBinary.zfill(len(yBinary))

    answer = ""
    rem = 0
    for i in range(len(xBinary) - 1, -1, -1):
        theSum = int(xBinary[i]) + int(yBinary [i]) + rem
        rem = int(theSum / 2)
        answer = str(theSum - 2 * rem) + answer

    if rem:
        answer = "1" + answer

    return answer


print(binary_addition(24, 98))
print(binary_addition(2387482, 1))
print(binary_addition(25, 25))
```