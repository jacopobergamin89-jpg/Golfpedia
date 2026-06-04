# Golfpedia — sito completo

Tutti i file usano il tuo `golfpedia.css` e la stessa struttura (header, nav, footer).

## Come iniziare
1. Scompatta lo zip e carica tutto nella root del repo GitHub.
2. `index.html` è la home. Menu e footer funzionano già su ogni pagina.
3. Per aggiungere/rifare una pagina parti da `template.html`.

## Menu (uguale su tutte le pagine)
Campi · Storia · Glossario · Top 50 · Attrezzatura · Il campo · Handicap · Tornei · Viaggi · Shop
(Il menu è ormai pieno: se in futuro diventa troppo, conviene raggruppare alcune voci in un menu a tendina.)

## Sezioni-hub (come Attrezzatura)
- ATTREZZATURA -> carrelli, oggetti del campo, mazze, palline
- IL CAMPO -> erba e sabbia, le figure del golf, oggetti del campo

## Novità di questo giro
- VIAGGI (nuova sezione): pagina evocativa sul golf travel (Italia e mondo) con DUE slot
  pubblicitari di affiliazione (Booking). Sono riquadri segnaposto .adbox: ci incolli dentro
  il codice del banner reale quando vuoi.
- IL CAMPO (nuova sezione-hub) con:
  - erba.html -> tipi di erba (dove e perché) + la sabbia dei bunker (ancora #sabbia)
  - figure.html -> le figure del golf: maestro, caddie, caddie master, marshall, greenkeeper, ecc.
- GLOSSARIO: aggiunta la RICERCA in cima (barra che resta visibile mentre scorri); filtra le
  voci man mano che digiti. Non serve nessun servizio esterno, è tutto nella pagina.
- CSS: ho aggiunto in fondo a golfpedia.css due piccoli blocchi commentati:
  ".adbox" (slot pubblicitari) e ".gloss-search" (barra del glossario). Il resto del CSS è il tuo, invariato.

## Slot pubblicitari
- Per metterne altri in qualunque pagina, incolla:
  <div class="adbox"><span class="lab">Spazio pubblicitario</span><span class="hint">descrizione</span></div>
  e poi sostituisci il contenuto con il codice AdSense (dopo l'approvazione) o il banner di affiliazione.
- Usa "adbox tall" per un riquadro più alto.

## Note
- golfpedia.css è il TUO file; ho solo aggiunto in coda i due blocchi sopra.
- golfpedia-logo.png: rigenerato dal favicon (cerchio verde/rosso). Se hai un logo diverso, sostituiscilo.
- Privacy e Cookie nel footer puntano a "#": crea le pagine quando generi le informative.
- Mancano ancora le schede dei circoli buca-per-buca.
