# Kaskáda

Demoliční hra do prohlížeče (desktop s myší). Najdeš na mapě svůj dům, hra ho postaví podle skutečných
map a ty ho z první osoby rozebereš na cihly, prkna a peří.

## Jak hrát

- Po spuštění se ukáže mapa. Najdi adresu nebo klikni na svůj dům a dej **Bourat tento dům**.
- V editoru doladíš patra, střechu a barvy. Ke každé straně domu můžeš nahrát fotku stěny: přetáhneš
  4 rohy, tažením označíš okna a dveře a hra je vyřeže přesně tam, kde jsou na fotce.
- `W A S D` chůze, myš rozhlížení, levé tlačítko nářadí, `1`–`5` nebo kolečko výběr nářadí
- kladivo (omítka, cihly, dřevo), perlík (i beton), sbíječka (všechno, přesně), nálože (`E` odpálí), bourací koule
- `F` létání (mezerník nahoru, `C` dolů), `Esc` pauza

Zdi a stropy jsou z 10cm kostek (omítka navrchu, uvnitř cihla a beton). Nábytek je ze skutečných modelů
a rozpadá se po dílech podle materiálu: postel na rám, matraci a peřinu, ze které se vysype peří.
Dřevo se láme na úlomky a třísky, sedačka na molitan a potah, sklo a keramika na střepy, knihy na papíry,
květináč na hlínu a listí. Sud s výstražným znakem na půdě vybuchne. Vnitřek domu je vymyšlený,
mapa ho nezná.

V Česku si hra k domu sama dotáhne data ČÚZK: ortofoto (zem kolem domu, krytina střech, stromy, slunce podle
stínů na snímku), registr budov RÚIAN (druh konstrukce, číslo popisné) a výškopis (tvar, sklon a výška střechy,
výšky sousedů).

## Jak to běží

Jedna stránka `index.html` bez sestavování, vedle ní textury `tex/` a modely `models/`. Knihovny se načítají
z CDN (three.js r185, Rapier 0.19.3, záloha cannon-es 0.20.0, Leaflet 1.9.4 pro mapu). Stačí ji vystavit jako
statický web, třeba přes GitHub Pages (větev `main`, kořen).

Mapa a stažení budov fungují jen na normálním webu. V sandboxu (třeba náhled na claude.ai) se cizí servery
nenačtou a hra nabídne jen tlačítko na plnou verzi.

## Data a licence

- Mapa a budovy: © [přispěvatelé OpenStreetMap](https://www.openstreetmap.org/copyright), licence ODbL.
  Data se stahují až v prohlížeči hráče (Overpass API, hledání adres přes Nominatim) a nikam se neukládají.
- Ortofoto, RÚIAN a výškopis DMP 1G / DMR 5G: © [ČÚZK](https://cuzk.gov.cz), otevřená data CC BY 4.0, stahují se
  až v prohlížeči hráče ze služeb ags.cuzk.gov.cz.
- Textury v `tex/` a modely v `models/`: [Poly Haven](https://polyhaven.com), CC0 (seznamy v `tex/SOURCES.md`
  a `models/SOURCES.md`). Modely jsou rozdělené na díly a odlehčené v Blenderu.
- three.js (MIT), Rapier (Apache-2.0), cannon-es (MIT), Leaflet (BSD-2-Clause).
