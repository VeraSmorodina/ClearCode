## Задание 4

**7.1**

open - isDoorOpen

x - isEmpty;

active - isActive

checked - isCheckboxChecked;

empty - isListEmpty;

**7.2**

b - found;

flag - done;

y - success;

**7.3**

Было:

```java
for(int i=0;i<manArray.length;i++){
    for(int j=0;j<manArray[i].children.size();i++){
    //...
    }
}
```

Стало:

```java
for(int manIndex=0;manIndex<manArray.length;manIndex++){
    for(int childIndex=0;childIndex<manArray[manIndex].children.size();childIndex++){
    //...
    }
}
```

**7.4**

evenNumber - notEvenNumber positiveNumberCount - notPositiveNumberCount

**7.5**

temp - isTemperatureWithinRange x - sumAllNumbers










