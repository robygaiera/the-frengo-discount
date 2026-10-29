# THE FUCKING DISCOUNT

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

Pioggia di `€ $ £ ¥ ₿` e cifre su canvas, scanline CRT, pannelli con angoli da terminale. Il pulsante `pioggia: ON/OFF` in basso a destra spegne l'animazione (utile per leggere meglio o risparmiare batteria); con `prefers-reduced-motion` attivo parte già spenta e mostra solo una texture statica.

## In locale

Apri `index.html` con doppio clic. Funziona anche da `file://`.

## Pubblicare su GitHub Pages

```bash
git init
git add .
git commit -m "The Fucking Discount"
git branch -M main
git remote add origin https://github.com/TUO-UTENTE/NOME-REPO.git
git push -u origin main
```

Poi su GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `root` → Save**.

Dopo un minuto il sito è online su `https://TUO-UTENTE.github.io/NOME-REPO/`.

## Formula

```
sconto % = (1 − prezzo finale ÷ (listino IVato × quantità)) × 100
```

Se il prezzo di partenza è inserito IVA esclusa, il listino viene prima portato IVA inclusa: `listino × (1 + aliquota)`.
