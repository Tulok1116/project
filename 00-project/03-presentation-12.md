---
project_outline: "[[00-project/01-project-outline]]"
---

<!-- @slide Egyedi 2D fizikai motor játékokhoz -->
<!-- 5xl -->

# Egyedi 2D fizikai motor játékokhoz

**Szerző:** Galambos Bence

**Neptun:** D0EWY6

**Témavezető:** Novák Péter

**Projektazonosító:** 2026-NP-05

---

<!-- @slide Probléma -->

## Probléma

* **A kereskedelmi fizikai motorok bonyolultsága:** A modern játékmotorok (pl. PhysX, Box2D) beépített alrendszerei hatalmas funkcionalitást biztosítanak, de egyúttal "fekete dobozként" működnek, elrejtve a háttérben zajló matematikai és numerikus folyamatokat.
* **A szimulációs ciklus megértésének hiánya:** A numerikus integráció, a térbeli előszűrés (*broad phase*), a pontos ütközésvizsgálat (*narrow phase*), valamint az ütközési válasz (*collision response*) összefüggő láncolatának önálló megvalósítása komoly mérnöki és matematikai kihívást jelent.
* **Numerikus instabilitás és hibák:** Nem megfelelő integrátor vagy túl nagy időlépés ($\Delta t$) esetén a szimulációkban numerikus drift lép fel, ami az energia nem-megmaradásához és a testek "szétrobbanásához" vezethet.
* **Kompromisszumok kezelése:** Meg kell határozni a pontosság, a fizikai helyesség és a valós idejű számítási teljesítmény (*skálázhatóság*) közötti optimális mérnöki egyensúlyt.

---

<!-- @slide Célfelhasználók -->

## Célfelhasználók

* **Játékfejlesztők és Motorfejlesztők:** Akik meg akarják érteni a 2D merevtest-fizika belső felépítését, és saját, optimalizált fizikai magot (*physics core*) kívánnak integrálni egyedi rendszereikbe.
* **Szimulációs Mérnökök és Kutatók:** Akik ellenőrzött, determinisztikus tesztkörnyezetet keresnek numerikus módszerek, integrátorok (pl. Euler vs. Verlet) és ütközésdetektálási algoritmusok vizsgálatára.
* **Informatikus Hallgatók és Oktatók:** Akik a BSc-szintű fizika, numerikus matematika és szoftverarchitektúra gyakorlati megvalósítását és validációját elemzik.

---

<!-- @slide Tervezett hatókör -->

## Tervezett hatókör

* **Benne van a hatókörben:**
  * **Numerikus Integráció:** Külső erők és sebességek kezelése (pl. Semi-Implicit Euler / Verlet integrátorok).
  * **Ütközésdetektáló Pipeline:** Az előszűrés (*broad phase*) és a pontos geometriai metszetvizsgálat (*narrow phase*, pl. SAT – Separating Axis Theorem konvex poligonokhoz és körökhöz) szétválasztása.
  * **Ütközési Válasz & Kényszerek:** Impulzus alapú dinamika, restitúció (rugalmasság), súrlódás, forgás, valamint behatolási hiba elleni pozíció-korrekció (*positional correction*) és egyszerű csuklók/távolságkényszerek.
  * **Validáció és Mérések:** Reprodukálható tesztesetek futtatása, numerikus stabilitás vizsgálata különböző időlépések mellett, valamint a testszámfüggő számítási költségek elemzése.

---

<!-- @slide Tervezett hatókör -->
## Tervezett hatókör

* **Nincs benne a hatókörben:**
  * Kereskedelmi fizikai motorok teljes körű, ipari funkcionalitásának lemásolása.
  * Komplex, teljes értékű 3D fizikai szimulációk.
  * Külső fizikai motor beépítése fő szimulációs magként (csak validációs / összehasonlítási alapként engedélyezett).

---

<!-- @slide Kezdeti felhasználói utak -->

## Kezdeti felhasználói utak

1. **Tesztjelenet Létrehozása és Konfigurálása:**
   * A fejlesztő/felhasználó kiválaszt vagy létrehoz egy ellenőrzött tesztjelenetet (pl. egymásra halmozott dobozok, lejtőn guruló körök, kényszerrel rögzített ingák).
   * Beállítja a szimulációs paramétereket (gravitáció, időlépés $\Delta t$, restitúciós együtthatók).

2. **Szimulációs Ciklus Futtatása:**
   * A rendszer valós időben (vagy lépésenként) végrehajtja a ciklust: numerikus integráció $\rightarrow$ broad phase $\rightarrow$ narrow phase $\rightarrow$ ütközési válasz és kényszermegoldó.

3. **Mérési Adatok Rögzítése és Elemzése:**
   * A felhasználó megfigyeli a mozgást a megjelenítő felületen, miközben a rendszer rögzíti a fontosabb mérőszámokat (pl. behatolási hiba mértéke, energiaviselkedés, FPS / számítási költség).

---

<!-- @slide Következő lépések -->

## Következő lépések

* **Matematikai és Architekturális Alapok Véglegesítése:** A vektor, mátrix osztályok, valamint a merevtest (*Rigid Body*) struktúra megtervezése a választott programozási nyelven.
* **Integrátor és Broad Phase Implementáció:** A numerikus integrációs ciklus és a kezdeti térbeli előszűrési algoritmus elkészítése.
* **Geometriai Ütközésvizsgálat (SAT) Fejlesztése:** A körök, AABB-k és konvex sokszögek metszetvizsgálatának, valamint a kontaktus-halmaz (*manifold*) generálásának programozása.
* **Verziókövetési Környezet Kialakítása:** A Git-alapú GitHub repó struktúrájának felépítése, ügyelve arra, hogy érzékeny adatok vagy tokenek ne kerüljenek commitolásra.
