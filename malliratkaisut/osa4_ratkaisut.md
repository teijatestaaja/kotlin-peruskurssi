[Tietoa kurssista](../README.md) | [Osa 1](../osa-1.md) | [Osa 2](../osa-2.md) | [Osa 3](../osa-3.md) | [Osa 4](../osa-4.md) | [Osa 5](../osa-5.md) | [Malliratkaisut](malliratkaisut.md) | [FAQ](../faq.md)

# Osa 4 Toistolauseet - malliratkaisut

Tehtävä 4.1

Ohjelma tulostaa:
90
80
70
60
50

Tehtävä 4.2

Ohjelma tulostaa: 1098765483241

Tehtävä 4.3

Ohjelma tulostaa:
3
6
9

Tehtävä 4.4

```kotlin
fun main() {
    for (luku in 1..10 step 3) {
   		println(luku)
    }
}
```

Tehtävä 4.5

```kotlin
fun main() {
    var muuttuja = 1
    while(muuttuja < 10) {
        print(muuttuja)
        if (muuttuja % 2 == 0) {
            println(" on jaollinen kahdella")
        } else {
            println(" ei ole jaollinen kahdella")
        }
        muuttuja++
    }
}
```

Tehtävä 4.6

```kotlin
fun main() {
    var summa = 0
    for (i in 1..10) {
    	summa += i
    }
    println("Summa: " + summa)
}
```

Tehtävä 4.7

```kotlin
fun main() {
    var summa = 0
    for (i in 1..10) {
    	summa += i
    }
    println("Keskiarvo: " + summa*1.0/10)
}
```

Tehtävä 4.8

```kotlin
fun main() {
    for (i in 100 downTo 1) {
    	println(i)
    }
}
```

Tehtävä 4.9

```kotlin
fun main() {
    for (i in 1..5) {
    	println("Hei maailma!")
    }
}
```

Tehtävä 4.10

```kotlin
fun main() {
    for (i in 10..20 step 2) {
    	print(i.toString() + " ")
    }
}
```
