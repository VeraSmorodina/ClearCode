### Задание 17

1. Недостоверный комментарий

До:
```java
// Этот метод возвращает список всех пользователей
public List<User> getUsers() {
    return users.subList(0, 10);
}
```
После:
```java
// Возвращает первых 10 пользователей из списка
public List<User> getUsers() {
    return users.subList(0, 10);
}
```
2. Шум

До:
````java
// Увеличиваем счетчик на 1
counter++;
````
После:
```java
// Увеличиваем общий счетчик пользователей
totalUserCount++;
```
3. Избыточные комментарии

До:
```java
// Эта функция добавляет пользователя в систему и возвращает статус операции.
public boolean addUser(User user) {
    // код...
    return true;
}
```
После:
```java
public boolean addUser(User user) {
    // Добавляем пользователя в систему.
    return true;
}
```
4. Слишком много информации

До:
```java
// В этом методе мы будем рассматривать различные аспекты работы с пользователями, включая их создание, редактирование и удаление.
public void manageUsers() {
    // код...
}
```
После:
```java
// Управляет пользователями: создание, редактирование и удаление.
public void manageUsers() {
    // код...
}
```
5. Нелокальная информация

До:
```java
// В системе есть разные типы пользователей: администраторы, обычные пользователи и гости.
if (user.isAdmin()) {
    grantAdminAccess();
}
```
После:
```java
// Проверяем, является ли пользователь администратором.
if (user.isAdmin()) {
    grantAdminAccess();
}
```

6. Отсутствие контекста

До:
```java
// Обрабатываем данные.
processData(data);
```
После:
```java
// Обрабатываем входные данные для анализа.
processData(inputData);
```

7. Избыточный уровень детализации

До:
```java
// Этот метод отвечает за создание нового объекта пользователя в базе данных с заданными параметрами.
public void createUser(String name, String email) {
    database.add(new User(name, email));
}
```
После:
```java
// Создает нового пользователя в базе данных.
public void createUser(String name, String email) {
    database.add(new User(name, email));
}
```

8. Позиционные маркеры

До:
```java
//////////НЕ ИЗМЕНЯЙТЕ ЭТОТ ФАЙЛ!!!/////////
public final class BuildConfig {
    ...
}
```
После:

```java
// Используйте этот файл только для чтения значений
public final class BuildConfig {
    ...
}
```

9. Закомментированный код

Был закомментированный метод, удалила его:

```java
        //    @Before
        //    public void setUp() throws Exception {
        //        InputStream stream = new FileInputStream("src/test/resources/initial_scroll_request.json");
        //        byte[] data = new byte[stream.available()];
        //        stream.read(data);
        //        expected = new String(data, StandardCharsets.UTF_8);
        //    }
```

10. Шум

До:
```java
/** Удалить профиль по UUID */
public void removeProfile(java.lang.String profileUUID) throws RemoteException;
```
После:
```java
public void removeProfile(String profileUUID) throws RemoteException;
```

11. Шум

До:
```java
// Создаем фабрику SSL-сокетов с нашим полностью доверительным менеджером
final SSLSocketFactory sslSocketFactory = sslContext.getSocketFactory();
```
После:
```java
final SSLSocketFactory sslSocketFactory = sslContext.getSocketFactory();
```

12. 

До:
```java
// Извлечь уведомление
void extract(){
    ...
}
```
После:
```java
void extractAndShowNotification(){
    ...
}
```
13. Шум

До:
```java
// Класс для хранения состояния ленивого списка
public class rememberForeverLazyListState() {
    ...
}
```

После:
```java
public class rememberLazyListState() {
    ...
}
```

14. Не использовать комментарии там, где можно использовать функцию или переменную

До:
```java
// Пауза VPN (то же самое, что и использование функции паузы в панели уведомлений)
public void pause() throws RemoteException;
```
После:
```java
public void pauseVPN() throws RemoteException;
```

15. Позиционные маркеры

До:
```java
/////////////// ЗАПУСКАЙТЕ ЭТОТ ТЕСТ ТОЛЬКО ЕСЛИ СЕРВИС ПРОКРУТКИ ДОСТУПЕН ////////////////////////
void scrollRequestTest(){
    ...
}
```
После:
```java
// Запускайте этот тест только если сервис прокрутки доступен
void scrollRequestTest(){
    ...
}
```