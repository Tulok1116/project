name: Galambos Bence
neptun: D0EWY6
id: 2026-NP-05
github: https://github.com/
github project: https://github.com/Tulok1116/project
---
# Egyedi 2D fizikai motor játékokhoz

A kétdimenziós merevtest-fizika a numerikus integrációt, az ütközések felismerését, a kontaktusok meghatározását és az ütközési választ egyetlen, egyszerre stabil és hatékony szimulációs folyamatba kapcsolja össze. A projekt célja egy kompakt, saját 2D fizikai motor megvalósítása, majd annak ellenőrzött kísérletekkel történő értékelése a helyesség, a numerikus viselkedés és a teljesítmény szempontjából.

## Célok

- **Elsődleges cél:** Működő, verziókezelt 2D merevtest-fizikai rendszer létrehozása kölcsönható testek szimulálására és megjelenítésére.
- **Célfelhasználók / érintettek:** Játékfejlesztők, szimulációs mérnökök és numerikus módszerek iránt érdeklődők.
- **Mérhető sikerkritériumok:** A felhasználó ellenőrzött tesztjeleneteket tud létrehozni; a szimuláció állítható paraméterekkel futtatható; a lényeges fizikai és teljesítménymérőszámok (pl. behatolási hiba, energiaviselkedés, testszámfüggő skálázhatóság) megfigyelhetők és rögzíthetők.
- **Korlátok:** A játékmotor beépített fizikai alrendszere nem használható a vizsgált testek szimulációjára; hitelesítő adatok és titkos kulcsok nem kerülhetnek a repóba.

## Hatókör

### Benne van a hatókörben

- Szimulációs ciklus és numerikus integráció (pl. Euler, Verlet vagy Runge-Kutta).
- Előszűrés (broad phase) és pontos ütközésvizsgálat (narrow phase) szétválasztása.
- BSc-szinten ésszerű geometriai esetek kezelése (körök, tengelyekkel párhuzamos téglalapok, konvex sokszögek).
- Ütközési válasz, rugalmasság (restitúció), súrlódás, forgás és egyszerű kényszerfeltételek.
- Reprodukálható tesztesetek és validációs kísérletek a stabilitás és teljesítmény mérésére.

### Nincs benne a hatókörben

- Kereskedelmi fizikai motor teljes funkcionalitásának reprodukálása.
- Komplex 3D fizikai szimulációk.
- Külső fizikai motorok beépítése a fő szimulációs magként (csak validációs/összehasonlítási alapegységként használhatók).

## Jegyzetek

A fejlesztés során a hangsúly egy összefüggő szimulációs folyamat megértésén, a választott matematikai módszerek korlátainak elemzésén és a kompromisszumok (stabilitás, helyesség, teljesítmény) dokumentálásán van.
