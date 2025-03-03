## **Aufgabe 2 - Impure Functions zu Pure Functions umschreiben**
Wir überarbeiten **impure functions** so, dass sie die Regeln für **pure functions** einhalten.

### ❌ **Impure Function 1.1 - `addToCart`**
**Problem:** Verändert den globalen Zustand `cartItems`.  
**Lösung:** Stattdessen eine neue Liste zurückgeben.

#### ✅ **Pure Function (JavaScript)**
```javascript
function addToCart(cart, item) {
    return [...cart, item]; // Erstellt eine neue Liste ohne Mutation
}

let cart = [];
cart = addToCart(cart, "Apple");
cart = addToCart(cart, "Banana");
console.log(cart); // ['Apple', 'Banana']
```

#### ✅ **Pure Function (Scala)**

```
def addToCart(cart: List[String], item: String): List[String] = {
  cart :+ item // Erstellt eine neue Liste ohne Veränderung der alten
}

val cart = List()
val newCart = addToCart(cart, "Apple")
println(newCart) // List(Apple)
```

#### ❌ **Impure Function 1.4 - multiplyWithRandom**

**Problem:** Verwendet Math.random(), was ein zufälliges Ergebnis liefert.  
**Lösung:** Zufallswert als Parameter übergeben.

#### **✅ Pure Function (JavaScript)**  

```
function multiplyWithRandom(number, randomValue) {
    return number * randomValue;
}

console.log(multiplyWithRandom(5, 0.5)); // Immer 2.5
```

#### **✅ Pure Function (Scala)**  

```
def multiplyWithRandom(number: Double, randomValue: Double): Double = {
  number * randomValue
}

println(multiplyWithRandom(5, 0.5)) // Immer 2.5
```

#### **❌ Impure Function 1.6 - printAndReturnString**  
**Problem:** Gibt Wert auf der Konsole aus (Seiteneffekt).  
**Lösung:** Nur Rückgabe ohne console.log. 

#### **✅ Pure Function (JavaScript)**  

```
function returnString(str) {
    return str; // Keine Nebenwirkungen
}
```

#### **✅ Pure Function (Scala)**

```
def returnString(str: String): String = str
```

