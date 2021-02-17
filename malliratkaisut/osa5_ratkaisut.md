[Etusivu](../README.md) | [Osa 1](../osa-1.md) | [Osa 2](../osa-2.md) | [Osa 3](../osa-3.md) | [Osa 4](../osa-4.md) | [Osa 5](../osa-5.md) | [Malliratkaisut](malliratkaisut.md) | [FAQ](../faq.md)

# Osa 5 Funktiot - malliratkaisut

Tehtävä 5.1

Funktio laskee luvun 5 kertoman 5! ja tulostaa sen näytölle.

Tehtävä 5.2

Jos funktiolle parametrina annetut luvut ovat erisuuret, funktio laskee ja palauttaa lukujen erotuksen siten, että suuremmasta luvusta vähennetään pienempi. Jos luvut ovat yhtäsuuret, funktio palauttaa 0.

Tehtävä 5.3

Funktio muuttaa parametrissa annetun nimen alkukirjaimen isoksi kirjaimeksi. Jos nimeä ei ole annettu, käytetään oletuspaluuarvoa "Tuntematon".

Tehtävä 5.4

```kotlin
fun toinenOmaFunktio(x: Int) : Int {
   return x * 2
}

fun omaFunktio(y: Int) {
   for (x in 1..3) {
      println(toinenOmaFunktio(y))
   }
}

fun main() {
   omaFunktio(5)
}
```

Tehtävä 5.5

```kotlin
fun laske(a: Int, b: Int): Int {
    return a - b
}

fun main() {
    val a = 10
    val b = 4
    val erotus = laske(a, b)
    print("Lukujen " + a + " ja " + b + " erotus on " + erotus + ".")
}
```

Tehtävä 5.6

```kotlin
fun kolmellaJaolliset() {
    for (i in -30..30) {
        if (i % 3 == 0 && i != 0) {
            println(i)
        }
    }
}

fun main() {
    kolmellaJaolliset()
}
```

Tehtävä 5.7

```kotlin
fun osamaara(jaettava: Int, jakaja: Int) {
    if (jakaja != 0) {
        print(jaettava * 1.0 / jakaja)
    } else print(0)
}

fun main() {
    osamaara(5, 2)
}
```

Tehtävä 5.8

```kotlin
fun suurempi(a: Int, b: Int): Int {
    if (a >= b) {
        return a
    } else return b
}

fun main() {
    print(suurempi(5, 15))
}
```

Tehtävä 5.9

```kotlin
fun tutkiLuku(x: Int): String {
    if (x > 0) {
        return "positiivinen"
    } else if (x < 0) {
        return "negatiivinen"
    } else return "nolla"
}

fun main() {
    println(tutkiLuku(2))
    println(tutkiLuku(-2))
    println(tutkiLuku(0))
}
```

Tehtävä 5.10

```kotlin
fun tulostaPienin(a: Int, b: Int, c: Int) {
    var pienin = a
    
    if (b < a) {
        pienin = b
    }
    
    if (c < b && c < a) {
        pienin = c
    }

    println(pienin)
}

fun main() {
    tulostaPienin(0, 2, 9)
    tulostaPienin(0, 9, 2)
    tulostaPienin(2, 0, 9)
    tulostaPienin(2, 9, 0)
    tulostaPienin(9, 0, 2)
    tulostaPienin(9, 2, 0)
}
```