# Kaskáda

Fyzikální demoliční hra do prohlížeče (desktop s myší). Prakem a náložemi boříš věže i vlastní čtvrť
postavenou z OpenStreetMap. Skóre rány se počítá jako **body × násobič**: sklo a TNT zvedají násobič
a jedna dobrá rána spustí řetězovou reakci.

## Jak hrát

- Myší míříš, podržením natáhneš prak, puštěním vystřelíš.
- Mezerník přepne přímou a obloukovou dráhu, `R` postaví úroveň znovu, `M` vypne zvuk.
- **Moje místo:** najdi adresu nebo klikni do mapy na svůj dům a dej *Postavit toto místo*. Budovy se
  stáhnou z OpenStreetMap a postaví z bloků. Pravým tlačítkem položíš nálož (máš 5), klávesa `D` je
  odpálí postupně za sebou. Na konci uvidíš, kolik procent čtvrti padlo.

## Jak to běží

Jedna stránka `index.html` bez sestavování. Knihovny se načítají z CDN (three.js r185, Rapier 0.19.3,
záloha cannon-es 0.20.0, Leaflet 1.9.4 pro mapu). Stačí ji vystavit jako statický web, třeba přes
GitHub Pages (větev `main`, kořen).

Výběr na mapě a automatické stažení budov fungují jen na normálním webu. Uvnitř sandboxu (třeba
artefakt na claude.ai) se cizí servery nenačtou a hra místo mapy nabídne nahrání souboru `map.osm`
z exportu na openstreetmap.org.

## Data a licence

- Mapa a budovy: © [přispěvatelé OpenStreetMap](https://www.openstreetmap.org/copyright), licence ODbL.
  Data se stahují až v prohlížeči hráče (Overpass API, hledání adres přes Nominatim) a nikam se neukládají.
- Textury v `tex/`: [Poly Haven](https://polyhaven.com), CC0 (seznam v `tex/SOURCES.md`).
- three.js (MIT), Rapier (Apache-2.0), cannon-es (MIT), Leaflet (BSD-2-Clause).
