[Tietoa kurssista](../README.md) | [Osa 1](../osa-1.md) | [Osa 2](../osa-2.md) | [Osa 3](../osa-3.md) | [Osa 4](../osa-4.md) | [Osa 5](../osa-5.md) | [Yhteenveto](../yhteenveto.md) | [Malliratkaisut](malliratkaisut.md) | [FAQ](../faq.md) | [Sanasto](../sanasto.md)

# Osa 2 Muuttujat - malliratkaisut

Tehtävä 2.1

```kotlin
fun main() {
    val a = 1
    val b = 2
    println("Summa: ${a + b}")
}
```

Tehtävä 2.2

```kotlin
fun main() {
    val sivu = 10.0
    println("Neliön pinta-ala: ${sivu * sivu}")
}
```

Tehtävä 2.3

Tässä tehtävässä voit hyödyntää [Kotlinin math-kirjastoa](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.math/), jos haluat käyttää piin tarkkaa arvoa. Voit myös luoda oman muuttujan arvolla 3,14.

```kotlin 
fun main() {
    val sade = 10.0
    println("Ympyrän pinta-ala: ${kotlin.math.PI * sade * sade}")
}
```

Tehtävä 2.4

```kotlin
fun main() {
    print(1+2+3+4+5)
}
```

Tehtävä 2.5

```kotlin
fun main() {
    print((1+2+3+4+5)/5)
}
```

Tehtävä 2.6

```kotlin
fun main() {
    print("Osaan ohjelmoida Kotlin-ohjelmointikielellä!")
}
```

Tehtävä 2.7

Tässä kohtaa voit käyttää tulostuksessa joko yksinkertaisia lainausmerkkejä (char-merkkimuuttuja) tai kaksinkertaisia lainausmerkkejä (string-merkkijonomuuttuja).

```kotlin
fun main() {
    print("X")
}
```

Tehtävä 2.8

```kotlin
fun main() {
    val merkki = "Commodore"
    val nro = 64
    print(merkki + " " + nro)
}
```

Tehtävä 2.9

Tässä tehtävässä voit käyttää kenoviivaa sekä lauseen sisältävien lainausmerkkien merkitsemiseen että rivinvaihdon tekemiseen erikoismerkillä \n

```kotlin
fun main() {
    val teksti = "Hän sanoi: \"Kotlin-ohjelmointi on hauskaa\"!\nja lähti koodaamaan."
    print(teksti)
}
```

Tehtävä 2.10

```kotlin
fun main() {
    println("10 + 5 = 15")
    println("10 - 5 = 5")
    println("10 * 5 = 50")
    println("10 / 5 = 2")
    println("10 % 5 = 0")
}
```

Tehtävä 2.11

```kotlin
fun main() {
    var teksti : String = "Kotlin-kielen alkeisiin voi tutustua Kotlin Koans Online -sivustolla."
    print(teksti)
}
```

Tehtävä 2.12

```kotlin
fun main() {
    var x = 2
    println(x)
    x = 2 * x
    println(x)
}
```

Tehtävä 2.13

```kotlin
fun main() {
    var a = "a"
    var b = "b"
    var c = "c"
    print(a+b+c)
}
```

Tehtävä 2.14

```kotlin
fun main() {
    var luku = 100
    println(luku)
    luku = 10
    println(luku)
}
```

Tehtävä 2.15

```kotlin
fun main() {
    val a = 10
    val b = 5
    println("$a + $b = ${a + b}")
    println("$a - $b = ${a - b}")
    println("$a * $b = ${a * b}")
    println("$a / $b = ${a / b}")
    println("$a % $b = ${a % b}")
}
```

> (c) Teija Alasalmi 2021

> Kurssimateriaalin käyttäminen kaupallisiin tarkoituksiin tai opetusmateriaalina ilman lupaa on ehdottomasti kielletty!