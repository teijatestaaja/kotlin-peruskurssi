[Tietoa kurssista](README.md) | [Osa 1](osa-1.md) | [Osa 2](osa-2.md) | [Osa 3](osa-3.md) | [Osa 4](osa-4.md) | [Osa 5](osa-5.md) | [Yhteenveto](yhteenveto.md) | [Malliratkaisut](malliratkaisut/malliratkaisut.md) | [FAQ](faq.md) | [Sanasto](sanasto.md)

# Osa 1: Ohjelman rakenne

## Oppimistavoitteet

- Opit kirjoittamaan yksinkertaisen Kotlin-ohjelman, joka tulostaa tekstiä.
- Tutustut Kotlin-hiekkalaatikkoon.
- Osaat tulkita ja korjata ohjelman suorittamisessa aiheutuneita yksinkertaisia virheitä.
- Osaat kirjoittaa koodiin kommentteja.

Tietokoneohjelmat, puhelimen sovellukset tai selaimen kautta toimivat sovellukset näyttävät monenlaisia viestejä käyttäjälle. Esimerkiksi mobiilisovellus voi vaatia sisäänkirjautumisen, ja jos käyttäjä kirjoittaa salasanansa väärin, mobiilisovellus näyttää käyttäjälle virheilmoituksen puhelimen näytöllä.

[Kotlin-ohjelmointikielessä](https://kotlinlang.org/) tekstiä tulostetaan näytölle komennolla *print*:

```kotlin
print("Hei!")
```

Kotlinilla tehdyt ohjelmat vaativat toimiakseen ohjelmarungon eli ns. pääohjelman, joka näyttää seuraavalta:

```kotlin
fun main() {
  print("Hei maailma!")
}
```

Ohjelman suoritus alkaa riviä *fun main() {*
seuraavalta riviltä ja päättyy sulkevaan aaltosulkuun }. Ohjelmarungon sisällä olevat komennot suoritetaan yksi kerrallaan. Yllä olevassa ohjelmassa on vain yksi komento: *print("Hei maailma!")* ja komento tulostaa näytölle tulosteen:

```text
Hei maailma!
```

Huomaa, että toisin kuin useimmissa ohjelmointikielissä, Kotlin ei edellytä komentojen päättyvän puolipisteeseen. Puolipisteen lisäämisestä ei myöskään aiheudu virhettä. Puolipiste kuitenkin tarvitaan, jos samalla rivillä on useampi komento:

```kotlin
fun main() {
    print("Hei "); print("maailma!")
}
```

Tämä ei kuitenkaan ole kovin luettavaa koodia. Yleensä jokainen komento kirjoitetaan ohjelmakoodissa omalle rivilleen.

Komennolla println tulostetaan näytölle tekstiä, ja sen jälkeen rivinvaihto:

```kotlin
println("Hei")
println("maailma!")
```

Seuraava ohjelma tulostaa näytölle tekstin "Hei maailma!" sekä perään rivinvaihdon:

```kotlin
fun main() {
    println("Hei maailma!")
}
```

Yllä oleva ohjelmakoodi on itseasiassa valmis ohjelma. Ohjelmakoodin lisäksi tarvitaan kuitenkin aina jonkinlainen ohjelmointiympäristö tai hiekkalaatikko, jossa ohjelma voidaan käynnistää eli ajaa.

## Kotlin-hiekkalaatikko

[Kotlin Playground](https://play.kotlinlang.org/) on verkossa selaimen kautta toimiva niin sanottu hiekkalaatikko-ympäristö, jonka avulla voit tutkia ja harjoitella Kotlin-ohjelmointikielen perusteita ilman erillisen ohjelmointiympäristön asennusta tai tunnuksen luomista. Kotlin-hiekkalaatikossa voit ajaa turvallisesti koodinpätkiä sekä pieniä Kotlin-ohjelmia. Lisäksi voit selata koodinäytteitä suoraan selaimessa.

![Kotlin-hiekkalaatikko](kuvat/kotlin_playground.PNG "Kotlin-hiekkalaatikko")

Ensimmäistä kertaa sivulle tultaessa hiekkalaatikko sisältää valmiin pääohjelman, ja sen sisältämää koodia voi muokata suoraan selainikkunassa. Pääohjelman voi suorittaa painamalla oikeassa laidassa näkyvää sinistä play-painiketta.

## Ohjelmakoodin kommentointi

Kotlin tukee sekä yksirivisiä (tai rivin lopussa olevia) koodikommentteja ja monirivisiä lohkokommentteja useimpien nykyaikaisten ohjelmointikielten tapaan. Yksirivisen kommentin voi kirjoittaa käyttäen kahta vinoviivaa:

```kotlin
fun main() {
    // tulostetaan näytölle tekstiä
    println("Hei maailma!")
}
```

Kommentteja ei koskaan tulosteta, vaan niiden avulla dokumentoidaan usein muuten vaikeaselkoista koodia. Kommentin voi myös asettaa koodirivin loppuun:

```kotlin
fun main() {
    println("Hei maailma!")    // tulostetaan näytölle tekstiä
}
```

Monirivinen lohkokommentti kirjoitetaan käyttäen vinoviivaa ja tähteä seuraavasti:

```kotlin
/* pääohjelmarunko */
fun main() {
    println("Hei maailma!")
}
```

## Yhteenveto

Tässä kurssin ensimmäisessä osassa käsiteltiin näytölle tulostamista Kotlinin standardikirjaston *print()* ja *println()* -funktioiden avulla. Lisäksi tutustuttiin pääohjelman käsitteeseen sekä Kotlin-hiekkalaatikkoon. Seuraavissa tehtävissä harjoittelet itse Kotlin-hiekkalaatikossa näytölle tulostamista. Kokeile rohkeasti, virhetilanteen sattuessa saat palattua lähtötilanteeseen, kun poistat kaiken tekstin hiekkalaatikosta ja lisäät tilalle tyhjän pääohjelmarungon

```kotlin
fun main() {
    
}
```

## Tehtävät

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

1.1 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/) Käynnistä eli aja hiekkalaatikossa näkyvä valmis koodi. Mitä ohjelma tulostaa?
Lisää print-lauseen perään puolipiste ja aja ohjelma uudelleen. Mitä ohjelma tulostaa?

1.2 Muokkaa tulostusta siten, että ohjelma tulostaa koko nimesi.

1.3 Muokkaa tulostusta siten, että ohjelma tulostaa ensimmäiselle riville ”Hei” ja toiselle riville nimesi.

1.4 Alla olevassa ohjelmassa on virhe:

   ```kotlin
   fun main() {
       println("Ohjelmoidaan") print("Kotlinilla!")
   }
   ```

   Kopioi ja liitä ohjelmakoodi Kotlin-hiekkalaatikkoon. Korjaa ohjelmakoodia ja aja ohjelma siten, että se tulostaa tekstin kahdelle riville:

   ```text
   Ohjelmoidaan
   Kotlinilla!
   ```

   ![Guru](kuvat/star.png "Guru-tehtävä")&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Guru-tehtävä**

1.5 Alla olevassa ohjelmassa on virhe:

   ```kotlin
   fun main() {
       println("Kotlin-ohjelmointi on hauskaa ja helppoa!
   }
   ```

   Aja ohjelma Kotlin-hiekkalaatikossa ja korjaa virheet hiekkalaatikon antamien virheilmoitusten mukaan.

Kun olet saanut osan 1 tehtävät tehtyä, voit siirtyä [osaan 2](osa-2.md).

> (c) Teija Alasalmi 2021

> Kurssimateriaalin käyttäminen kaupallisiin tarkoituksiin tai opetusmateriaalina ilman lupaa on ehdottomasti kielletty!
