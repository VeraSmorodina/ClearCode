1

Было:
```java
FileInputStream fi;
fi = new FileInputStream(files.get(i));
```
Стало:
```java
FileInputStream fi = new FileInputStream(files.get(i));
```
// Сделала инициализацию переменной сразу при ее объявлении

2

Было:
```java
BufferedInputStream origin = null;
...//несколько строк кода
  for(int i=0;i<files.size();i++){
    FileInputStream fi=new FileInputStream(files.get(i));
    origin=new BufferedInputStream(fi,BUFFER);
    ...
  }
```
Стало:
```java
...//несколько строк кода
BufferedInputStream bufferedInputStream=null;
   for(int i=0;i<files.size();i++){
      FileInputStream fileInputStream=new FileInputStream(files.get(i));
      bufferedInputStream=new BufferedInputStream(fi,BUFFER);
      ...
   }
```
// Перенесла инициализацию переменной в место перед непосредственным вызовом и дала более правильное наименование

3

Было:
```java
ZipOutputStream out = null;
out = new ZipOutputStream(new BufferedOutputStream(dest));
```
Стало:
```java
ZipOutputStream zipOutputStream = new ZipOutputStream(new BufferedOutputStream(dest));
```
// Сделала инициализацию переменной сразу при ее объявлении

4

Было:
```java
long totalTime = 10_000L;
```
Стало:
```java
final long totalTimeMillis = 10_000L;
```
// Добавила переменной модификатор final и дала более правильное наименование

5

Было:
```java
double initialValue = 0.5;
```

Стало:

```java
final double totalTimeValue = 0.5;
```

// Добавила переменной модификатор final и дала более правильное наименование

6

Было:
```java
public class UpdateLoaderImpl {

    private final Context context;

    Provider provider = new Provider();
    SearchService searchService = new SearchService();

    public UpdateLoaderImpl(Context context) {
               super(taskManagerUrl);
               this.context = context;
           }
    }
```

Стало:
```java
public class UpdateLoaderImpl implements UpdateLoader {

    private final Context context;
    private Provider provider;
    private SearchService searchService;

    public UpdateLoaderImpl(Context context) {
               super(taskManagerUrl);
               this.context = context;
               this.provider = new Provider();
               this.searchService = new SearchService();
           }
     ...
    }
```
// Перенесла инициализацию всех переменных в конструктор

7

Было:
```java
ArrayList<Product> favoriteProducts;
... // несколько строк кода
favoriteProducts = getFavoriteProducts(idsArray);
   for(Product product:favoriteProducts){
      ...
   }
```
Стало:
```java
... // несколько строк кода
ArrayList<Product> favoriteProducts=getFavoriteProducts(idsArray);
   for(Product product:favoriteProducts){
     ...
   }
```
// Перенеса объявление переменной в место ее непосредственного использования

8

Было:
```java
int maxProductsCount = 15;
```
Стало:
```java
final static int maxProductsCount = 15;
```
// Добавила переменной модификатор final static

9

Было:
```java
class FiltersHandlerImpl implements FiltersHandler {
    HashSet<String> selected = new HashSet<>();
    HashSet<Pair<String, String>> available = new HashSet<>();
    HashSet<Pair<String, String>> selectedPrimaries = new HashSet<>();

    public FiltersHandlerImpl(FiltersCalculating filtersCalculating, FilterTagSplitter splitter) {
        this.calculating = filtersCalculating;
        this.splitter = splitter;
    }
        ...
}
```
Стало:
```java
class FiltersHandlerImpl implements FiltersHandler {
    private HashSet<String> selected;
    private HashSet<Pair<String, String>> available;
    private HashSet<Pair<String, String>> selectedPrimaries;
    private FiltersCalculating calculating;
    private FilterTagSplitter splitter;

    public FiltersHandlerImpl(FiltersCalculating filtersCalculating, FilterTagSplitter splitter) {
        this.calculating = filtersCalculating;
        this.splitter = splitter;
        this.selected = new HashSet<>();
        this.available = new HashSet<>();
        this.selectedPrimaries = new HashSet<>();
    }
        ...
}
```
// Перенесла инициализацию всех переменных в конструктор

10

Было:
```java
int[]resultArray=new int[array.length];
// несколько строк кода
        for(int i=0;i<array.length;i++){
        if(i==0)resultArray[array.length-1]=array[i];
        else resultArray[array.length-i-1]=array[i];
        }
```
Стало:
```java
// несколько строк кода
int[]resultArray=new int[array.length];
        for(int i=0;i<array.length;i++){
        if(i!=0){
        resultArray[array.length-1]=array[i];
        continue;
        }
        resultArray[array.length-i-1]=array[i];
        }
```
Перенесла объявление переменной непосредственно перед циклом и убрал else

11

Было:
```java
int[]userIdArray=new int[array.length];
// операции с userIdArray
```
Стало:
```java
int[]userIdArray=new int[array.length];
// операции с userIdArray
userIdArray=null;
```
// Присвоила переменной недопустимое значение

12

Было:
```java
int waitingTime=calculateWaitingTime()
... // операции с waitingTime
```
Стало:
```java
int waitingTime = calculateWaitingTime()
if(waitingTime!=null&&waitingTime>=0){
   // операции с waitingTime
}
waitingTime = null;
```
// Включила инвариант и присвоила переменной недопустимое значение после окончания работы с ней

13

Было:
```java
List<Comment> commentList = commentsRepository.getCommentList();
// операции с commentList
```
Стало:
```java
List<Comment> commentList=commentsRepository.getCommentList();
   if(commentList!=null)
     // операции с commentList
```
// Включила инвариант для проверки на null

14

Было:
```java
String taskManagerUrl = "...";
```
Стало:
```java
final static String taskManagerUrl = "...";
```
// Добавила переменной модификатор final static

15

Было:
```java
String attachmentUrl = "...";
```
Стало:
```java
final static String attachmentUrl = "...";
```
// Добавила переменной модификатор final static

