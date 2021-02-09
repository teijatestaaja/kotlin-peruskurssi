[Etusivu](../README.md) | [Osa 1](../osa-1.md) | [Osa 2](../osa-2.md) | [Osa 3](../osa-3.md) | [Osa 4](../osa-4.md) | [Osa 5](../osa-5.md) | [Malliratkaisut](malliratkaisut.md) | [FAQ](../faq.md)

# Osa 3 Ehto- ja valintalauseet - malliratkaisut

Tehtävä 3.1

Ohjelma tulostaa: sopiva

Tehtävä 3.2

Ohjelma tulostaa: tiramisu

Tehtävä 3.3

```kotlin
fun main() {
    val x = 1

    if (x > 0) {
      print(x)
    }
}
```

Tehtävä 3.4

```kotlin
fun main() {
   val arvottu = true;
   if (arvottu) {
     print("Arvotaan luku")
   } else {
     print("Arvonta päättyi!")
   }
}
```

Tehtävä 3.5

```kotlin
fun main() {
   val luku = 2;
   if (luku < 0) {
     print("negatiivinen")
   } else {
     print("positiivinen")
   }
}
```

Tehtävä 3.6

```kotlin
fun main() {
    val luku = 5

    when (luku) {
      in 1..4 -> print("liian pieni")
      in 5..10 -> print("sopiva")
      else ->      {
          print("liian suuri")
      }
    }
}
```

Tehtävä 3.7

```kotlin
fun main() {
    val a = 5
    val b = 2

    if (a > 10 && b > 10) {
      print(a+b)
    } else {
      print(a*b)
    }
}
```

Tehtävä 3.8

```kotlin
fun main() {
    val luku = 3

    if (luku==3) {
      print("Peli päättyi!")
    }
}
```

Tehtävä 3.9

```kotlin
fun main() {
    val a = 10
    val b = 5

    if (b!=0) {
      print(a/b)
    }
}
```

Tehtävä 3.10

```kotlin
fun main() {
    val luku = 8

    if (luku % 2 == 0 && luku % 4 == 0) {
    	print("jaollinen 2:lla ja 4:lla")
    }
}
```