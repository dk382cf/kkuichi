# Diplomová práca - Príloha B

**Autor:** Bc. Dominik Kuruc  
**Školiteľ:** doc. Ing. Marek Bundzel, PhD.  

---

## Obsah prílohy

Táto príloha obsahuje:

- `findBuildings_small.ipynb` – spracovanie malej oblasti (ladenie algoritmu)
- `findBuildings_large.ipynb` – spracovanie veľkej oblasti
- `detector_my.py` – implementácia detekčného a klasifikačného algoritmu
- `convert.ipynb` - pretypovanie súborov na .tif(v prípade potreby)
- `gui.py` – grafické používateľské rozhranie
- `gui_output` - výstupy pre GUI
- `QGIS/` - úložisko vrstiev v QGISe
- `QGIS_csv/` – výstupy vo formáte CSV pre vizualizáciu v QGIS
- `vizualizacie/` – obrázkové výstupy detekcie
- `zdroj/` – vstupné dáta (DEM, maska)
- `Kuruc_Dominik_DP` - projekt v QGIS

---

## Požiadavky (knižnice)

Pre správne fungovanie projektu je potrebné nainštalovať nasledovné knižnice:

- numpy  
- opencv-python  
- matplotlib  
- rasterio  
- pandas  
- tkinter  

Inštalácia:

pip install numpy opencv-python matplotlib rasterio pandas

---

## Postup použitia

### 1. Spracovanie malej oblasti

Notebook `findBuildings_small.ipynb` slúži na testovanie a ladenie algoritmu.

Obsahuje:
- načítanie dát
- extrakciu objektov
- výpočet príznakov
- klasifikáciu
- vizualizáciu výsledkov

---

### 2. Spracovanie veľkej oblasti

Notebook `findBuildings_large.ipynb` slúži na spracovanie celej oblasti.

Kvôli výkonnosti:
- dáta sa delia na menšie časti (chunky)
- každá časť sa spracuje samostatne

Výstup:
- detegované objekty
- CSV súbor (WKT geometria)
- dáta pripravené pre QGIS

---

### 3. Spustenie GUI

Grafické rozhranie umožňuje jednoduché spustenie algoritmu bez potreby práce s notebookmi.

Spustenie:

python gui.py

Funkcionalita GUI:
- načítanie vstupných dát (DEM, maska)
- spustenie detekcie objektov
- zobrazenie výsledkov
- export výsledkov (CSV)

---

### 4. Vizualizácia v QGIS

Výsledný CSV súbor obsahuje objekty vo formáte WKT.

Postup:
1. Importovať CSV ako Add Delimited Text Layer
2. Nastaviť geometriu ako WKT
3. Nastaviť súradnicový systém:

EPSG:32616 – WGS 84 / UTM zone 16N

---

## Poznámky

- Algoritmus je založený na kombinácii geometrických a výškových príznakov
- Klasifikácia prebieha pomocou pravidiel definovaných v súbore `detector_my.py`
- Tento súbor je kľúčový a nie je možné ho vynechať

---

## Výstupy

- CSV súbory (QGIS)
- vizualizácie
- klasifikované objekty
