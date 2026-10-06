# Afbeeldingen

Zet hier de foto's uit het ontwerp neer. Zolang een bestand ontbreekt verwijdert
de pagina de `<img>` zelf (`onerror`) en blijft een rustig warm vlak staan in de
juiste verhouding, dus de layout verspringt niet.

| Bestandsnaam                 | Gebruikt voor                      | Verhouding | Nu       | Nodig voor 2× |
|------------------------------|------------------------------------|-----------|----------|---------------|
| `hotel-winselerhof.jpg`      | Achtergrond van de hero            | vrij      | 516×290  | 2880×760      |
| `wijnproeverij.jpg`          | Wijnproeverij voor twee            | 3:2       | 530×353  | 900×600       |
| `diner-wijnarrangement.jpg`  | niet meer in gebruik               | 3:2       | 372×234  | n.v.t.        |
| `drankpakket.jpg`            | Genot — wijn en champagne          | 3:2       | 310×143  | 700×467       |
| `late-checkout.jpg`          | Genot — late check-out             | 3:2       | 310×144  | 700×467       |
| `sauna.jpg`                  | Genot — privé sauna-slot           | 3:2       | 310×151  | 700×467       |
| `kasteel-hoensbroek.jpg`     | Activiteiten — Kasteel Hoensbroek  | 3:2       | 900×600  | voldoet       |
| `strijthagerbeekdal.jpg`     | Activiteiten — wandeling           | 3:2       | 900×600  | voldoet       |
| `fietsen-huren.jpg`          | Activiteiten — fietsen huren       | 3:2       | 900×600  | voldoet       |
| `bloemen-kamer.jpg`          | Genot — bloemen op de kamer        | 3:2       | 900×600  | voldoet       |
| `taart-kamer.jpg`            | Genot — taart op de kamer          | 3:2       | 900×600  | voldoet       |
| `ontbijt-kamer.jpg`          | Genot — ontbijt op de kamer        | 3:2       | 900×600  | voldoet       |

De huidige bestanden komen uit het ontwerp en zijn ongeveer 1×. De vier
aanbodfoto's staan er goed op, maar `hotel-winselerhof.jpg` is nu de
hero-achtergrond en wordt over de volle vensterbreedte uitgerekt: 516px bron op
1425px weergave, op retina zelfs 2850px. Die is zichtbaar zacht en heeft met
voorrang een origineel nodig van minimaal 2880px breed.

Tot dat origineel er is staat er een pleister in `index.html`: de hero-foto ligt
in een eigen laag (`.hero::after`) met een blur die meeschaalt met de
vensterbreedte (1,5px vanaf 900px, 3px vanaf 1300px, 5px vanaf 1700px). Dat
verbergt de pixelblokken. Zodra een scherpe bron beschikbaar is kunnen die drie
media queries weg.

De bronbestanden staan in `_bron/`. Ze hadden afgeronde hoeken ingebakken
(transparante pixels links); die zijn eraf gesneden voor de JPEG-conversie.

Budget: foto's ≈150 kB JPEG, transparant beeld als WebP (`cwebp -q 82 -alpha_q 90`).

# Fonts

De pagina verwacht de huisstijlfonts zelf gehost, zoals in de styleguide:

```
public/fonts/recoleta/Recoleta-Regular.ttf
public/fonts/recoleta/Recoleta-Medium.ttf
public/fonts/recoleta/Recoleta-SemiBold.ttf
public/fonts/recoleta/Recoleta-Bold.ttf
public/fonts/basis-grotesque/basisgrotesque-regular.ttf
public/fonts/basis-grotesque/basisgrotesque-medium.ttf
public/fonts/basis-grotesque/basisgrotesque-bold.ttf
```

Zolang die ontbreken valt de pagina terug op Georgia (kop) en de systeem-sans
(body). Geen externe CSS, dus geen Google Fonts.

## Herkomst en licentie van de bijgeplaatste foto's

Zes foto's zijn gezocht en toegevoegd voor de upsellsectie. **Alle zes staan
onder CC0 of publiek domein**: vrij voor commercieel gebruik, geen
naamsvermelding verplicht, geen doorgifteverplichting. Dat is bewust; CC BY en
CC BY-SA waren er ook, maar die dwingen zichtbare attributie af op een
verkooppagina en CC BY-SA besmet bovendien afgeleide bewerkingen.

| Bestand | Onderwerp | Licentie | Bron |
|---|---|---|---|
| `kasteel-hoensbroek.jpg`  | Kasteel Hoensbroek        | CC0 | Wikimedia Commons, `Heerlen-Kasteel Hoensbroek-1.JPG`, fotograaf Romaine |
| `strijthagerbeekdal.jpg`  | Strijthagerbeekdal        | CC0 | Wikimedia Commons, `Schaesberg-Strijthagerbeekdal (1).jpg`, fotograaf Romaine |
| `fietsen-huren.jpg`       | Fiets op een bospad       | CC0 | StockSnap, `vintage-bike-FCT8DXZBFQ` |
| `bloemen-kamer.jpg`       | Boeket op donker hout     | CC0 | StockSnap, `flower-table-KFLZ0EM2X5` |
| `taart-kamer.jpg`         | Punt taart op een bord    | CC0 | StockSnap, `cake-dessert-NYBRCP91R9` |
| `ontbijt-kamer.jpg`       | Koffie en croissant       | CC0 | StockSnap, `coffee-latte-MK3VLNK8NA` |

Alle zes zijn bijgesneden naar 3:2 en verkleind naar 900x600, JPEG kwaliteit 80,
progressief. Dat is 2x van de kaartbreedte op desktop en ruim 2x op mobiel.

De eerste twee zijn de werkelijke locaties, niet iets wat erop lijkt. Kasteel
Hoensbroek en het Strijthagerbeekdal liggen allebei echt binnen de reistijd die
op de kaart staat.

### Wat nog ontbreekt

- **Suite in de historische hoeve** (`kamerupgrade`). Hier staat bewust nog een
  beeldplek. Een willekeurige hotelkamer van een stockbank tonen bij een
  product dat een specifieke kamer in dit hotel verkoopt, is misleidend. Deze
  foto moet van Hotel Winselerhof zelf komen.
- **`hotel-winselerhof.jpg`** is nog steeds 516x290 en wordt als hero over de
  volle breedte uitgerekt. Daar staat nu een blur op als pleister. Ook deze
  moet van het hotel komen, minimaal 2880px breed.
- **`taart-kamer.jpg`** is de zwakste van de zes: er staat een hand in beeld en
  het bord is niet bijzonder. Vervangbaar zodra er iets beters is.

## Nieuw in v2 (aanbod van ViaLuxury zelf)

| Bestand | Bron | Licentie | Auteur | Bewerking |
|---|---|---|---|---|
| `wijngaard-limburg.jpg` | [Maastricht-Apostelhoeve (4)](https://commons.wikimedia.org/wiki/File:Maastricht-Apostelhoeve_(4).jpg) | CC0 | Romaine | Uitsnede 1170x780 uit 3840x2160, verkleind naar 900x600 |
| `wijnproeverij.jpg` | [Wine Tasting](https://stocksnap.io/photo/wine-tasting-T8FNYMYTHK) | CC0 1.0 | Kelly Ishmael | Uitsnede 530x353 uit de 960px-versie, niet opgeschaald |

CC0 vraagt geen naamsvermelding, dus er staat niets bij op de pagina.

Let op bij `wijnproeverij.jpg`: op het origineel staat het merk van een echt
wijnhuis leesbaar op de flessen. De uitsnede is daar precies op gekozen, zodat
er geen volledige merknaam meer in beeld staat. De CC0-licentie dekt de foto,
niet het merk, dus vervang dit beeld door een eigen foto van de wijngaard
waarmee we samenwerken zodra die er is. Het bestand is 530px breed en dus
alleen scherp op 1x; het is wel al scherper dan de foto die het vervangt.

## Twee bestanden zijn te klein

`sauna.jpg` is 310x151 en `diner-wijnarrangement.jpg` is 372x234. In v2 dragen ze
een kaart van 416px breed (thermaalbad) en 343px (restaurant). De eerste wordt
dus 1,3x opgeschaald en is zichtbaar zacht. De `width`/`height` in de HTML stond
bovendien op 900x600 voor beide; dat is nu gecorrigeerd naar de echte maten,
want een onjuiste maat is erger dan geen maat.

Verkoop je straks echt tickets voor Thermae 2000, dan levert die partner
beeldmateriaal. Dat is de goedkoopste oplossing en meteen de juiste locatie.
