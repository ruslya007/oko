# Silniční oko (pilot)

Webová aplikace, která přes kameru telefonu rozpoznává objekty, odhaduje rychlost projíždějících vozidel a analyzuje činnost člověka. Vše běží v prohlížeči, nic se neodesílá.

- `index.html` – v0.1: detekce objektů (COCO-SSD, 80 tříd) a rychlost mezi dvěma branami
- `v2/` – v0.2: 3D odhad rychlosti podle výšky vozu, galerie vozidel, učení z potvrzených modelů
- `v3/` – v0.3: přepínání kamer, nahrávání, analýza činnosti člověka (pozice, pád, gesta, chůze) s učením z potvrzení

Kamera funguje jen přes HTTPS. Rychlosti jsou orientační a nemají právní váhu; analýza činnosti není zdravotnický prostředek.
