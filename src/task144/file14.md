### Задание 14

Пример 1: Использование Map для хранения объектов с уникальными ключами

Код до применения принципов:

```java
class Student {
    String name;
    int score;

    Student(String name, int score) {
        this.name = name;
        this.score = score;
    }
}

public class Example1 {
    public static void main(String[] args) {
        Student[] students = new Student[3];
        
        students[0] = new Student("Alice", 85);
        students[1] = new Student("Bob", 90);
        students[2] = new Student("Charlie", 78);

        // Поиск студента по имени
        String searchName = "Bob";
        for (int i = 0; i < students.length; i++) {
            if (students[i].name.equals(searchName)) {
                System.out.println(searchName + " scored: " + students[i].score);
            }
        }
    }
}
```
Код после применения принципов:
```java
class Student {
    String name;
    int score;

    Student(String name, int score) {
        this.name = name;
        this.score = score;
    }
}

public class Example1 {
    public static void main(String[] args) {
        Map<String, Student> studentMap = new HashMap<>();
        
        studentMap.put("Alice", new Student("Alice", 85));
        studentMap.put("Bob", new Student("Bob", 90));
        studentMap.put("Charlie", new Student("Charlie", 78));

        // Поиск студента по имени
        String searchName = "Bob";
        if (studentMap.containsKey(searchName)) {
            System.out.println(searchName + " scored: " + studentMap.get(searchName).score);
        } else {
            System.out.println(searchName + " not found.");
        }
    }
}
```

Пример 2: Использование PriorityQueue для управления задачами

Код до применения принципов:

```java
class Task implements Comparable<Task> {
    String name;
    int priority;

    Task(String name, int priority) {
        this.name = name;
        this.priority = priority;
    }

    @Override
    public int compareTo(Task other) {
        return Integer.compare(this.priority, other.priority);
    }
}

public class Example2 {
    public static void main(String[] args) {
        Task[] tasks = new Task[3];
        
        tasks[0] = new Task("Task 1", 2);
        tasks[1] = new Task("Task 2", 1);
        tasks[2] = new Task("Task 3", 3);

        // Сортировка задач по приоритету
        for (int i = 0; i < tasks.length; i++) { // Ошибка: сложная сортировка
            for (int j = i + 1; j < tasks.length; j++) {
                if (tasks[i].compareTo(tasks[j]) > 0) {
                    Task temp = tasks[i];
                    tasks[i] = tasks[j];
                    tasks[j] = temp;
                }
            }
        }

        // Вывод отсортированных задач
        for (Task task : tasks) {
            System.out.println(task.name + " with priority " + task.priority);
        }
    }
}
```

Код после применения принципов:
```java
class Task implements Comparable<Task> {
    String name;
    int priority;

    Task(String name, int priority) {
        this.name = name;
        this.priority = priority;
    }

    @Override
    public int compareTo(Task other) {
        return Integer.compare(this.priority, other.priority);
    }
}

public class Example2 {
    public static void main(String[] args) {
        PriorityQueue<Task> taskQueue = new PriorityQueue<>();
        
        taskQueue.add(new Task("Task 1", 2));
        taskQueue.add(new Task("Task 2", 1));
        taskQueue.add(new Task("Task 3", 3));

        // Вывод отсортированных задач по приоритету
        while (!taskQueue.isEmpty()) {
            Task task = taskQueue.poll();
            System.out.println(task.name + " with priority " + task.priority);
        }
    }
}
```

Пример 3: Использование Set для хранения уникальных значений

Код до применения принципов:
```java
public class Example3 {
    public static void main(String[] args) {
        String[] items = {"apple", "banana", "apple", "orange"};

        // Проверка на уникальность элементов
        for (int i = 0; i < items.length; i++) { 
            for (int j = i + 1; j < items.length; j++) { 
                if (items[i].equals(items[j])) { // Ошибка: дублирование элементов
                    System.out.println(items[i] + " is a duplicate.");
                }
            }
        }
        
        System.out.println(Arrays.toString(items));
    }
}
```
Код после применения принципов:

```java
public class Example3 {
    public static void main(String[] args) {
        String[] items = {"apple", "banana", "apple", "orange"};
        
        Set<String> uniqueItems = new HashSet<>();
        
        for (String item : items) { 
            if (!uniqueItems.add(item)) { // Проверка на уникальность с использованием Set
                System.out.println(item + " is a duplicate.");
            }
        }

        System.out.println(uniqueItems); // Вывод уникальных элементов
    }
}
```

Пример 4: Использование Deque вместо стека для обработки данных

Код до применения принципов:
```java
public class Example4 {
    public static void main(String[] args) {
        int[] stackArray = new int[5];
        
        // Заполнение стека
        for (int i = 0; i < stackArray.length; i++) {
            stackArray[i] = i + 1;
        }

        // Обработка стека
        for (int i = stackArray.length - 1; i >= 0; i--) { 
            System.out.println(stackArray[i]);
            stackArray[i] += 10; // Ошибка: изменение значений в массиве через индексы
            System.out.println(stackArray[i]);
         }
     }
}
```
Код после применения принципов:
```java
public class Example4 {
    public static void main(String[] args) {
        Deque<Integer> stackDeque = new ArrayDeque<>();
        
        // Заполнение стека
        for (int i = 1; i <= 5; i++) {
            stackDeque.push(i);
         }

         // Обработка стека
         while (!stackDeque.isEmpty()) { 
             int value = stackDeque.pop();
             System.out.println(value);
             value += 10; // Безопасное изменение значения без прямой индексации
             System.out.println(value);
         }
     }
}
```
Пример 5: Использование List для работы с коллекцией объектов

Код до применения принципов:
```java
class Employee {
    String name;

    Employee(String name) {
         this.name = name;
     }
}

public class Example5 {
     public static void main(String[] args) {
         Employee[] employees = new Employee[3];
         
         employees[0] = new Employee("John");
         employees[1] = new Employee("Jane");
         employees[2] = new Employee("Doe");

         // Вывод имен сотрудников с использованием индексов
         for (int i = 0; i <= employees.length; i++) { // Ошибка: выход за границы массива
             System.out.println(employees[i].name);
         }
     }
}
```
Код после применения принципов:
```java
import java.util.ArrayList;
import java.util.List;

class Employee {
     String name;

     Employee(String name) {
         this.name = name;
     }
}

public class Example5 {
     public static void main(String[] args) {
         List<Employee> employees = new ArrayList<>();
         
         employees.add(new Employee("John"));
         employees.add(new Employee("Jane"));
         employees.add(new Employee("Doe"));

         // Вывод имен сотрудников без использования индексов
         for (Employee employee : employees) { 
             System.out.println(employee.name);
         }
     }
}
```