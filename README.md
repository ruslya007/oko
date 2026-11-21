# Silniční oko (pilot)

Webová aplikace, která přes kameru telefonu rozpoznává objekty, odhaduje rychlost projíždějících vozidel a analyzuje činnost člověka. Vše běží v prohlížeči, nic se neodesílá.

- `index.html` – v0.1: detekce objektů (COCO-SSD, 80 tříd) a rychlost mezi dvěma branami
- `v2/` – v0.2: 3D odhad rychlosti podle výšky vozu, galerie vozidel, učení z potvrzených modelů
- `v3/` – v0.3: přepínání kamer, nahrávání, analýza činnosti člověka (pozice, pád, gesta, chůze) s učením z potvrzení
- `v4/` – v0.4: klepnutí nebo obtažení neznámého předmětu ve videu, návrhy názvu (moje databáze, vozidla, detektor, ImageNet), vlastní databáze naučených věcí, hledání a automatický sběr vzorků
- `v5/` – v0.5: HUD nad videem (moje rychlost z GPS, souřadnice, ulice a orientační bod z OpenStreetMap), okraje silnice, jízdní pruhy, zvýraznění překážek, připočtení vlastní rychlosti k rychlostem ostatních
- `v6/` – v0.6: tři režimy (Doma, Jedu autem, Ochrana perimetru), lepicí zmenšitelné okno videa, automatické hledání linií, hlídání pohybu s nahráváním klipů, databáze událostí s hodnocením a CSV

Kamera funguje jen přes HTTPS. Rychlosti jsou orientační a nemají právní váhu; analýza činnosti není zdravotnický prostředek.

- **v0.7** (`/v7/`): učení klepnutím do videa je ve výchozím stavu vypnuté (zapíná se zaškrtnutím); gesta rukou – OK, palec nahoru/dolů, prostředník, V, pěst, dlaň, ukazování, rohy, modlitba, signál o pomoc (dlaň s palcem dovnitř → pěst); události s potvrzením a učením z oprav.
- **v0.8** (`/v8/`): SPZ (OCR, zkušebně), rysy postav pro opakované rozpoznání a alarm e-mailem (mail.php).
- **v0.9** (`/v9/`): režimy Řidič a Dohled; robustnější měření rychlosti projíždějících aut; zápis přestupků (rychlost, čára, protisměr) s fotem a videem.
- **v0.10** (`/v10/`): Dohled pěšky/za jízdy, přestupky s přesným časem, GPS a adresou, směr jízdy, přejetí čar i při pohybu, pozorování vozidel, záložka Přehled funkcí.
- **v0.11** (`/v11/`): semafor (červená/oranžová/zelená, jízda na červenou přes stop čáru), dopravní značky (omezení rychlosti OCR, STOP, dej přednost, hlavní silnice, zákaz vjezdu), varování řidiče.
- **v0.12** (`/v12/`): vlastní rychlost z pozadí (pohled shora na silnici, korelace posunu) + ruční zadání a kalibrace, takže rychlost aut před vámi je absolutní, ne relativní; přísnější neznámé překážky (stín a skvrny se ignorují, vypnuto ve výchozím stavu); poplach překážky jako průhledné červené označení přímo ve videu.
- **v0.13** (`/v13/`): detektor YOLOX (nano/tiny/s, ONNX Runtime Web, licence Apache 2.0) vedle COCO-SSD, volba „obě“ spojí výsledky; váhy modelů jsou v `oko/models/` (jen v repozitáři nase-tv-web).
- **v0.14** (`/v14/`): hledání silnice a jízdních pruhů neuronovou sítí YOLOP (licence MIT, 320 nebo 640) místo odhadu podle barvy; ONNX Runtime Web se načítá z vlastního serveru (`models/ort/`), běží ve vlákně na pozadí.
