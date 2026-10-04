# asumi.it — landing page

Sito statico, una sola pagina, senza dipendenze esterne (font self-hosted, nessun cookie, nessun tracciamento).

## File
| File | Ruolo |
|---|---|
| `index.html` | La landing (con meta SEO, Open Graph e dati strutturati JSON-LD) |
| `404.html` | Pagina di errore servita da GitHub Pages |
| `fonts/` | Montserrat, Lora italic, Noto Serif JP (solo i kanji/kana usati) |
| `assets/` | Logo ufficiale in WebP (simbolo grande e simbolo piccolo) |
| `favicon-32.png`, `favicon-192.png`, `apple-touch-icon.png`, `logo.png` | Icone e logo per Google |
| `og-image.png` | Anteprima 1200×630 per LinkedIn, WhatsApp, ecc. |
| `robots.txt`, `sitemap.xml` | Indicizzazione motori di ricerca |
| `llms.txt` | Sintesi testuale per assistenti AI (GEO) |
| `CNAME` | Dominio personalizzato: **da ricreare** con dentro `asumi.it` quando il dominio è acquistato |
| `.nojekyll` | Pubblica i file così come sono |

## Pubblicazione su GitHub Pages
1. Crea un repository dedicato (es. `asumi-web`) e carica **il contenuto** di questa cartella nella radice del repository.
2. Repository → Settings → Pages → Source: *Deploy from a branch*, branch `main`, cartella `/ (root)`.
3. Settings → Pages → Custom domain: `asumi.it` (il file `CNAME` è già presente).
4. Dal profilo GitHub: Settings → Pages → *Verified domains* → aggiungi `asumi.it` (record TXT da inserire nel DNS). Evita che altri possano usare il dominio su GitHub.
5. Quando il certificato è pronto, attiva **Enforce HTTPS**.

## DNS presso il registrar di asumi.it
| Tipo | Nome | Valore |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |
| CNAME | www | `<utente-github>.github.io` |

Verifica i valori sulla documentazione GitHub Pages al momento della configurazione. Il record MX della posta va lasciato intatto.

## Dopo la messa online
- Registra il sito su Google Search Console e Bing Webmaster Tools e invia `https://asumi.it/sitemap.xml`.
- Controlla i dati strutturati con il Rich Results Test di Google e l'anteprima social con il LinkedIn Post Inspector.

## Da aggiornare quando disponibili
- P.IVA, codice fiscale, numero REA: footer di `index.html` (cerca `DA AGGIORNARE`) e, per la P.IVA, aggiungi `"vatID": "IT..."` e `"taxID": "..."` nell'oggetto Organization del JSON-LD.
- Email ufficiale: `index.html` (link, tasto Copia, JSON-LD) e `llms.txt`.
- Logo: i file in `assets/` sono estratti dai PNG/JPG HD in `Asumi/resources/`. Con un file vettoriale (SVG/AI/EPS) la resa sarebbe più nitida.
- Profili LinkedIn dei fondatori, se vuoi: aggiungi `"sameAs": ["https://www.linkedin.com/in/..."]` alle Person del JSON-LD.
