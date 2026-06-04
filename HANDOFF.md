# Golfpedia — Handoff del progetto

Documento di consegna completo. Spiega cos'è il sito, come è fatto, come si aggiorna e cosa resta da fare. Aggiornato a giugno 2026.

---

## 1. Cos'è

**Golfpedia** è un'enciclopedia del golf in italiano: un sito di pagine HTML statiche (niente database, niente backend), pensato per essere semplice da gestire e veloce.

- **Sito online:** https://jacopobergamin89-jpg.github.io/Golfpedia/
- **Hosting:** GitHub Pages, dal repository `jacopobergamin89-jpg/Golfpedia`, ramo `main`.
- **Dominio futuro previsto:** golfpedia.it (citato nel footer; non ancora collegato).

Il sito è un progetto editoriale indipendente: non è affiliato a federazioni, circoli o altre enciclopedie (lo dichiara il footer).

---

## 2. Come si aggiorna (workflow)

Il sito vive su GitHub. Il ciclo di lavoro è sempre lo stesso:

1. Si modifica o si crea un file (HTML, CSS, immagine).
2. Si carica su GitHub nel repository, nella cartella principale (dove c'è `index.html`).
3. GitHub Pages ripubblica il sito in automatico, di solito entro un minuto o due.
4. Sul browser conviene fare un **refresh forzato** (Cmd+Shift+R) perché Pages tiene in cache la versione vecchia per qualche minuto.

Per caricare/sostituire un file su GitHub: aprire il file e usare la **matita (Edit)**, oppure `Add file → Upload files` per sostituirlo o aggiungerne di nuovi.

> **Importante:** tenere **una sola copia aggiornata** di ogni file. Quando si lavora con un assistente, il file modificato torna sempre "in mano a chi gestisce il sito", che lo ricarica al posto del vecchio.

---

## 3. Struttura del sito

Il menu in alto ha **10 voci fisse**, in quest'ordine:

`Campi · Storia · Glossario · Top 50 · Attrezzatura · Il campo · Handicap · Tornei · Viaggi · Shop`

Alcune voci sono "hub" (pagine-indice) che portano a pagine di dettaglio. Le pagine di dettaglio **non** stanno nel menu in alto: si raggiungono dagli hub e dalla **mappa del sito** (`mappa.html`).

### Pagine principali
| File | Pagina |
|---|---|
| `index.html` | Home — ricerca campi e ingresso a tutte le sezioni |
| `storia.html` | Storia del golf (mondo) |
| `storia-italia.html` | Storia del golf in Italia (Acquasanta 1903, FIG 1927, primi campioni) |
| `glossario.html` | Glossario A–Z **con ricerca** |
| `personaggi.html` | Top 50 giocatori |
| `handicap.html` | Handicap e World Handicap System |
| `tornei.html` | Major, tour, Ryder Cup, golf italiano |
| `viaggi.html` | Viaggi e mete di golf |
| `shop.html` | Negozio dei prodotti propri (vedi sezione 6) |
| `mappa.html` | Mappa del sito: elenco di tutte le pagine |

### Sezione "Attrezzatura" (hub: `attrezzatura.html`)
| File | Pagina |
|---|---|
| `carrelli.html` | Carrelli e sacche |
| `oggetti-del-campo.html` | Oggetti del campo (marker, ripara-pitch, ecc.) |
| `mazze.html` | Mazze |
| `palline.html` | Palline |
| `marche.html` | Le marche del golf e i loro ambassador |
| `allenamento-casa.html` | Attrezzi per allenarsi a casa |

### Sezione "Il campo" (hub: `campo.html`)
| File | Pagina |
|---|---|
| `percorso.html` | Com'è fatto e come si gioca un percorso (fairway, rough, ostacoli, fuori limite, paletti, distanze, scorecard, etichetta, drop) |
| `struttura-campo.html` | Com'è strutturato un circolo (club house, range, macchine palline, percorsi 0–36 buche) |
| `proshop.html` | Il pro shop: cosa ci trovi |
| `erba.html` | Erba e sabbia dei bunker |
| `manutenzione.html` | Macchinari e manutenzione del verde (collegata da dentro `erba.html`) |
| `figure.html` | Le figure del golf (maestro, caddie, greenkeeper, ecc.) |

### File di supporto
| File | A cosa serve |
|---|---|
| `golfpedia.css` | **Lo stile di tutto il sito.** Ogni pagina lo richiama. Senza, il sito è "nudo". |
| `golfpedia-logo.png` | Logo (cerchio verde/rosso). Sostituibile con uno definitivo. |
| `template.html` | Pagina vuota di base, da copiare per crearne di nuove. Non è una pagina pubblica. |
| `LEGGIMI.md` / `HANDOFF.md` | Note interne (non pubblicate o solo di servizio). |
| `img/` | Cartella delle immagini (vedi sezione 5). |

---

## 4. Il menu è ripetuto in ogni pagina

**Punto chiave da ricordare.** Non esiste un "menu unico": la barra di navigazione e il footer sono **copiati dentro ogni pagina HTML**. Conseguenza pratica:

- se si cambia una voce di menu (es. si aggiunge una sezione, si rinomina una voce, si corregge un link), la modifica va fatta **su tutte le pagine**, non in un posto solo;
- è già successo, per esempio, con il link "Shop": andava corretto in 24 pagine.

**Possibile miglioramento futuro:** passare a un "menu unico" caricato via JavaScript (un solo file da modificare). Per ora è stato volutamente lasciato così perché semplice e robusto.

---

## 5. Lo stile e le immagini

### Stile (`golfpedia.css`)
- Palette: sfondo crema, **verde** (`#16a34a`) e **rosso** (`#e0232b`) — richiamo al tricolore.
- Font (da Google Fonts): Newsreader (titoli), DM Sans (testo), DM Mono (etichette).
- Classi principali già pronte: intestazione/menu (`site`, `bar-sec`), articoli (`prose`), griglie indice degli hub (`index2`, `catrow`), schede prodotto dello shop (`prod-grid`, `prod`, `price`), riquadri pubblicitari/affiliazione (`adbox`), ricerca glossario (`gloss-search`).
- Ogni nuova pagina deve avere in testa: `<link rel="stylesheet" href="golfpedia.css">`.

### Immagini (cartella `img/`)
- Le immagini sono file nel repository, dentro la cartella **`img/`** (allo stesso livello delle pagine). Si richiamano così: `<img src="img/nomefile.jpg" alt="descrizione">`.
- **Regole per i nomi:** tutto minuscolo, senza spazi né accenti (usare il trattino). GitHub distingue maiuscole/minuscole, quindi il nome nel file HTML deve essere identico a quello del file caricato.
- **Niente foto prese da altri siti:** sono coperte da copyright. Usare foto proprie, immagini con licenza libera (Unsplash, Pexels, Wikimedia con attribuzione) o materiali ufficiali autorizzati.
- **Alleggerire sempre le foto** prima di caricarle: ridimensionare a circa 1080 px di lato e salvarle in JPEG. Le foto dei prodotti sono già state ottimizzate (da ~14 MB totali a ~1,4 MB).

---

## 6. Lo Shop (importante)

Lo shop **non** è affiliazione: vende **prodotti propri** (accessori da golf prodotti dalla società). Pagamento previsto: **carta di credito**, tramite link di pagamento esterni.

### Com'è fatta la pagina
`shop.html` mostra una griglia di schede prodotto. Ogni scheda è un blocco:

```html
<article class="prod">
  <div class="ph"><img src="img/nomefoto.jpg" alt="..."></div>
  <div class="body">
    <span class="cat">Categoria</span>
    <h3>Nome prodotto</h3>
    <p>Descrizione breve.</p>
    <div class="price">€ 00,00</div>
    <a class="buy" href="LINK-DI-PAGAMENTO">Acquista</a>
  </div>
</article>
```

Per aggiungere/togliere un prodotto si copia o si elimina un blocco `<article class="prod">`.

### I 10 prodotti già inseriti (con la foto collegata)
| Prodotto | Categoria | Foto |
|---|---|---|
| Cancelletti per il putt | Allenamento | `img/cancelli_putt.jpg` |
| Cestello porta-palline | Allenamento | `img/cestello_allenamento.jpg` |
| Traccia-linee per palline | Accessori | `img/marker_palline.jpg` |
| Porta-palline e tee personalizzato | Idee regalo | `img/palline_tee_piramide.jpg` |
| Porta-palline con moschettone | Idee regalo | `img/palline_tee.jpg` |
| Ripara-pitch pieghevole | Accessori | `img/pickmark.jpg` |
| Posiziona-tee ad altezza fissa | Accessori | `img/posiziona_tee.jpg` |
| Conta-colpi da sacca | Accessori | `img/segna_stroke.jpg` |
| Porta-tee da cappello | Accessori | `img/tee_cappello.jpg` |
| Porta 3 palline e tee da sacca | Accessori | `img/tee_palline_gancio.jpg` |

### Cosa manca per renderlo operativo
1. **Prezzi:** sostituire `€ 00,00` con il prezzo reale di ogni prodotto.
2. **Link di pagamento:** sostituire `href="#"` del bottone "Acquista" con un link di pagamento. Serve un account incassi che accetti carte:
   - **Stripe** (consigliato): crei un "Payment Link" per prodotto e lo incolli nel bottone. Commissioni ~1,5% + 0,25€ a transazione (carte UE).
   - **PayPal** o **SumUp/Nexi**: alternative valide, stesso principio.
   Il pagamento avviene sulla pagina sicura del fornitore; il sito statico non gestisce le carte.
3. **Pagine legali** (vendendo prodotti propri sono necessarie): **spedizioni e resi**, **condizioni di vendita**, **privacy**, **cookie**. Nei testi dello shop e nel footer i link puntano ancora a `#`. Sono contenuti aziendali/legali da far validare a chi segue gli aspetti fiscali e legali della società (non è consulenza legale).

---

## 7. Note di contenuto e accuratezza

Il sito punta alla correttezza. Dove un dato è volatile o incerto, le pagine riportano una nota **"Da verificare"**:
- **`marche.html`** — gli "ambassador" delle marche cambiano spesso (contratti annuali): da aggiornare periodicamente.
- **`percorso.html`** — le regole (colori paletti, opzioni di drop, drop dall'altezza del ginocchio) sono verificate sulle regole R&A/USGA attuali; i colori dei segnali di distanza variano da circolo a circolo.
- **`storia-italia.html`** — date e nomi dei primi circoli verificati; eventuali "reperti" storici andrebbero documentati con fonti dirette.
- **`erba.html`** — nomi commerciali di erbe e sabbie variano: da verificare caso per caso.

**Glossario:** in `glossario.html` ogni termine è un `<p><strong>Termine</strong> — definizione.</p>` sotto la lettera corrispondente (`<h2>X</h2>`). C'è una barra di ricerca in cima che filtra i termini: aggiungendo nuovi termini in ordine alfabetico, la ricerca continua a funzionare da sola.

---

## 8. Come creare una pagina nuova

1. Duplicare `template.html` e rinominarlo (nome minuscolo, senza spazi: es. `regole-base.html`).
2. Riempire `<title>`, l'intestazione `art-hero` e il contenuto dentro `<article class="prose">`.
3. Nel menu della nuova pagina, mettere la classe `active` sulla voce di sezione giusta.
4. Aggiungere il link alla pagina nell'**hub** di riferimento (`attrezzatura.html` o `campo.html`) e nella **mappa** (`mappa.html`).
5. Se la pagina deve comparire nel menu in alto, aggiungere la voce **in tutte le pagine** (vedi sezione 4).

---

## 9. Cose ancora aperte (TODO)

- [ ] **Shop:** inserire prezzi reali e link di pagamento (Stripe/PayPal).
- [ ] **Pagine legali:** spedizioni e resi, condizioni di vendita, privacy, cookie (oggi puntano a `#`).
- [ ] **Logo definitivo** al posto di `golfpedia-logo.png` (se disponibile).
- [ ] **Foto nelle pagine di contenuto** (non solo shop): decidere dove servono e prepararle (con licenza/foto proprie).
- [ ] **Sezione Viaggi:** sviluppare i racconti/"diario di viaggio" (es. la coppia in camper che gioca i campi durante il viaggio), tenendo i campi reali descritti in modo corretto e segnalando che è narrativa.
- [ ] **Schede dei circoli buca per buca:** il contenuto più lungo e impegnativo; rinviato. Sarà il cuore "enciclopedico" del sito.
- [ ] **Menu unico** via JavaScript, per non dover più modificare il menu pagina per pagina (miglioramento tecnico).
- [ ] **Idee di pagine** già proposte: "Iniziare a giocare", "Regole base ed etichetta", "Come leggere lo scorecard", "Tipi di percorso", "L'Open d'Italia", "Glossario per principianti".

---

## 10. Riepilogo file

**Pagine (25):** index, storia, storia-italia, glossario, personaggi, handicap, tornei, viaggi, shop, mappa, attrezzatura, carrelli, oggetti-del-campo, mazze, palline, marche, allenamento-casa, campo, percorso, struttura-campo, proshop, erba, manutenzione, figure, template.

**Supporto:** golfpedia.css, golfpedia-logo.png, LEGGIMI.md, HANDOFF.md.

**Immagini (`img/`, 10 foto prodotto):** cancelli_putt, cestello_allenamento, marker_palline, palline_tee, palline_tee_piramide, pickmark, posiziona_tee, segna_stroke, tee_cappello, tee_palline_gancio (tutte `.jpg`).

> Per ripartire da zero senza confusione: scaricare lo zip completo del sito, cancellare tutto nel repo e ricaricare i file dello zip. L'unico file indispensabile per l'aspetto grafico è `golfpedia.css`.
