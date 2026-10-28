# Lavagna Magica

Una lavagna da disegno per bambini dai 3 anni in su. Funziona nel browser, su telefono, tablet e computer, senza installare nulla e senza account.

- **Colori:** 10 pulsanti grandi.
- **Pennelli:** pennarello, arcobaleno magico, stelline e gomma, con tre spessori.
- **Adesivi:** gatto, cane, coniglio, pulcino, pesce, farfalla, coccinella, albero, abete, margherita, girasole e tulipano. Si trascinano col dito per scegliere dove metterli.
- **Cancellare:** il cestino pulisce tutto con un tocco e "Rimetti il disegno" lo riporta indietro. La freccia toglie l'ultimo tratto.
- **Offline:** dopo la prima apertura funziona anche senza internet e si può aggiungere alla schermata Home.

Non raccoglie dati e non contiene pubblicità: è un solo file `index.html` con tutto il codice dentro.

## Pubblicarla su GitHub Pages

1. Crea un nuovo repository su GitHub, per esempio con il nome `lavagna-magica`, pubblico e vuoto.
2. Carica tutti i file di questa cartella, compresi quelli che iniziano con il punto (`.nojekyll`, `.gitignore`).
   - Dal sito: nel repository clicca **Add file → Upload files**, trascina i file e conferma con **Commit changes**.
   - Da terminale:

     ```bash
     git init -b main
     git add .
     git commit -m "Prima versione della lavagna"
     git remote add origin https://github.com/TUO-UTENTE/lavagna-magica.git
     git push -u origin main
     ```

3. Nel repository apri **Settings → Pages**.
4. In **Build and deployment** scegli **Deploy from a branch**, poi il ramo **main** e la cartella **/ (root)**, e premi **Save**.
5. Dopo uno o due minuti la pagina compare in alto, all'indirizzo:

   `https://TUO-UTENTE.github.io/lavagna-magica/`

Quell'indirizzo si può mandare ai genitori o aprire sul tablet dei bambini.

## Aggiungerla alla schermata Home

- **iPhone e iPad (Safari):** tasto Condividi, poi **Aggiungi alla schermata Home**.
- **Android (Chrome):** menu con i tre puntini, poi **Installa app** o **Aggiungi a schermata Home**.

Si apre a tutto schermo, come un'app.

## Provarla sul tuo computer

Apri `index.html` con un doppio clic. Per provare anche la modalità offline serve un piccolo server locale:

```bash
python3 -m http.server 8000
```

Poi vai su `http://localhost:8000`.

## Pubblicare una modifica

Dopo aver cambiato `index.html`, apri `sw.js` e aumenta il numero nella riga `const CACHE = 'lavagna-magica-v1';` (per esempio `v2`). Così i dispositivi che l'hanno già salvata scaricano la versione nuova alla prossima apertura.

## Cosa c'è nella cartella

| File | A cosa serve |
| --- | --- |
| `index.html` | La lavagna: pagina, stile e codice. |
| `manifest.webmanifest`, `icon*.png`, `icon.svg`, `apple-touch-icon.png` | Nome e icona quando la si aggiunge alla schermata Home. |
| `sw.js` | Salva i file per usarla senza internet. |
| `.nojekyll` | Dice a GitHub di pubblicare i file così come sono. |

## Aggiungere un adesivo

In `index.html` cerca la lista `STICKERS`. Ogni adesivo è una riga con un nome e un disegno in SVG su un quadrato di 100 per 100. Copia una riga, cambia il nome e il disegno, e compare da solo nell'elenco.

## Note

Il font arrotondato (Fredoka) viene caricato da Google Fonts. Se il dispositivo è offline la prima volta, usa un font simile già presente nel sistema e tutto funziona uguale.
