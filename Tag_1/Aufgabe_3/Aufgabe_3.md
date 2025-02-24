
# Aufgabe 3 - TipCalculator

```java
import java.util.List;

public class TipCalculator {
    public static int calculateTip(List<String> names) {
        if (names.isEmpty()) {
            return 0;
        }
        return names.size() > 5 ? 20 : 10;
    }
}
```
