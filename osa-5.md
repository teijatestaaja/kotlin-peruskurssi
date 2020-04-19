# Osa 5: Funktiot

## Oppimistavoitteet

- Tunnet käsitteet funktio, funktion parametri ja funktion paluuarvo.
- Osaat luoda funktioita pala palalta.
- Osaat luoda parametrillisia ja parametrittomia funktioita.
- Osaat luoda funktioita, jotka palauttavat arvon.
- Osaat kutsua funktioita pääohjelmasta että muiden funktioiden sisältä.

Tietokoneohjelmien ja erilaisten mobiili- ja www-sovellusten kaikki toiminnallinen koodi kirjoitetaan funktioihin. Jokaisen ohjelman lähdekoodista löytyy aina vähintäänkin main-funktio, jonka avulla ohjelma käynnistetään. Tätä kutsutaan yleensä pääohjelmaksi. Tämän kurssin ensimmäisessä osassa opimme, että Kotlinilla tehdyt ohjelmat vaativat toimiakseen ohjelmarungon, joka näyttää seuraavalta:

```kotlin
fun main() {
   // Tähän tulee koodi, jolla ohjelma käynnistetään
}
```

Tämä ohjelmarunko on itseasiassa funktio. Kotlinissa funktiot määritellään *fun*-avainsanan avulla. Avainsanaa seuraa aina funktion nimi, jonka perässä on tavalliset sulkeet. Funktion sisältämä koodi kirjoitetaan aina aaltosulkeiden sisään. Yllä oleva funktio ei sisällä koodia, ainoastaan kommenttimerkin. Voimme lisätä funktioon koodia:

```kotlin
fun main() {
   print("Hei koodari")
}
```

Nyt main-funktio tulostaa tekstin *Hei koodari* Kotlin-ohjelmointikielen valmiin *print*-funktion avulla. Kotlinissa on useita valmiita funktioita, joita ohjelmoija voi käyttää hyödykseen. Ohjelmoija voi myös kirjoitaa omia funktioita, joten katsotaanpa seuraavaksi miten funktioita kirjoitetaan eli määritellään Kotlinissa.

## Funktion osat

Ohjelmakoodissa olevat funktiot voivat suorittaa monenlaisia toimintoja tai laskea ja palauttaa jonkin arvon. Jotta funktio toimisi ja sitä voidaan kutsua muualta koodista, tulee funktio määritellä. Funktiossa on neljä tärkeää osaa:

- funktion nimi
- parametrit ja niiden tyypit
- paluuarvon tyyppi sekä
- varsinainen funktion sisältämä koodi.

Funktion runko näyttää siis seuraavalta:

```kotlin
fun funktionNimi(parametri: parametrinTyyppi): paluuarvonTyyppi {
   // funktion sisältämä koodi
}
```

Pureudutaan seuraavaksi funktiorungon osiin hieman tarkemmin. Jokaisella funktiolla tulee olla nimi. Kotlinissa funktiot nimetään ns. *camelCase*-tyylin avulla siten, että ensimmäinen sana kirjoitetaan pienellä ja loput alkavat isolla alkukirjaimella:

```kotlin
fun lisaaYksi() {

}
```

Seuraavaksi funktioon määritellään sen mahdollisesti käyttämät parametrit. Parametrit ovat funktiolle annettavia arvoja, joita käytetään funktion suorituksessa. Funktion parametrit määritellään funktion nimen jälkeen olevien sulkujen sisällä. Parametrista annetaan parametrin nimi ja parametrin tyyppi kaksoispisteellä erotettuna. Seuraavassa esimerkissä lisaaYksi-funktiolle on annettu yksi parametri, *Int*-tyyppinen parametri *luku*:

```kotlin
fun lisaaYksi(luku: Int) {

}
```

Seuraavaksi funktioon määritellään sen mahdollisesti palauttaman arvon tyyppi. Funktiot voivat palauttaa arvoja sille ohjelmanosalle, jossa funktiota kutsuttiin. Tällöin paluuarvon tyyppi tulee olla määriteltynä funktioon, jotta kutsuva ohjelmanosa osa käsitellä saamaansa dataa oikein. Seuraavassa esimerkissä lisaaYksi-funktiolle on annettu paluuarvon tyypiksi kokonaisluku (*Int*). Funktio siis palauttaa kokonaisluvun.

```kotlin
fun lisaaYksi(luku: Int): Int {

}
```

Lopuksi funktiolle lisätään koodi, joka funktion tulee suorittaa. Funktion lähdekoodi kirjoitetaan aaltosulkeiden sisälle. Lähdekoodi voi sisältää esimerkiksi muuttujia, ehto- tai valintalauseita, toistolauseita tai kutsuja muihin funktioihin. Seuraavassa esimerkissä lisaaYksi-funktiolle on kirjoitettu lähdekoodi, jossa parametrissa annetusta luvusta luodaan uusi luku lisäämällä lukuun yksi. Lopuksi uusi luku palautetaan funktion paluuarvona *return*-avainsanan avulla:

```kotlin
fun lisaaYksi(luku: Int): Int {
   val uusiLuku = luku + 1
   return uusiLuku
}
```

Nyt funktio palauttaa parametrina annetun luvun lisättynä yhdellä. Sama lähdekoodi voitaisiin kirjoittaa vielä yksinkertaisemmin:

```kotlin
fun lisaaYksi(luku: Int): Int {
   return luku + 1
}
```

Funktioita siis kirjoitetaan pala palalta. Yleensä yksi funktio hoitaa vain yhtä asiaa, eli esimerkiksi jonkun arvon laskemista, arvon tarkastamista, arvon muokkaamista tai tulostamista.

Funktion ei tarvitse välttämättä palauttaa mitään arvoa. Funktioon ei myöskään välttämättä tarvitse määritellä parametreja. Seuraava on esimerkki funktiosta, jossa ei ole mitään parametreja eikä se palauta mitän arvoa:

```kotlin
fun tulosta() {
    print("Hei!")
}
```

## Funktion kutsuminen

Funktiota kutsutaan kirjoittamalla ohjelmanosaan (esimerkiksi main-funktioon) funktion nimi sekä antamalla sille funktion mahdollisesti vaatimat parametrit. Yllä olevaa esimerkkifunktiota voidaan kutsua pääohjelmassa seuraavasti:

```kotlin
fun main() {
   val luku = 10
   val paluuarvo = lisaaYksi(luku)
   print("Uusi luku on " + paluuarvo)
}
```

Esimerkissä määritellään ensin kokonaislukutyyppinen luku-muuttuja, jonka arvo on 10. Seuraavaksi kutsutaan lisaaYksi-funktiota siten, että funktion palauttama kokonaislukuarvo otetaan talteen paluuarvo-nimiseen muuttujaan. Lopuksi saatu arvo tulostetaan näytölle.

Funktioita voidaan kutsua myös toisesta funktiosta. Muistamme, että Kotlinissa myös pääohjelma on funktio, joten siinä kutsutaan usein funktiota funktion sisällä. Seuraavassa esimerkissä main-funktiossa kutsutaan valmista print-funktiota:

```kotlin
fun main() {
   print("Hei koodari")
}
```

Myös itse tehdystä funktiosta voidaa kutsua joko valmiita funktioita, tai muita itse tehtetyjä funktioita. Seuraavassa esimerkissä main-funktiosta kutsutaan itse tehtyä tulostaTulos-funktiota. Tulosta funktiossa kutsutaan valmista *print*-funktiota, sekä itse tehtyä laskeSumma-funktiota.

```kotlin
fun laskeSumma(a: Int, b: Int) : Int {
    return a + b
}

fun tulostaTulos() {
    print("Summa on " + laskeSumma(1, 2))
}

fun main() {
    tulostaTulos()
}
```

## Tehtävät

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

1. Mitä seuraava funktio tekee?

   ```kotlin
   fun omaLaskuri() {
      var tulo = 1;
      for (luku in 1..5) {
         tulo = tulo * luku
      }
      print(tulo)
   }
   ```

2. Mitä seuraava funktio tekee?

   ```kotlin
   fun laske(luku: Int, toinenLuku: Int) : Int {
      if (luku > toinenLuku) {
         return luku - toinenLuku
      } else if (toinenLuku > luku) {
         return toinenLuku - luku
      }
      return 0
   }
   ```

3. Mitä seuraava funktio tekee?

   ```kotlin
   fun muuta(nimi : String) : String {
      return nimi.capitalize()
   }
   ```

4. Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/)\
Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun toinenOmaFunktio(x: Int) : Int{
      return x * 2
   }

   fun omaFunktio(y: Int) {
      for (x in 1..3) {
         println(toinenOmaFunktio(y))
      }
   }

   fun main() {
      toinenOmaFunktio(5)
   }
   ```

   ja korjaa ohjelmaa siten, että ohjelma tulostaa luvun 10 kolme kertaa allekkain.

5. Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun laske(a: Int, b: Int) {
      val tulos = a + b
   }

   fun main() {
      val a = 10
      val b = 4
      val erotus = laske(a, b)
      print("Lukujen " + a + " ja b " + b + " erotus on " + erotus)
   }
   ```

   ja korjaa funktiota siten, että ohjelma tulostaa tekstin *Lukujen erotus on 6.
6. Kirjoita funktio, joka ei saa mitään parametreja ja joka laskee ja tulostaa kaikki kolmella jaolliset luvut väliltä -30...30
7. Kirjoita funktio, joka saa parametrinaan kaksi kokonaislukua ja joka tulostaa näiden erotuksen.
8. Kirjoita funktio, joka tulostaa näytölle parametrinaan saamistaan kahdesta luvusta suurimman.
9. Kirjoita funktio, joka tarkasta oliko parametrina saatu luku positiviinen. Jos oli, funktio palauttaa merkkijonon "positiivinen". Muutoin palauttaa merkkijonon "negatiivinen".

   **Guru-tehtävä**
10. Kirjoita funktio, joka saa parametrinaan kokonaisluvun ja joka tulostaa kyseisen luvun käänteisluvun näytölle.

Hienoa! Nyt olet suorittanut kurssin loppuun. Seuraavaksi voit suorittaa Kotlin jatkokurssin, joka on tulossa kesällä 2020 :)
