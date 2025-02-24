# Aufgabe 1 - imperativ vs. deklarativ

## Imperativer Stil mit Anpassung
```java
public static int calculateScore(String word) {
    int score = 0;
    for (char c : word.toCharArray()) {
        if (c != 'a') {
            score++;
        }
    }
    return score;
}
```


## Deklarativer Stil mit Anpassung
```java
public static int wordScore(String word) {
    return (int) word.chars().filter(c -> c != 'a').count();
}
```
