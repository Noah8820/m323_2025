
# Aufgabe 2 - Shopping Cart Funktion

## Imperative Umsetzung
```java
class ShoppingCart {
    private List<String> items = new ArrayList<>();
    private boolean bookAdded = false;

    public void addItem(String item) {
        items.add(item);
        if (item.equalsIgnoreCase("book")) {
            bookAdded = true;
        }
    }

    public void removeItem(String item) {
        items.remove(item);
        if (item.equalsIgnoreCase("book") && !items.contains("book")) {
            bookAdded = false;
        }
    }

    public List<String> getItems() {
        return items;
    }

    public double getDiscount() {
        return bookAdded ? 5.0 : 0.0;
    }
}
```

## Funktionale Umsetzung
```java
import java.util.List;

public class ShoppingCartFunctional {
    public static double getDiscountPercentage(List<String> cart) {
        return cart.contains("book") ? 5.0 : 0.0;
    }
}
```
