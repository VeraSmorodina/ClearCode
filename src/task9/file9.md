### Задание 9

if(temperature == 0) - if(temperature == FREEZING_POINT)
магическое число изменено на константу, стало ясно зачем нужна переменная

for (int i = 10; i >= 0; i--) - for (int START_COUNT = 10; i >= 0; i--)
магическое стартовое число изменено на константу

int port = 8080 - private static final int PORT = 8080
значение данной переменной будет тебоваться часто имеет смысл сделать ее константой

new byte[4096] - new byte[READ_BYTES_BUFFER];
// магическое число при чтении из файла заменено на константу

notify(101, nb.build()) - notify(ERROR_NOTIFICATION_ID, nb.build());
// магическое число в поле с id заменено на константу

response.code() == 200 - response.code() == ERROR_RESPONSE_CODE
// магическое число кода ответа сервера заменено на константу

final static String usersPath - final static String USERS_PATH
// имя константы изменено на заглавные буквы через подчеркивание

final static String homePdfsUrl - final static String HOME_PDF_URL
// имя константы изменено на заглавные буквы через подчеркивание

if(age < 18) - if(age < MINIMUM_AGE)
//магическое число заменено на константу

int BUFFER - int READ_BYTES_BUFFER
// стало более ясно, для чего нужна эта переменная

double area = 3.14 * radius * radius - double area = PI * radius * radius
//число пи вынесено в константу

for (int i = 0; i <= 200; i++) - for (int i = 0; i <= MAX_NUMBER; i++)
магическое число в цикле изменено на константу





