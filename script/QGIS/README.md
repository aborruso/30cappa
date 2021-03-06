# Contenuto della cartella QGIS

La cartella contiene i dati, progetto e script utili per risolvere i `30cappa` del Decreto di Natale.

# i 30cappa calcolati con QGIS 3.x e SpatiaLite 5.0

- autore @totofiandaca
- licenza [WTFPL](https://it.wikipedia.org/wiki/WTFPL)

## Struttura cartella

La struttura di base è:

```
script/
│
├── QGIS/
│   ├── dati/
|       ├── Italy.geojson
|       ├── 30cappa.sqlite
|       ├── comuni.*
|       ├── province.csv
|       ├── regioni.csv
|       ├── regioni_vett.geojson
|   ├── output/
|       ├── Aree30cappa.*
|       ├── lista_nro_comuni_x_comune5k.csv
|       ├── stile.qml
|       ├── atlas_EN/
|       ├── atlas_PA/
|   ├── scriptSQL/
|       ├── script.sql
|       ├── script_atlas.sql
|   ├── 30cappa.model
|   ├── 30cappaAtlas.model
|   ├── 30cappaAtlas.qgs
|   ├── pagima_atlas.pdf
|   ├── modello_all_FINALE.png

```

## descrizione 

cartella | nome file | descrizione
---------|-----------|-----------
dati     | Italy.geojson | limiti nazionali
dati     | 30cappa.sqlite | database con elaborazioni
dati     | comuni.* | shapefile ISTAT 2020 con aggiunto il campo abitanti ISTAT 01/01/2020
dati     | province.csv | tabella con moni e sigle province
dati     | regioni.csv | tabella con nomi regioni
dati     | regioni_vett.geojson | vettore con le regioni italiane
output   | Aree30cappa.* | shapefile output modello
output   | lista_nro_comuni_x_comune5k.csv | tabella con la lista dei comuni, output dello script_atlas.sql
output   | stile.qml | stile per QGIS
output   | pagine | pagine atlas comuni della provincia di Enna
output   | pagine | pagine atlas comuni della provincia di Palermo
scriptSQL| script.sql | script SQL da usare in spatialite_gui, genera aree30cappa
scriptSQL| script_atlas.sql | script SQL da usare in spatialite_gui, genera tabella lista_nro_comuni_x_comune5k
QGIS     | 30cappa.model | modello per QGIS
QGIS     | 30cappaAtlas.model | modello per QGIS per l'Atlas
QGIS     | 30cappaAtlas.qgs | progetto QGIS
QGIS     | modello_all_FINALE.png | immagine del workflow del modello
QGIS     | pagina_Atlas_orizzontale.png | pagina dell'Atlas layout orizzontale

## modello

![](modello_all_FINALE.png)

## atlas

Nel progetto QGIS sono presenti due Atlas, uno con layout orizzontale e l'altro verticale:

![](pagina_Atlas_orizzontale.png)

![](./output/atlas_PA/30cappaPA.gif)

![](./output/atlas_EN/30cappaEN.gif)

## Video demo

[![](https://img.youtube.com/vi/jq9shGmd2vU/0.jpg)](https://youtu.be/jq9shGmd2vU "#30cappa by @pigreco")

blog post di riferimento: <https://pigrecoinfinito.com/2020/12/26/il-decreto-di-natale-in-chilometri/>

## Test performance

Laptop anno 2015

partendo dal vettore _comuni_ creato da @aborruso (che contiene già il campo abitanti)

- con **QGIS**:
per ottenere il vettore delle `aree30cappa` (unico file) impiego circa 5 min - modello di processing;

- con **Script SQL**:
per ottenere il vettore delle `aree30cappa` (unico file) impiego circa 7/4 min - lancio script da spatialite_gui;