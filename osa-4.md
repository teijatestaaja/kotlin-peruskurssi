[Etusivu](README.md) | [Osa 1](osa-1.md) | [Osa 2](osa-2.md) | [Osa 3](osa-3.md) | [Osa 4](osa-4.md) | [Osa 5](osa-5.md)

# Osa 4: Toistolauseet

## Oppimistavoitteet

- Tunnet käsitteen toistolause ja osaat luoda ohjelman, joka sisältää toistolauseen.
- Opit käyttämään while-toistolausetta.
- Opit käyttämään do..while-toistolausetta.
- Opit käyttämään for-toistolausetta.

Toistolauseiden avulla tietokoneohjelmiin, mobiilisovelluksiin tai www-sovelluksiin voidaan toteuttaa toiminnallisuutta, jota toistetaan niin kauan kun tietty lopetusehto toteutuu. Yksinkertainen mobiilisovellus, jossa mitataan aikaa on esimerkki toistettavasta toiminnallisuudesta: Aikalaskuri käynnistyy, kun käyttäjä painaa Aloita-painiketta. Tällöin laskuri käynnistyy ja mittaa kulunutta aikaa niin kauan, kunnes käyttäjä painaa pysäytä-painiketta.

 Kotlinissa on kolme eri tyyppiä olevia toistolauseita:

- while
- do..while
- for

## While-toistolause

Toistolause sisältää aina lausekkeen, jonka perusteella päätellään jatketaanko toistoa, sekä aaltosulkeilla merkatun lohkon, joka sisältää toistettavan lähdekoodin. *while*-toistolauseen muoto on seuraava:

```kotlin
while (tähän_tulee_lauseke) {
    // Tähän tulee toistettava lähdekoodi
}
```

Toistolauseen sisältämä lauseke määrä sen, miten kauan toistoa jatketaan. Seuraavassa esimerkissä toistolausetta suoritetaan ikuisesti, sillä toistolauseen lausekkeen arvo on aina tosi (*true*):

```kotlin
while (true) {
   println("Kotlin-ohjelmointi on kivaa!")
}
```

Toistolauseen saa päätettyä komennolla *break*:

```kotlin
while (true) {
   println("Kotlin-ohjelmointi on kivaa!")
   break;
}
```

Kun tietokone suorittaa komennon *break*, siirtyy ohjelman suoritus toistolauseen lohkoa seuraavaan komentoon. Nyt näytölle tulostetaan vain kerran seuraava viesti:

```text
Kotlin-ohjelmointi on kivaa!
```

Seuraavassa on esimerkki yksinkertaisesta while-toistolauseesta. Ohjelma tulostaa luvut 1-5, sillä toistolauseen ensimmäisen kierroksen jälkeen palataan uudestaan alkuun tutkimaan toteutuuko toistolauseen lauseke luku <= 5 :

```kotlin
var luku = 1           // alussa luku on 1
while (luku <= 5) {    // niin kauan kunnes käsiteltävä luku on pienempi tai yhtä pieni kuin 5
   print(luku)         // tulostetaan käsiteltävä luku
   luku++              // lisätään luku-muuttujan arvoa yhdellä
}
```

Toistolauseesta poistutaan esimerkiksi jos käyttäjä syöttää tietyn syötteen tai jos toistolauseessa tehtävä laskenta päätyy haluttuun lopputulokseen. Palataanpa aikalaskuri-esimerkkiin. Seuraavassa ohjelmassa määritellään toistolauseen sisällä käsiteltävät muuttujat ennen toistolauseen lohkoa. Sekunnit-muuttujaa kasvatetaan toistolausessa ja lausetta jatketaan niin kauan, kunnes sekunnit-muuttujan arvo on 60. Tällöin kaynnissa-muuttujan arvoksi muutetaan epätosi (*false*). Tämän jälkeen toistolauseesta poistutaan, koska uutta toistokierrosta aloittaessa kaynnissa-muuttujan arvona onkin *false*:

```kotlin
var kaynnissa = true
var sekunnit = 0
while (kaynnissa) {
   println(sekunnit)
   if (sekunnit == 60) {
      kaynnissa = false;
   }
   sekunnit++
}
```

Toistolauseen alkuun palataan siis silloin kun suoritus päätyy toistolauseen lohkon loppuun eli kun kaikki toistolauseen lohkossa olevat komennot on suoritettu. Toistolauseen alkuun voi palata myös muualta kuin toistolauseen lopusta erillisellä *continue*-komennolla. Seuraava ohjelma arpoo lukuja väliltä 1-5 ja tulostaa arvotun luvun arvon. Jos luku on muu kuin 5, hypätään takaisin toistolauseen alkuun ja arvotaan uusi luku. Jos arvottu luku oli 5, toistolauseen suoritus päättyy:

```kotlin
while (true) {
   var luku = kotlin.random.Random.nextInt(1, 6)
   print(luku)
   if (luku != 5) {
      continue
   } else break
}
```

## do..while -lause

*do..while*-toistolause on *while*-toistolauseen kaltainen. Lauseiden ero on se, että *do..while*-lausessa aaltosulkeiden sisällä oleva lähdekoodi suoritetaan aina ensin, ja lausekkeen evaluointi suoritetaan vasta sen jälkeen:

```kotlin
var luku = 1
do {
   print(luku)
   luku++
} while (luku <= 5)
```

## for-lause

*for*-toistolauseen muoto on seuraava:

```kotlin
for (muuttuja in arvoalue vapaaehtoinen_ehto) {
    // Tähän tulee toistettava lähdekoodi
}
```

Seuraavassa on yksinkertainen esimerkki, joka tulostaa luvut 1-5. Tässä *for*-toistolauseessa muuttuja luku saa arvon alueesta 1..5, eli joka kierroksella vuorotellen arvon 1, 2, 3, 4, 5:

```kotlin
for (luku in 1..5) {
   print(luku)
}
```

Luvut 1-5 voidaan tulostaa käänteisesti 5-1 käyttämällä *downTo*-funktiota:

```kotlin
for (luku in 5 downTo 1) {
   print(luku)
}
```

Seuraavassa esimerkissä tulostetaan luvut 1-5 pois lukien viimeinen luku 5 käyttämällä *until*-funktiota:

```kotlin
for (luku in 1 until 5) {
   print(luku)
}

*for*-toistolauseessa voidaan käyttää myös vapaaehtoisena ehtona funktiota, esimerkiksi *step*-funkiota tulostamaan lukuja tietyin välein. Seuraava ohjelma tulostaa kaikki parilliset luvut väliltä 1-10:

```kotlin
for (parillinen in 1..10 step 2) {
   print(parillinen)
}
```

Funktioihin palataan kurssin seuraavassa osassa.

## Yhteenveto

Tässä kurssin osassa käsiteltiin erilaisia toistolauseita, joita käytetään silloin, kun ohjelmaan halutaan tositettavaa toiminnallisuutta. Tutustuimme *while*, *do..while* sekä *for*-toistolauseisiin.

## Tehtävät

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

4.1 Mitä seuraava ohjelma tulostaa?

   ```kotlin
   fun main() {
      var luku = 100
	   while (luku > 10) {
   		if (luku > 50) {
      		luku = luku - 10
      		println(luku)
   		} else {
     		   luku = -1
   		}
	   }
   }
   ```

4.2 Mitä seuraava ohjelma tulostaa?

   ```kotlin
   fun main() {
      var tulos = 10
	   do {
         print(tulos)
         if (tulos == 2 || tulos == 4) {
            print(tulos*2)
         }
         tulos--
	   } while (tulos > 0)
   }
   ```

4.3 Mitä seuraava ohjelma tulostaa?

   ```kotlin
   fun main() {
      for (x in 1 until 12) {
         if (x % 3 == 0) {
            println(x)
         }
      }
   }
   ```

4.4 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/) Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   for (luku in 1..10) {
      println(luku)
   }
   ```

   ja korjaa toistolausetta siten, että ohjelma tulostaa allekkain luvut 1 4 7 10

4.5 Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun main() {
      var muuttuja = 1
      while(muuttuja < 10) {
         if (muuttuja > 0) {
            println("jaollinen kahdella")
         }
         muuttuja++
      }
   }
   ```

   ja korjaa toistolausetta siten, että ohjelma tulostaa muuttujan arvon sekä kahdella jaollisten lukujen kohdalla "on jaollinen kahdella", muuten "ei ole jaollinen kahdella".

4.6 Kirjoita ohjelma, joka laskee ja tulostaa näytölle lukujen 1-10 summan.

4.7 Kirjoita ohjelma, joka laskee ja tulostaa näytölle lukujen 1-10 keskiarvon.

4.8 Kirjoita ohjelma, joka laskee ja tulostaa näytölle luvut 1-100 käänteisessä järjestyksessä.

4.9 Kirjoita ohjelma, joka kirjoittaa 5 kertaa näytölle tekstin "Hei maailma!"

   **Guru-tehtävä**

4.10 Kirjoita ohjelma, joka tulostaa luvut 10 12 14 16 18 20

Kun olet saanut osan 4 tehtävät tehtyä, voit siirtyä tämän kurssin viimeiseen [osaan 5](osa-5.md).
