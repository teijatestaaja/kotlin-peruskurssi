[Tietoa kurssista](README.md) | [Osa 1](osa-1.md) | [Osa 2](osa-2.md) | [Osa 3](osa-3.md) | [Osa 4](osa-4.md) | [Osa 5](osa-5.md) | [Malliratkaisut](malliratkaisut/malliratkaisut.md) | [FAQ](faq.md)

# Osa 2: Muuttujat

## Oppimistavoitteet

- Tunnet käsitteen muuttuja. Tiedät mitä ovat muuttujan tyyppi, muuttujan nimi, ja muuttujan arvo.
- Osaat luoda ja käsitellä kokonaisluku-, liukuluku-, merkki-, merkkijono- ja totuusarvomuuttujia.
- Osaat tehdä yksinkertaisia laskutoimituksia.
- Osaat suorittaa ohjelmia Kotlin-hiekkalaatikossa.

Ohjelmointikielissä muuttujalla tarkoitetaan eräänlaista tietovarastoa, johon voidaan säilöä tietoa. Muuttuja voi viitata lähes minkä tyyppiseen tietoon tahansa. Kaikki tietokoneohjelmat, työpöytäsovellukset, www-sovellukset ja mobiilisovellukset säilövät jonkinlaista tietoa. Esimerkiksi mobiilisovellus, johon kirjaudutaan sisälle voi tallentaa kirjautumistapahtumasta monenlaista tietoa sisäisiin muuttujiinsa.

Muuttujalle tulee aina antaa nimi, ja muuttujaan asetetaan arvo yhtäsuuruusmerkillä. Kotlinissa muuttuja voidaan määritellä usealla eri tavalla. Yksi esimerkki muuttujasta:

```text
val luku = 2
```

Yllä on määritelty luku-niminen muuttuja, jolle on asetettu arvoksi 2.

## Muuttujan määrittely

Kotlin-ohjelmointikielessä voidaan määritellä minkä tyyppiseen tietoon muuttuja viittaa. Muuttujan tyyppi määrää arvot, joita muuttuja voi saada. Kotlinissa muuttujan perustyyppejä ovat esimerkiksi kokonaisluku (int), liukuluku (Double) eli desimaaliluku, merkkimuuttuja (Char), teksti eli merkkijono (String) tai totuusarvo (Boolean):

```kotlin
val x: Int = 100            // kokonaislukumuuttuja
val x: Double = 5.0         // liukulukumuuttuja
val x: Char = 'k'           // merkkimuuttuja
val x: String = "kissa"     // merkkijonomuuttuja
val x: Boolean = true       // totuusarvomuuttuja
```

Koska Kotlin on staattisesti tyypitetty ohjelmointikieli, on jokaisella muuttujalla oltava määritelty tyyppi. Kotlin osaa tunnistaa joitakin muuttujan tyyppejä automaattisesti ohjelman kääntämisen aikana, joten perustyypin muuttujille tyypin antaminen on vapaaehtoista:

```kotlin
val x = 100                 // kokonaislukumuuttuja
val x = 5.0                 // liukulukumuuttuja
val x = 'k'                 // merkkimuuttuja
val x = "kissa"             // merkkijonomuuttuja
val x = true                // totuusarvomuuttuja
```

Kotlinissa muuttujilla on ns. vahva tyypin päättely, eli aiemmin määritelty muuttuja ei saa viitata muun kaltaiseen tietoon. Seuraava muuttujien määrittely aiheuttaa virheen:

```kotlin
val x = 100
val x = "kissa"
```

Vaikka muuttujan tyyppi voidaan aina ilmoittaa, kuten edellä nähtiin, Kotlinissa jätetään yleensä tyypin päättely kääntäjän tehtäväksi. Seuraavissa muuttujien määrittelyissä määritellään kaksi kokonaislukutyyppistä muuttujaa a ja b, joiden molempien arvo on 1:

```kotlin
val a = 1
val b: Int = 1
```

## Val ja Var

Kotlinissa muuttujat jaetaan muuttumattomiin ja muuttuviin muuttujiin. Muuttumattomat muuttujat esitellään avainsanalla *val*:

```kotlin
val luku = 2
```

Muuttuvat muuttujat esitellään avainsanalla *var*:

```kotlin
var luku = 4
```

Edellä olevien muuttujien erona on se, että muuttumattomat muuttujat ovat vain tiedon lukemista varten, eli kun muuttumattomaan muuttujaan on asetettu arvo, sitä ei voi muuttaa, ainoastaan lukea. Jos val-avainsanalla määriteltyyn muuttujaan yritetään myöhemmin asettaa joku toinen arvo, Kotlin-kääntäjä ilmoittaa virheestä:

```kotlin
val x = 2
x = 4    // tuloksena virhe
```

Var-avainsanalla määritellyn muuttujan arvon muuttaminen jälkikäteen onnistuu sen sijaan ilman virheitä:

```kotlin
var x = 4
x = 6    // Onnistuu
```

Kotlinissa muuttujien ei tarvitse olla muuttumattomia, vaikka sitä suositellaankin. Eli mikäli mahdollista, esittele muuttujat aina mieluummin val-avainsanaa käyttäen. Seuraavassa muuttujien erilaisia tyyppejä esitellään hieman tarkemmin.

## Kokonaisluku- ja liukulukumuuttujat

Kotlinissa kokonaislukuja varten on neljä tyyppiä, jotka ovat erikokoisia ja joiden arvoalueet vaihtelevat. Kokonaisluvuille varatut tyypit ovat Byte, Short, Int ja Long. Lähtökohtaisesti kuitenkin kaikilla muuttujilla, jotka on alustettu kokonaislukuarvoilla ja jotka eivät alita tai ylitä kokonaislukualueen enimmäisarvoja (-2147483648 ja 2147483647), on johdettuna tyyppinä Int:

```kotlin
val luku = 1000           // Int-tyyppinen muuttuja
val toinenLuku = 10000    // Int-tyyppinen muuttuja
```

Mikäli muuttujan arvo ylittää kokonaislukualueen enimmäisarvon, tunnistaa Kotlin-kääntäjä muuttujan automaattisesti Long-tyyppiseksi. Tavutietotyypit Byte ja Short voivat olla hyödyllisiä tilanteissa, joissa pyritään mahdollisimman vähäiseen muistin käyttöön ja joissa muistin säästöillä on todella merkitystä. Niitä voidaan käyttää myös Int-tyypin sijasta silloin, kun käytettyjen tavutietotyyppien minimi- ja maksimirajat auttavat selventämään koodia. Muuten ohjelmoija pärjää varsin pitkälle Int-tyypin kokonaisluvuilla.

Liukuluku- eli desimaalityyppinen luku määritellään Double-tyyppiseksi muuttujaksi:

```kotlin
val luku = 10.0
val luku : Double = 10.0
```

Liukuluku- eli desimaalityyppisiä lukuja varten Kotlinissa on itseasiassa kaksi tietotyyppiä, Float ja Double. Liukulukutyypit eroavat toisistaan siinä, kuinka monta desimaalinumeroa ne voivat tallentaa. Kotlin-kääntäjä olettaa automaattisesti kaikkien liukulukujen olevan ns. kaksoistarkkuuden Double-tyyppisiä.
Tällä kurssilla käytetään ainoastaan Int-tyyppisiä kokonaislukumuuttujia ja Double-tyyppisiä liukulukumuuttujia. Katsotaanpa seuraavaksi, miten luvuilla suoritetaan laskutoimituksia.

## Laskutoimitukset kokonaisluku- ja liukulukumuuttujilla

Kotlin tukee aritmeettisten toimintojen vakiojoukkoa luvuille. Luvuille voidaan tehdä seuraavat operaatiot:

\+ yhteenlasku\
\- vähennyslasku\
\* kertolasku\
/ jakolasku\
% jakojäännös

Laskentajärjestys on tuttu: laskenta tehdään vasemmalta oikealle sulut huomioon ottaen. Kuitenkin * ja / lasketaan ennen + ja - operaatioita
Lukuja voidaan laskea yhteen seuraavasti:

```kotlin
val eka = 10
val toka = 4
val summa = eka + toka
print(summa)
```

Tulostaa näytölle

```text
Summa = 14
```

Vähennys- ja kertolasku tehdään vastaavaan tapaan.

Jakolasku on hieman hankalampi operaatio. Kotlinissa kahden luvun jakolasku tuottaa aina kokonaisluvun:

```kotlin
val eka = 10
val toka = 4
val tulos = eka / toka
print("Tulos = " + tulos)
```

Tulostaa näytölle

```text
Tulos = 2
```

Sen sijaan jos jakolaskun jakaja tai jaettava (tai molemmat) ovat liukulukuja, tulee tulokseksi myös liukuluku:

```kotlin
val eka = 10.0
val toka = 4.0
val tulos = eka / toka
print("Tulos = " + tulos)
```

Tulostaa näytölle

```text
Tulos = 2.5
```

Myös kahden kokonaisluvun jakolaskusta saa oikean lopputuloksen, kun jaettava tai jakaja muunnetaan liukuluvuksi kertomalla se luvulla 1.0:

```kotlin
val eka = 10
val toka = 4
val tulos = eka / (toka * 1.0)
print("Tulos = " + tulos)
```

Tulostaa näytölle

```text
Tulos = 2.5
```

## Tehtävät kokonaisluku- ja liukulukumuuttujista

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

2.1 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/)\
Kirjoita ohjelma, joka laskee ja tulostaa kahden kokonaisluvun summan. Toisin sanoen, luo kaksi kokonaislukutyyppistä muuttujaa, ja laske niiden summa omaan muuttujaan. \
Lopuksi tulosta summa näytölle.

2.2 Kirjoita ohjelma, joka laskee ja tulostaa neliön pinta-alan, kun neliön sivun pituus on 10.0.

2.3 Kirjoita ohjelma, joka laskee ja tulostaa ympyrän pinta-alan, kun ympyrän säde on 10.0.

2.4 Kirjoita ohjelma, joka laskee lukujen 1-5 summan ja tulostaa sen näytölle.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Guru-tehtävä**

2.5 Kirjoita ohjelma, joka laskee lukujen 1-5 keskiarvon ja tulostaa sen näytölle.

## Merkki- ja merkkijonomuuttujat

Kotlinissa merkkimuuttuja (Char) määritellään käyttäen yksittäisiä lainausmerkkejä:

```kotlin
val merkki = 'A'
val merkki: Char = 'b'
```

Mikäli halutaan määritellä merkiksi yksittäinen lainausmerkki, tulee merkin edessä käyttää kenoviivaa \\

```kotlin
val merkki = '\''
```

Samalla tavalla toimitaan mm. seuraavien erikoismerkkien kanssa: ” \ $

Merkkijonomuuttujat (String) puolestaan määritellään käyttäen kaksinkertaisia lainasmerkkejä:

```kotlin
val merkkijono = "Kotlin-ohjelmointi on hauskaa!"
```

Merkkijonomuuttujia voidaan yhdistää toisiinsa + operaattoria käyttäen. Seuraavat komennot:

```kotlin
var merkkijono1 = "Kotlin-ohjelmointi"
var merkkijono2 = " on hauskaa!"
print(merkkijono1 + merkkijono2)
```

Tulostavat näytölle tekstin

```text
Kotlin-ohjelmointi on hauskaa!
```

Merkkijonomuuttujaan voi yhdistää myös muun tyyppisiä muuttujia. Seuraavat komennot:

```kotlin
var merkkijono: String = " vuonna Kotlin-ohjelmointia"
var vuosi: Int = 2021
print(merkkijono + vuosi)
```

Tulostavat näytölle tekstin

```text
Kotlin-ohjelmointia vuonna 2021
```

Kokonais- tai liukulukumuuttujan yhdistäminen merkkijonoon ei sen sijaan onnistu suoraan, sillä seuraava tuottaa virheilmoituksen:

```kotlin
var merkkijono: String = "Kotlin-ohjelmointia vuonna "
var vuosi: Int = 2021
print(vuosi + merkkijono)
```

Luvun ja merkkijonon yhdistämisen merkkijonoon saa toimimaan, kun muuntaa luvun merkkijonoksi niin sanottua toString() -funktiota käyttäen:

```kotlin
fun main() {
   var merkkijono: String = " vuonna Kotlin-ohjelmointia"
	var vuosi: Int = 2021
	print(vuosi.toString() + merkkijono)
}
```

Nyt näytölle tulostuu:

```text
2021 vuonna Kotlin-ohjelmointia
```

## Tehtävät merkki- ja merkkijonomuuttujista

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

2.6 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/)
Kirjoita ohjelma, joka tulostaa näytölle merkkijonon: Osaan ohjelmoida Kotlin-ohjelmointikielellä!

2.7 Kirjoita ohjelma, joka tulostaa näytölle merkin X.

2.8 Kirjoita ohjelma, joka luo merkkijonomuuttujan jonka arvo on Commodore, kokonaislukumuuttujan jonka arvo on 64 ja lopuksi tulostaa näytölle merkkijonon Commodore 64

2.9 Kirjoita ohjelma, joka tulostaa näytölle seuraavan tekstin kahdelle riville:

   ```kotlin
   Hän sanoi: "Kotlin-ohjelmointi on hauskaa!"
   ja lähti koodaamaan.
   ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Guru-tehtävä**

2.10 Kirjoita ohjelma, joka tulostaa näytölle seuraavan tulostuksen käyttäen merkkijonoja:

   ```kotlin
   10 + 5 = 15
   10 - 5 = 5
   10 * 5 = 50
   10 / 5 = 2
   10 % 5 = 0
   ```

## Totuusarvomuuttujat

Kuten muissakin ohjelmointikielissä, myös Kotlinissa on käytössä totuusarvomuuttuja (Boolean). Totuusarvomuuttujaan voi asettaa vain arvon true (tosi) tai false (epätosi):

```kotlin
val ehto = true;
val uusiehto = false;
```

Myös totuusarvomuuttujan voi esitellä sekä var että val-avainsanalla. Vain var-avainsanalla esitellyn muuttujan totuusarvo on muutettavissa:

```kotlin
   val ainaTosi = true
   println(ainaTosi)
    
   var muuttuvaArvo = true
   println(muuttuvaArvo)
   muuttuvaArvo = false
   println(muuttuvaArvo)
```

Edellä oleva tulostaa:

```kotlin
   true
   true
   false
```

## Yhteenveto

Tässä kurssin osassa käsiteltiin Kotlin-ohjelmointikielen muuttujia. Tutustuimme muuttumattomiin ja muuttuviin muuttujiin, kokonaisluku- ja liukulukumuuttujiin, merkki- ja merkkijonomuuttujiin sekä totuusarvomuuttujiin. Seuraavissa tehtävissä harjoittelet lisää muuttujien määrittelyä, käyttöä ja muuttujien arvojen tulostamista. Valitse tehtävistä mieleinen taso, voit toki halutessasi tehdä kaikki tehtävät.

## Tehtävät koko osiosta

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

2.11 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/)\
Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun main() {
       var teksti : Char = "Kotlin-kielen alkeisiin voi tutustua Kotlin Koans Online -sivustolla."
       print(teksti)
   }
   ```

   ja korjaa ohjelmaa siten, että ohjelma tulostaa ilman virheitä.

2.12 Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun main() {
       val x = 2
       println(x)
       x = 2 * x
       println(x)
   }
   ```

   ja korjaa ohjelmaa siten, että ohjelma tulostaa luvut 2 ja 4 allekkain

   ```text
   2
   4
   ```

2.13 Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun main() {
       var a = "a"
       var b = 'b'
       var c = 'c'
       print(abc)
   }
   ```

   ja korjaa ohjelmaa siten, että ohjelma tulostaa

   ```text
   abc
   ```

2.14 Kirjoita ohjelma, joka luo muuttujan, antaa sille arvon 100 ja tulostaa muuttujan. Tämän jälkeen ohjelma muuttaa saman muuttujan arvoksi 10 ja tulostaa muuttujan.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Guru-tehtävä**

2.15 Kirjoita ohjelma, joka laskee ja tulostaa seuraavien laskujen tulokset näytölle:

   ```text
   10 + 5 = 15
   10 - 5 = 5
   10 * 5 = 50
   10 / 5 = 2
   10 % 5 = 0
   ```

Kun olet saanut osan 2 tehtävät tehtyä, voit siirtyä [osaan 3](osa-3.md).
