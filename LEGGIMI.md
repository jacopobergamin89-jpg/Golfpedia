# Golfpedia — sito completo

Tutti i file usano il tuo `golfpedia.css` e la stessa struttura (header, nav, footer).

## Come iniziare
1. Scompatta lo zip e carica tutto nella root del repo GitHub.
2. `index.html` è la home. Menu e footer funzionano già su ogni pagina.
3. Per aggiungere/rifare una pagina parti da `template.html`: cambi titolo, descrizione,
   occhiello, H1 e il contenuto; lasci header e footer identici; metti `class="active"`
   sulla voce di menu della pagina.

## Cosa è cambiato rispetto ai tuoi file
- Menu unico: al posto delle due voci Mazze e Palline ora c'è ATTREZZATURA, applicato su
  TUTTE le pagine (menu in alto e footer).
  Ordine menu: Campi · Storia · Glossario · Top 50 · Attrezzatura · Handicap · Tornei · Shop.
- attrezzatura.html (NUOVA): pagina-hub della sezione, con le quattro voci
  (Carrelli, Oggetti del campo, Mazze, Palline). Usa i componenti del tuo CSS, niente stile aggiunto.
- tornei.html: ampliata con Major (uno per uno), Ryder/Presidents/Solheim Cup, i circuiti
  (PGA, DP World, LIV aggiornato al 2026), la piramide amateur->pro e il golf italiano.
- Nella home, la sezione "Esplora l'enciclopedia" ora ha una sola voce Attrezzatura al posto
  delle quattro separate (coerente col menu).

## File inclusi
index, storia, glossario, personaggi, attrezzatura, mazze, palline, carrelli,
oggetti-del-campo, handicap, tornei, template, golfpedia.css, golfpedia-logo.png

## Note
- golfpedia.css è il TUO file originale, invariato.
- golfpedia-logo.png: il CSS lo usa per il segno accanto a "Golfpedia.". L'ho rigenerato dal
  tuo favicon (cerchio verde/rosso). Se hai un logo diverso, sostituisci questo file.
- Privacy e Cookie nel footer puntano ancora a "#": quando generi le informative (es. iubenda)
  crea privacy.html e cookie.html e aggiorna i due link.
- Mancano ancora le schede dei circoli buca-per-buca: quando ne hai una pronta, mandamela e la
  integro nello stesso stile.
