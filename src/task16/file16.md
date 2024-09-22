## Задание 16

###Пуект 1

Пример 1

До:
```java
// Проверка, является ли строка пустой или null
if (str == null || str.isEmpty()) {
    System.out.println("Строка пустая");
}
```
После:
```java
if (isStringNullOrEmpty(str)) {
    System.out.println("Строка пустая");
}

private boolean isStringNullOrEmpty(String str) {
    return str == null || str.isEmpty();
}
```
Пример 2

До:
```java
// Получаем максимальное значение из массива чисел
int max = Integer.MIN_VALUE;
for (int number : numbers) {
    if (number > max) {
        max = number;
    }
}
```
После:
```java
int maxNumber = findMaxValue(numbers);

private int findMaxValue(int[] numbers) {
    int max = Integer.MIN_VALUE;
    for (int number : numbers) {
        if (number > max) {
            max = number;
        }
    }
    return max;
}
```

Пример 3

До:
```java
public class Example10 {
    public static void main(String[] args) {
        String[] items = {"item1", "item2", "item3"};
        
        for (int i = 0; i < items.length; i++) { 
            System.out.println(items[i]); 
        }
        
        // Вывод количества элементов в массиве 
        System.out.println("Total items: " + items.length);
    }
}
```
После:
```java
public class Example10 {
    public static void main(String[] args) {
        String[] items = {"item1", "item2", "item3"};
        printItems(items);
        printTotalItemsCount(items.length);
    }

    private static void printItems(String[] items) { 
        for (String item : items) { 
            System.out.println(item); 
        }
     }

     private static void printTotalItemsCount(int count) { 
         System.out.println("Total items: " + count); 
     }
}
```

###Пункт 2

Пример 1
```java
// Проверяем быстродействие сервиса ElasticSearch
@Test
public void testLoadAllComments() {
    long startTime = System.currentTimeMillis();
    searchService.loadAllComments("6ea41470-a62e-4c19-895b-fad0b5dda8e8");
    long elapsedTime = System.currentTimeMillis() - startTime;
    System.out.println("Elapsed time: " + elapsedTime + " ms");
}
```
###Пункт 3

Пример 1
```java
// p0 - сообщение, p1 - id пользователя, от которого оно пришло
@Override
public void onMessageReceived(RtmMessage p0, String p1) {
    if (p0 != null) {
        _receivedMessageFlow.tryEmit(p0.getText());
    }
}
```
Пример 2
```java
// String - id пользователя, Int - код его статуса в сети
@Override
public void onPeersOnlineStatusChanged(Map<String, Integer> status) {
    if (status != null) {
        for (Map.Entry<String, Integer> entry : status.entrySet()) {
            String userId = entry.getKey();
            int statusCode = entry.getValue();
            processUserOnlineStatusChange(userId, statusCode);
        }
    }
}

private void processUserOnlineStatusChange(String userId, int statusCode) {
    // Реализация обработки изменения статуса пользователя
    // Например, обновление интерфейса или отправка уведомления
}
```
Пример 3
```java
// p0 - файл, прикрепленный к сообщению, p1 - id пользователя, который его отправил
@Override
public void onFileMessageReceivedFromPeer(RtmFileMessage p0, String p1) {
    if (p0 != null) {
        _receivedFileMessageFlow.tryEmit(p0);
    }
}
```
Пункт 4

Пример 1

```java
// Этот метод может вызвать NullPointerException.
public String getUserName(User user) {
    return user.getName();
}
```
Пример 2
```java
// Этот метод устарел и не рекомендуется к использованию.
public void oldMethod() {
    // Устаревшая логика...
}
```
Пример 3
```java
// Внимание: этот код может быть медленным при обработке больших объемов данных.
// Рассмотрите возможность оптимизации или использования потоковой обработки.
public List<String> processLargeDataSet(List<String> data) {
    // Обработка данных...
}
```
### Пункт 5

Пример 1

```java
// Параметр userId должен быть валидным и существовать в системе.
// Невалидный userId приведет к ошибкам при загрузке данных пользователя.
public void loadUserData(String userId) {
    // Логика загрузки данных пользователя
}
```
Пример 2
```java
// Синхронизация необходима для предотвращения конфликтов при одновременном доступе к методу из нескольких потоков.
// Это гарантирует целостность данных при обновлении баланса счета.
public void updateAccountBalance() {
    // Логика обновления баланса счета
}
```

### Пункт 6

Пример 1
```java
// TODO: Написать тесты для метода calculateDiscount().
// Убедитесь, что все возможные сценарии учитываются в тестах.
public void calculateDiscount() {
        // Логика расчета скидки
        }
}
```
Пример 2
```java
// TODO: Реализовать экспорт данных в формат CSV в методе exportData().
// Текущая реализация поддерживает только экспорт в формат JSON.
public void exportData() {
    // Текущая реализация экспорта данных
}
```
Пример 3
```java
// TODO: Реализовать обработку исключений в методе connectToDatabase().
// Убедитесь, что все возможные ошибки подключения обрабатываются корректно.
public void connectToDatabase() {
    // Логика подключения к базе данных
}
```
Пример 4
```java
// TODO: Рефакторинг метода complexLogicMethod(int a, int b) для улучшения читаемости и поддержки.
// Рассмотрите возможность разделения логики на несколько методов с ясными именами. 
public void complexLogicMethod(int a, int b) { 
    if (a > b) { 
        System.out.println("A is greater than B"); 
        checkIfNegative(b); // Вынесение проверки в отдельный метод 
    } 
} 

private void checkIfNegative(int number) { 
    if (number < 0) { 
        System.out.println("Number is negative"); 
    } 
} 
```

