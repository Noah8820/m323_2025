# Aufgabe 3 - Eigene Pure Functions schreiben

## 3.1 Summe aller Listenelemente
Die Funktion berechnet rekursiv die Summe aller Zahlen in einer Liste.

```scala
def sumList(numbers: List[Int]): Int = {
  if (numbers.isEmpty) 0
  else numbers.head + sumList(numbers.tail)
}

println(sumList(List(1, 2, 3, 4))) // 10
```

## 3.2 Mittelwert einer Liste
Die Funktion berechnet den Durchschnitt aller Zahlen in einer Liste.


```
def average(numbers: List[Int]): Double = {
  if (numbers.isEmpty) 0
  else sumList(numbers).toDouble / numbers.length
}

println(average(List(1, 2, 3, 4))) // 2.5
```

## 3.3 Alphabetische Sortierung einer Liste
Diese Funktion sortiert eine Liste von Strings alphabetisch.

```
def sortStrings(strings: List[String]): List[String] = {
  strings.sorted
}

println(sortStrings(List("Banane", "Apfel", "Zitrone"))) // List(Apfel, Banane, Zitrone)
```

## 3.4 Objekte nach Datum, Priorität und Titel sortieren
Die Funktion sortiert eine Liste von Aufgaben zuerst nach Datum, dann nach Priorität und zuletzt nach Titel.

```
case class Task(date: String, priority: Int, title: String)

def sortTasks(tasks: List[Task]): List[Task] = {
  tasks.sortBy(task => (task.date, task.priority, task.title))
}

val tasks = List(
  Task("2024-05-01", 2, "Task B"),
  Task("2024-04-01", 1, "Task A"),
  Task("2024-04-01", 3, "Task C")
)

println(sortTasks(tasks))
```

## 3.5 Blätter einer Baumstruktur extrahieren
Diese Funktion liest alle Blätter (Elemente ohne weitere Kinder) aus einer Baumstruktur und gibt sie als flache Liste zurück.

```
sealed trait Tree
case class Leaf(value: Int) extends Tree
case class Node(left: Tree, right: Tree) extends Tree

def collectLeaves(tree: Tree): List[Int] = tree match {
  case Leaf(value) => List(value)
  case Node(left, right) => collectLeaves(left) ++ collectLeaves(right)
}

val tree = Node(Node(Leaf(1), Leaf(2)), Leaf(3))
println(collectLeaves(tree)) // List(1, 2, 3)

```
