[Osa 1](osa-1.md) | [Osa 2](osa-2.md) | [Osa 3](osa-3.md) | [Osa 4](osa-4.md) | [Osa 5](osa-5.md)

# Osa 3: Ehto- ja valintalauseet

## Oppimistavoitteet

- Tunnet käsitteen ehtolause.
- Osaat luoda ehtolauseita, joiden avulla ohjelmaan saadaan vaihtoehtoista toimintaa.
- Tunnet ehtolauseissa tyypillisesti käytettävät vertailuoperaattorit ja loogiset operaatiot *ja*, *tai*, sekä *ei*.
- Tunnet käsitteen valintalause.
- Osaat luoda valintalauseita.

## Jos-ehtolause

Ehtolauseita tarvitaan kaikissa tietokoneohjelmissa, työpöytäsovelluksissa, mobiilisovelluksissa tai selaimella käytettävissä sovelluksissa. Ehtolauseiden avulla mihin tahansa ohjelmaan toteutetaan vaihtoehtoista toiminnallisuutta, eli toiminnallisuutta joka riippuu tavalla tai toisella ohjelmassa olevien muuttujien tilasta tai käyttäjän tekemistä valinnoista. Esimerkiksi käyttäjän kirjautuessa sisään mobiilisovellukseen voitaisiin käyttää seuraavaa jos-ehtolausetta:

**Jos** käyttäjän kirjoittama salasana oli oikea, käyttäjälle näytetään sovelluksen etusivulla Tervetuloa-teksti.

Tilannetta voidaan kuvata Kotlin-ohjelmalla yksinkertaistettuna seuraavasti:

```kotlin
val salasana = "123abc"

if (salasana.equals("123abc")) {
     print("Tervetuloa!")
}
```

Yllä oleva ohjelma tarkastaa ehtolauseessa olevan *equals*-komennon avulla, onko salasana-muuttujan sisältönä merkkijono 123abc. Tällöin ohjelma tulostaa näytölle *print*-komennon avulla tekstin:

```text
Tervetuloa!
```

Muiden ohjelmointikielten tapaan myös Kotlinissa ehtolause alkaa avainsanalla *if*, jota seuraa sulut () ja aaltosulkeet {}. Tyhjä ehtolauseen runko näyttää siis seuraavalta:

```kotlin
if () {

}
```

Ehtolauseessa sulkujen sisälle asetetaan lauseke, joka evaluoidaan kun ehtolause saavutetaan. Evaluoinnin tulos on totuusarvo. Sulkuja seuraa lohko, joka määritellään aaltosulkeiden sisään. Lohkon sisällä oleva lähdekoodi suoritetaan mikäli sulkujen sisälle asetettu lauseke evaluoidaan todeksi (true). Edellä esitetyssä esimerkissä

```kotlin
val salasana = "123abc"

if (salasana.equals("123abc")) {
     print("Tervetuloa!")
}
```

- ehtolauseen lausekkeena on *salasana.equals("123abc")* joka saa arvon tosi eli *true*
- lohkon sisällä oleva lähdekoodi on *print("Tervetuloa!")* joka suoritetaan ehtolauseen lausekkeen ollessa tosi

## Muuten-lause

Esimerkissämme käyttäjän kirjautuessa sisään mobiilisovellukseen voi tapahtua paitsi onnellinen loppu (pääsy etusivulle) tai vähemmän onnellinen loppu (kirjautuminen sovellukseen ei onnistu). Vaihtoehtoinen toiminta voitaisiin toteuttaa ns. muuten-lauseen avulla:

Jos käyttäjän kirjoittama salasana oli oikea, käyttäjälle näytetään sovelluksen etusivulla Tervetuloa! -teksti. **Muuten** näytetään virhe "Väärä salasana!".

Tilannetta voidaan jälleen kuvata Kotlin-ohjelmalla yksinkertaistettuna seuraavasti:

```kotlin
val salasana = "kissa"

if (salasana.equals("123abc")) {
  print("Tervetuloa!")
} else {
  print("Väärä salasana!")
}
```

Yllä oleva ohjelma tarkastaa ehtolauseessa olevan *equals*-komennon avulla, onko salasana-muuttujan sisältönä merkkijono 123abc. Koska salasana-muuttujan sisältönä onkin merkkijono kissa, ehtolauseen lauseke saa arvon epätosi (false). Ohjelman suoritus siirtyy muuten-lohkoon, jossa ohjelma tulostaa näytölle *print*-komennon avulla tekstin:

```text
Väärä salasana!
```

Kotlinissa muuten-lause alkaa avainsanalla *else*, jota seuraa aaltosulkeet {}. Tyhjä muuten-lauseen runko näyttää siis seuraavalta:

```kotlin
else {

}
```

Muuten-lauseessa suoritettava lähdekoodi kirjoitetaan aaltosulkeiden sisään. Lohkon sisällä oleva lähdekoodi suoritetaan mikäli jos-ehtolauseen lauseke evaluoidaan epätodeksi (false). Muuten-lauseketta ei suoriteta, jos jos-ehtolauseen lauseke evaluoidaan todeksi.

Kotlinissa on yksi erikoisuus esimerkiksi Java-ohjelmointikieleen verrattuna. Kotlinissa avainsanalla *if* määritelty ehtolause on myös ns. ilmaus (expression), joka palauttaa arvon. Tämän vuoksi ehtolauseen arvo voidaan sijoittaa muuttujaan:

```kotlin
val salasana = "123abc"

val viesti = if (salasana.equals("123abc")) "Tervetuloa!" else "Väärä salasana!"
print(viesti)
```

Esimerkissä sijoitetaan viesti-muuttujaan jos-ehtolauseen palauttama arvo. Koska salasana-muuttujan sisältö on merkkijono 123abc, ehtolause palauttaa tekstin *Tervetuloa!* joka asetetaan viestin-muuttujan arvoksi. Komennolla *print* viesti-muuttujan sisältö tulostetaan lopuksi näytölle.

## Loogiset operaatiot

Loogisia operaatioita käytetään ohjelmoinnissa erilaisissa ohjausrakenteissa ehtolauseiden osana. Loogisilla operaatioilla yhdistetyistä lausekkeista voidaan muodostaa monimutkaisempia ehtoja, jotka vastaavat sisäkkäisiä valintarakenteita. Kotlin-ohjelmointikielessä on käytössä seuraavat loogiset operaatiot:

| Operaatio | Luonnollisen kielen vastine | Käyttötarkoitus |
| ----------|----------|------------------|
| !         | ei       | Kääntää sitä seuraavan lausekkeen totuusarvon päinvastaiseksi. |
| &&        | ja       | Antaa totuusarvon tosi vain, jos jokainen operaatioon osallistuva yksittäinen lauseke on tosi. |
| \|\|      | tai      | Antaa totuusarvon tosi, jos yksikin operaatioon osallistuva lauseke on tosi. |

Seuraavassa !:lla eli ei-operaatiolla käännetään ehtolausekkeen arvo päinvastaiseksi. *Väärä salasana!* -viesti tulostetaan näytölle, jos salasana-muuttujan sisältö ei ole merkkijono 123abc

```kotlin
val salasana = "kissa"

if (!salasana.equals("123abc") ) {
  print("Väärä salasana!")
} else {
  print("Tervetuloa!")
}
```

Seuraavassa yhdistetään &&:lla eli ja-operaatiolla kaksi yksittäistä ehtoa. Lausekkeessa tulostetaan näytölle *Tervetuloa!* -teksti, jos kayttajatunnus-muuttujan sisältönä on merkkijono koodari, ja salasana-muuttujan sisältönä on merkkijono 123abc

```kotlin
val kayttajatunnus = "koodari"
val salasana = "123abc"

if (kayttajatunnus.equals("koodari") && salasana.equals("123abc") ) {
  print("Tervetuloa!")
}
```

Seuraavassa annetaan ||:n eli tai-operaation avulla kaksi vaihtoehtoa. *Virhe!* -teksti tulostetaan, jos kayttajatunnus-muuttujan arvo ei ole merkkijono koodari tai jos salasana-muuttujan arvo ei ole merkkijono 123abc. Lauseke siis toteutuu, jos jompi kumpi ehdoista toteutuu. Tässä virheteksti tulostetaan, koska salasana-muuttujan sisältö ei ole haluttu:

```kotlin
val kayttajatunnus = "koodari"
val salasana = "kissa"

if (!kayttajatunnus.equals("koodari") || !salasana.equals("123abc") ) {
  print("Virhe!")
}
```

Ehtolauseita voi myös ketjuttaa *else...if* avainsanoja käyttämällä. Yllä olevan koodin voisi kirjoittaa toisin seuraavasti:

```kotlin
val kayttajatunnus = "koodari"
val salasana = "kissa"

if (!kayttajatunnus.equals("koodari")) {
  print("Väärä käyttäjätunnus!")
} else if (!salasana.equals("123abc")) {
  print("Väärä salasana!")
} else {
  print("Tervetuloa!")
}
```

Nyt ohjelma tulostaa yksilöidymmän *Väärä salasana!* -virheen, sillä ohjelman suoritus päättyy salasanan tarkastukseen *else...if* -lohkossa. Viimeistä *else*-lohkoa ei siis suoriteta. Ketjutuksen etuna onkin se, että yhden ehdon toteutuessa muita ehtoja ei turhaan evaluoida.

## Vertailuoperaattorit

Ehtolauseissa voidaan käyttää monenlaisia vertailuoperaattoreita, kun halutaan vertailla esimerkiksi täyttääkö joku luku tietyn ehdon. Kotlinissa vertailuoperaattoreita ovat:

- <  pienempi kuin
- <= pienempi tai yhtä suuri kuin
- \>  suurempi kuin
- \>= suurempi tai yhtä suuri kuin
- == yhtä suuri kuin
- != erisuuri kuin

Seuraavassa on muutamia esimerkkejä vertailuoperaattoreiden käytöstä. Alla olevassa ohjelmakoodissa jos-ehtolauseen lauseke evaluoidaan todeksi, jos muuttujassa ika oleva arvo on suurempi tai yhtäsuuri kuin 18. Tällöin ohjelman suoritus siirtyy ehtolauseen määrittelemään lohkoon, ja näytölle tulostetaan teksti *Saat ajaa autolla*:

```kotlin
val ika = 18
if (ika >= 18) {
  print("Saat ajaa autolla")
}
```

Seuraavassa esimerkissä evaluoidaan jos-ehtolauseke epätodeksi, ja tulostetaan else-lauseessa näytölle teksti *Saat ajaa mopolla*:

```kotlin
val ika = 15
if (ika < 15) {
  print("Saat ajaa pyörällä")
} else {
  print("Saat ajaa mopolla")
}
```

Seuraavassa esimerkissä tutkitaan useampia lausekkeita ketjuttamalla lauseita *else...if* -avainsanoilla. Koska ika-muuttujan arvona on 18, suoritaan vasta viimeinen muuten-lause joka tulostaa näytölle tekstin *Saat ajaa autolla*:

```kotlin
val ika = 18
if (ika < 15) {
  print("Saat ajaa pyörällä")
} else if (ika >=15 && ika < 16) {
  print("Saat ajaa mopolla")
} else if (ika >=16 && ika < 18){
  print("Saat ajaa kevytmoottoripyörällä")
} else {
  print("Saat ajaa autolla")  
}
```

## Kun-valintalause

Kun-valintalauseen muoto on seuraava:

```kotlin
when (tähän_tulee_lauseke) {
    ehto_1 -> // Tähän tulee lähdekoodi
    ehto_2 -> // Tähän tulee lähdekoodi
    ...
    else -> {
              // Tähän tulee lähdekoodi
    }
}
```

Kun-lauseen suoritus alkaa siinä olevan lausekkeen arvon laskemisella. Sen jälkeen siirrytään siihen tapaukseen, josta löytyy arvoa vastaava vakiolauseke, ja suoritetaan siellä olevat lauseet. Jos arvo ei vastaa mitään vakiolauseketta, suoritetaan else-osan lauseet. Seuraavassa esimerkissä tutkitaan valinta-muuttujan arvoa. Valinnalla 1 ja 2 tulostaa niitä vastaavat tulosteet. Kaikilla muilla valinnoilla ohjelma tulostaa tekstin *tuntematon valinta*:

```kotlin
when (valinta) {
  1 -> print("valitsit 1")
  2 -> print("valitsit 2")
  else -> {
      print("tuntematon valinta")
  }
}
```

Edellä nähty ketjutettu if-lause ei välttämättä ole kovin hyvä tapauksissa, joissa valittavana on rajallinen määrä toisensa poissulkevia vaihtoehtoja.
kun-lause toimii tässä tapauksessa paremmin, koska koodista tulee luettavampaa:

```kotlin
val ika = 18
when (ika) {
   in 1..14 -> print("Saat ajaa pyörällä")
   15 -> print("Saat ajaa mopolla")
   in 16..17 -> print("Saat ajaa kevytmoottoripyörällä")
   else -> print("Saat ajaa autolla")
}
```

## Yhteenveto

Tässä kurssin osassa käsiteltiin ehto- ja valintalauseita Kotlin-ohjelmointikielessä. Tutustuimme jos-ehtolauseeseen, muuten-lauseeseen, loogisiin operaatioihin sekä vertailuoperaattoreihin. Lisäksi tutustuimme kun-valintalauseeseen Seuraavissa tehtävissä harjoittelet ehto- ja valintalauseiden analysointia, korjaamista sekä muodostamista.

## Tehtävät

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**Perustehtävät**

3.1 Mitä seuraava ohjelma tulostaa?

   ```kotlin
   val luku = 5
  
   if (luku < 5) {
     print("liian pieni")
   } else if (luku >= 5 && luku <=10) {
     print("sopiva")
   } else {
     print("liian suuri")
   }
   ```

3.2 Mitä seuraava ohjelma tulostaa?

   ```kotlin
   val valinta = 1
   val resepti = "jälkiruoka"
   if (valinta == 1) {
     if (resepti.equals("pääruoka") ) {
       print("lasagne")
     } else {
       print("tiramisu")
     }
   }
   ```

3.3 Mene selaimella Kotlin-hiekkalaatikkoon osoitteeseen [https://play.kotlinlang.org/](https://play.kotlinlang.org/) Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   fun main() {
     val x = 1

     if (x < 0) {
       print(x)
     }
   }
   ```

   ja korjaa ehtolausetta siten, että ohjelma tulostaa muuttujan x arvon.

3.4 Kopioi seuraava ohjelmakoodi hiekkalaatikkoon

   ```kotlin
   val arvottu = true;
   if (!arvottu) {
        print("Arvotaan luku")
   } else {
      print("Arvonta päättyi!")
   }
   ```

   ja korjaa ohjelmaa siten, että ohjelma tulostaa tekstin *Arvotaan luku*.

3.5 Kirjoita ohjelma, joka luo muuttujan ja asettaa sille alkuarvon väliltä 0-100. Tämän jälkeen ohjelma tarkastaa muuttujan arvon, ja jos arvo on pienempi kuin 0, tulostaa merkkijonon *negatiivinen*, muuten tulostaa merkkijonon *positiivinen*.

3.6 Kirjoita ohjelma, joka toteuttaa tehtävän 1 toiminnallisuuden käyttäen when-lausetta.

3.7 Kirjoita ohjelma, joka laskee ja tulostaa kahden luvun summan, jos molemmat luvut ovat suurempia kuin 0. Muuten ohjelma laskee ja tulostaa lukujen erotuksen.

3.8 Kirjoita ohjelma, joka tulostaa merkkijonon *Peli päättyi!*, jos muuttujan luku arvo on yhtä suuri kuin 3.

3.9 Kirjoita ohjelma, joka laskee ja tulostaa näytölle kahden luvun a ja b osamäärän, jos jaettava b on eri suuri kuin nolla.

   **Guru-tehtävä**

3.10 Kirjoita ohjelma, joka tarkastaa onko luku jaollinen luvulla 2 sekä luvulla 4. Jos luku on jaollinen 2:lla, ohjelma tulostaa merkkijonon *jaollinen 2:lla*. Jos luku on jaollinen 4:lla, ohjelma tulostaa merkkijonon *jaollinen 4:lla*. Jos luku on jaollinen sekä kahdella että 4:lla, ohjelma tulostaa merkkijonon *jaollinen 2:lla ja 4:lla*.

Kun olet saanut osan 3 tehtävät tehtyä, voit siirtyä [osaan 4](osa-4.md).
