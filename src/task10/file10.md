### Задание 10

1

Было:
```java
String greeting = "Привет";
```
Стало:
```java
final String GREETING = "Привет";
String greeting = GREETING;
```
Перевела строковые значения в константы

2

Было:
```java
if (elementIndex < 0 || elementIndex > MAX_ELEMENTS || elementIndex == lastElementIndex)
```
Стало:
```java
boolean finished = elementIndex < 0 || elementIndex > MAX_ELEMENTS;
boolean repeatedEntry = elementIndex == lastElementIndex;
if (finished || repeatedEntry)
```
Упростила условие с помощью логических переменных для повышения читабельности.

3

Было:
```java
int result = (Integer.MAX_VALUE / 2) * 3;
```
Стало:
```java
int intermediate = Integer.MAX_VALUE / 2;
Integer result = (intermediate <= Integer.MAX_VALUE / 3) ? (intermediate * 3) : null;
```
Добавила проверку переполнения промежуточных результатов.

4

Было:
```java
int num = 10;
double result = num / 2.0;
```
Стало:
```java
int num = 10;
int result = num / 2;
```
Устранила неявное приведение типов, деление стало целочисленным.

5

Было:
```java
int numerator = 10;
int denominator = 0;
int result = numerator / denominator;
```
Стало:
```java
int numerator = 10;
int denominator = 0;
Integer result = (denominator != 0) ? (numerator / denominator) : null;
```
Добавила проверку на деление на ноль, предотвращая ошибку выполнения.

6

Было:
```java
int result = 5 / 2;
System.out.println(result);
```
Стало:
```java
int result = 5 / 2;
if (5 % 2 == 0) {
    System.out.println(result);
} else {
    System.out.println("Деление не целочисленное");
}
```

7

Было:
```java
int squirrelResult = squirrelResult * i
```
Стало:
```java
if (squirrelResultLong < Integer.MAX_VALUE) {
long squirrelResultLong = (long) squirrelResultInt * (long) i;
}
```
добавила проверку переполнения int

8

Было:
```java
int result += currentSpeed * (hoursSpent/lastHour);
```
Стало:
```java
if (lastHour != 0){
impulse += currentSpeed * (hoursSpent/lastHour);
}
```
добавила проверку на нулевое значение, переименовала переменную result в более понятное имя

9

Было:
```java
if (b - a == 1 || a - b == 1 || pairs.contains(new Pair(a, b))) sum += 1;
```
Стало:
```java
boolean isNumbersDiffersByOne = firstNumber - secondNumber == 1 || firstNumber - secondNumber == -1;
boolean isPairsListContainsPair = pairs.contains(new Pair(a, b));
if (isNumbersDiffersByOne || isPairsListContainsPair) sum += 1;
```    
добавила логические переменные для упрощения читаемости кода

10

Было:
```java
result += map.get(aChar) == null ? 23 : map.get(aChar);
```
Стало:
```java
result += map.get(aChar) == null ? DEFAULT_COST : map.get(aChar);
```
заменила магическое число на константу

11

Было:
```java
double percent = max / sum;
```
Стало:
```java
if (sum == 0) return;
double percent = max / sum;
```
добавила проверку на 0;

12

Было:
```java
float x = 0.1f;
```
Стало:
```java
double x = 0.1;
```
повысила точность с float до double.