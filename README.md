# Kaskáda

Demoliční hra do prohlížeče (desktop s myší). Najdeš na mapě svůj dům, hra ho postaví podle skutečných
map a ty ho z první osoby rozebereš na cihly, prkna a peří.

## Jak hrát

- Po spuštění se ukáže mapa. Najdi adresu nebo klikni na svůj dům a dej **Bourat tento dům**.
- V editoru doladíš patra, střechu a barvy. Ke každé straně domu můžeš nahrát fotku stěny: přetáhneš
  4 rohy, tažením označíš okna a dveře a hra je vyřeže přesně tam, kde jsou na fotce.
- **Fotky z ulice:** kde jsou na [Panoramax](https://panoramax.xyz) (otevřená obdoba Street View) 360° fotky, hra je k domu
  sama stáhne, doladí jejich polohu podle obrysu střech proti výškopisu a sousedům dá skutečné fasády. Pro tvůj dům nabídne
  v „Fasády z fotek“ už narovnanou fotku strany, okna stačí označit. Pokrytí je zatím hlavně ve větších městech, nafotit
  může kdokoli.
- **Fotorealistické okolí ze skenu:** v aplikaci Scaniverse (zdarma, iPhone i Android) pomalu obejdi dům a kus ulice
  (krokem do strany, ne otáčením na místě), exportuj sken jako SPZ a přetáhni ho v editoru do pole „Okolí ze skenu“.
  Hra ho sama zarovná k domu a sousedům z mapy, skutečný dům ze skenu nahradí tím na bourání a vymyšlené okolí v dosahu
  skenu schová. Posuvníky (s pohledem shora) zarovnání doladíš. Sken zůstane uložený jen v tvém prohlížeči.
- `W A S D` chůze, myš rozhlížení, levé tlačítko nářadí, `1`–`6` nebo kolečko výběr nářadí
- kladivo (omítka, cihly, dřevo), perlík (i beton; podrž tlačítko a rána je silnější), sbíječka (všechno, přesně),
  nálože (`E` odpálí), bourací koule, pila (úzký řez skrz celou zeď: obkroužený kus vypadne)
- `F` létání (mezerník nahoru, `C` dolů), `Esc` pauza
- V kuchyni a na půdě stojí plynové lahve. Rána kladivem ulomí ventil: lahev syčí, vystřelí po podlaze a za pár
  vteřin bouchne. Výbuch odpálí lahve, sudy a nálože kolem, takže vzniknou řetězové reakce.
- Body se počítají za zbořený objem a za události (okna, nábytek, zřícení, výbuchy, řetězovky). Rychle za sebou
  jdoucí události zvedají násobič komba, velké řetězovky zpomalí čas. Na konci je hodnocení, nejbizarnější
  destrukce a rekord domu.

Okolní domy mají okna po patrech, dveře do ulice a střechy z leteckého snímku, kolem rostou skutečné stromy
(listnáče, jasany, ovocné stromy, smrky a břízy) tam, kde je hra najde na snímku a ve výškopisu. Ploty, zídky
a živé ploty stojí na hranicích pozemků do ulice podle katastru, podél silnic svítí lampy.

Zdi a stropy jsou z 10cm kostek (omítka navrchu, uvnitř cihla a beton). Nábytek je ze skutečných modelů
a rozpadá se po dílech podle materiálu: postel na rám, matraci a peřinu, ze které se vysype peří.
Dřevo se láme na úlomky a třísky, sedačka na molitan a potah, sklo a keramika na střepy, knihy na papíry,
květináč na hlínu a listí. Sud s výstražným znakem na půdě vybuchne. Vnitřek domu je vymyšlený,
mapa ho nezná.

V Česku si hra k domu sama dotáhne data ČÚZK: ortofoto (zem kolem domu, krytina střech, stromy, slunce podle
stínů na snímku), registr budov a parcel RÚIAN (druh konstrukce, číslo popisné, hranice pozemků pro ploty)
a výškopis (tvar, sklon a výška střechy, výšky sousedů, skutečný terén kolem domu až k obzoru).

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
- Stromy `models/strom_*.glb`: vygenerované knihovnou [ez-tree](https://github.com/dgreenheck/ez-tree) (MIT,
  © Daniel Greenheck, licence v `models/LICENSE-ez-tree.txt`).
- Fotky z ulice: autoři na [Panoramax](https://panoramax.xyz), CC BY-SA 4.0 (jména autorů hra ukáže v editoru a ve hře);
  stahují se až v prohlížeči hráče a nikam se neukládají.
- three.js (MIT), Rapier (Apache-2.0), cannon-es (MIT), Leaflet (BSD-2-Clause), Spark pro skeny (MIT, načte se jen se skenem).
