Задание 13

Пример 1

До:

```java
public class Example4 {
    public static void main(String[] args) {
        int color = 255;
        System.out.println("Цвет: " + color);
    }
}
```
После:
```java
public class Example4 {
    public static void main(String[] args) {
        Map<String, Integer> colors = new HashMap<>();
        colors.put("white", 255);
        colors.put("black", 0);
        int color = colors.get("white"); // Позднее связывание
        System.out.println("Цвет: " + color);
    }
}
```
Пояснение: Хранение значений цветов в коллекции Map позволяет динамически управлять ими. Связывание происходит во время
выполнения при извлечении значения из карты по ключу, что обеспечивает гибкость и возможность изменения значений.

Пример 2: 

До:

```java
public class Example3 {
    public static void main(String[] args) {
        int color = 255; // Жестко закодированное значение
        System.out.println("Цвет: " + color);
    }
}
```

После:

```java
public class Example3 {
    public static void main(String[] args) {
        setColor(128); // Связывание во время выполнения
    }

    private static void setColor(int color) {
        System.out.println("Цвет: " + color);
    }
}
```
Пояснение: Передача значения цвета в качестве параметра метода setColor() позволяет изменять цвет, вызывая метод с
разными аргументами. Связывание происходит во время выполнения при вызове метода, что делает код более гибким.

Пример 3:

До:
```java
public class Example2 {
    public static void main(String[] args) {
        int color = 255; // Жестко закодированное значение
        System.out.println("Цвет: " + color);
    }
}
```
После:
```java
public class Example2 {
    public static void main(String[] args) {
        Properties properties = new Properties();
        try {
            properties.load(new FileInputStream("config.properties"));
            int color = Integer.parseInt(properties.getProperty("color")); // Позднее связывание System.out.println("Цвет: " + color); } catch (IOException e) { e.printStackTrace(); } } }

```
Пояснение: Чтение значения цвета из конфигурационного файла во время выполнения позволяет легко изменять настройки без
необходимости перекомпиляции программы. Связывание происходит при чтении свойства из файла, что обеспечивает
максимальную гибкость.

