# THE FRENGO DISCOUNT

**Live:** https://robygaiera.github.io/the-frengo-discount/

Webapp a file singolo (solo `index.html`, zero dipendenze) che calcola la percentuale di sconto esatta — con 2, 4, 6, 8, 10 o 12 decimali — per portare un prezzo IVato a un importo preciso. Grafica stile terminale Matrix, con pioggia di simboli di valuta sullo sfondo.

## Cosa fa

- Inserisci il **prezzo finale che vuoi ottenere**, IVA inclusa (es. 10,00 €).
- Inserisci la **quantità** (default 1).
- Inserisci il **prezzo di partenza** per pezzo, dicendo se è IVA inclusa o IVA esclusa.
- Imposti l'**aliquota IVA** (default 22%).
- Ottieni:
  - lo sconto da applicare, con i decimali che scegli;
  - prezzo unitario scontato e totale IVato;
  - dettaglio con listino, sconto in euro, imponibile e IVA;
  - il totale che otterresti davvero con quella percentuale, con lo scarto in euro (utile se il gestionale arrotonda lo sconto a 2 decimali).

Tutti i calcoli girano nel browser: nessun dato viene inviato da nessuna parte, nessuna build, nessun server.

## Grafica

Pioggia di `€ $ £ ¥ ₿` e cifre su canvas, scanline CRT, pannelli con angoli da terminale. Il pulsante `golden shower: ON/OFF` in basso a destra spegne l'animazione (utile per leggere meglio o risparmiare batteria); con `prefers-reduced-motion` attivo parte già spenta e mostra solo una texture statica.

## In locale

Apri `index.html` con doppio clic. Funziona anche da `file://`.

## Pubblicazione

Il sito è già online su GitHub Pages: `main` → `root`. Ogni push su `main` aggiorna la pagina dopo circa un minuto.

```bash
git add .
git commit -m "modifica"
git push
```

Per rifare tutto da zero: `gh repo create NOME-REPO --public --source=. --remote=origin --push`, poi **Settings → Pages → Deploy from a branch → `main` / `root`**.

## Formula

```
sconto % = (1 − prezzo finale ÷ (listino IVato × quantità)) × 100
```

Se il prezzo di partenza è inserito IVA esclusa, il listino viene prima portato IVA inclusa: `listino × (1 + aliquota)`.
