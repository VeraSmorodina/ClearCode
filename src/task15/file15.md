### Задание 15

3.1

Пример 1
```java
// Расчет случайного числа в промежутке от min до max
    static int randomInARange(int min, int max) {
        return  (int) (Math.random() * ((max - min) + 1)) + min;
    }
```
Пример 2
```java
public void attach(CreateIncidentView view) throws Throwable {
        this.view = view;
        //получаем данные по задаче, либо генерируем исключение
        data = view.getTaskData().orElseThrow(CantAttachViewWithoutData::new);
        view.setCallback(CreateIncidentPresenterImpl.this::createIncident);
        view.setSubject(data.getSubject());
    }
```
Пример 3
```java
public static void main(String[] args) {
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie", "David");

        // Использование Stream API для фильтрации и вывода имен, начинающихся с "A"
        names.stream()
        .filter(name -> name.startsWith("A")) // Фильтрация имен по условию
        .forEach(System.out::println);
        }
```
Пример 4
```java
public static void main(String[] args) {
        Map<String, String> users = new HashMap<>();
        users.put("user1", "Alice");
        
        // Использование Optional для безопасного получения значения по ключу
        Optional<String> user = Optional.ofNullable(users.get("user2"));
        
        user.ifPresentOrElse(
            System.out::println, 
            () -> System.out.println("Пользователь не найден.") // Обработка отсутствующего значения
        );
    }
```
Пример 5
```java
public static void main(String[] args) {
        // Используем try-with-resources для автоматического закрытия ресурсов
        try (BufferedReader reader = new BufferedReader(new FileReader("file.txt"))) { 
            String line;
            while ((line = reader.readLine()) != null) { 
                System.out.println(line);
            }
         } catch (IOException e) { 
             e.printStackTrace();
         } 
     }
```
Пример 6
```java
class Product {
    String name;
    double price;

    Product(String name, double price) {
        this.name = name;
        this.price = price;
    }
}

public class Example8 {
    public static void main(String[] args) {
        List<Product> products = new ArrayList<>();
        products.add(new Product("Apple", 0.99));
        products.add(new Product("Banana", 0.59));
        products.add(new Product("Cherry", 2.99));

        // Используем Function для преобразования продуктов в строки с ценой
        Function<Product, String> productToStringFunction = product -> product.name + ": $" + product.price;
        List<String> productStrings = products.stream()
                                             .map(productToStringFunction)
                                             .collect(Collectors.toList());
        productStrings.forEach(System.out::println);
    }
}
```
Пример 7
```java
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}

public class Example9 {
    public static void main(String[] args) {
        // Используем Supplier для генерации случайных людей
        Supplier<Person> personSupplier = () -> {
            String name = "Person " + (new Random().nextInt(100) + 1);
            int age = new Random().nextInt(50) + 18;
            return new Person(name, age);
        };

        // Генерируем и собираем людей в список с помощью Stream API
        List<Person> people = IntStream.range(0, 10)
                                       .mapToObj(i -> personSupplier.get())
                                       .collect(Collectors.toList());
        people.forEach(person -> System.out.println(person.name + " (" + person.age + ")"));
    }
}
```


3.2

Пример 1

До:
```java
public class Example5 {
public static void main(String[] args) {
Map<String, String> users = new HashMap<>();

        users.put("user1", "Тимофей");
        
        String user = users.get("user2"); // Получение значения по ключу
        
        if (user == null) { 
            System.out.println("User not found."); 
            return; 
         }

         System.out.println(user); 
     }
}
```

После:
```java
public class Example5 {
public static void main(String[] args) {
Map<String, String> users = new HashMap<>();
users.put("user1", "Антон");

         // Проверяем наличие пользователя и выводим сообщение об ошибке через метод
         String userNameToFind = "user2";
         printUserIfExists(users, userNameToFind); 
     }

     // Метод для проверки наличия пользователя и вывода сообщения об ошибке 
     private static void printUserIfExists(Map<String, String> users, String userId) { 
         String user = users.get(userId);
         if (user == null) { 
             System.out.println("User not found."); 
             return; 
         }
         System.out.println(user); 
     }
}
```
Пример 2

До:
```java
class Order {
    String itemName;
    double price;
    
    Order(String itemName, double price) {
        this.itemName = itemName;
        this.price = price;
    }
}

public class Example3 {
    public static void main(String[] args) {
        List<Order> orders = new ArrayList<>();
        
        orders.add(new Order("Laptop", 999.99));
        orders.add(new Order("Mouse", 25.50));
        
        double totalAmount = 0; // Итоговая сумма заказов
        
        for (Order order : orders) { 
            totalAmount += order.price; // Суммирование цен заказов
         }

         System.out.println("Total amount: $" + totalAmount);
     }
}
```
После:
```java
class Order {
    String itemName;
    double price;

    Order(String itemName, double price) {
         this.itemName = itemName; 
         this.price = price; 
     }
}

public class Example3 {
     public static void main(String[] args) { 
         List<Order> orders = createOrderList(); // Создание списка заказов

         double totalAmount = calculateTotalAmount(orders); // Подсчет итоговой суммы заказов

         System.out.println("Total amount: $" + totalAmount);
     }

     // Метод для создания списка заказов с ценами
     private static List<Order> createOrderList() { 
         List<Order> orders = new ArrayList<>(); 
         orders.add(new Order("Laptop", 999.99)); 
         orders.add(new Order("Mouse", 25.50)); 
         return orders; 
     }

     // Метод для подсчета итоговой суммы заказов
     private static double calculateTotalAmount(List<Order> orders) { 
         double totalAmount = 0; 

         for (Order order : orders) { 
             totalAmount += order.price; // Суммирование цен заказов
          } 

          return totalAmount; 
      }
}
```

Пример 3

До:
```java
import java.util.ArrayList;
import java.util.List;

class Student {
    String name;
    List<Integer> grades;

    Student(String name, List<Integer> grades) {
        this.name = name;
        this.grades = grades;
    }
}

public class Example2 {
    public static void main(String[] args) {
        List<Student> students = new ArrayList<>();
        
        students.add(new Student("Alice", List.of(90, 85, 88)));
        students.add(new Student("Bob", List.of(75, 80, 70)));
        
        for (Student student : students) {
            int sum = 0;
            for (int grade : student.grades) { // Вычисление суммы оценок
                sum += grade;
            }
            double average = sum / (double) student.grades.size(); // Вычисление среднего балла
            System.out.println(student.name + "'s average: " + average);
        }
    }
}
```
После:
```java
class Student {
    String name;
    List<Integer> grades;

    Student(String name, List<Integer> grades) {
        this.name = name;
        this.grades = grades;
    }
}

public class Example2 {
    public static void main(String[] args) {
        List<Student> students = createStudentList(); // Создание списка студентов
        
        for (Student student : students) {
            double average = calculateAverageGrade(student.grades); // Вычисление среднего балла
            System.out.println(student.name + "'s average: " + average);
         }
     }

     // Метод для создания списка студентов с оценками
     private static List<Student> createStudentList() {
         List<Student> students = new ArrayList<>();
         students.add(new Student("Павел", List.of(90, 85, 88)));
         students.add(new Student("Мария", List.of(75, 80, 70)));
         return students; 
     }

     // Метод для вычисления среднего балла студента
     private static double calculateAverageGrade(List<Integer> grades) { 
         int sum = 0; 
         for (int grade : grades) { 
             sum += grade; 
         } 
         return sum / (double) grades.size(); 
     }
}
```

