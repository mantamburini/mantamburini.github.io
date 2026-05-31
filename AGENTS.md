# CLAUDE.md — mantamburini.github.io

Contesto del progetto per AI assistant. Leggi prima di fare qualsiasi cosa.

---

## Cos'è questo repo

Blog statico Hugo con tema PaperMod. Pubblicato su GitHub Pages all'indirizzo `https://mantamburini.github.io`.

Autore: Marcello Anselmi Tamburini — IT Senior Service Manager, Crema (CR).

---

## Struttura del repo

```
mantamburini.github.io/
├── .github/
│   └── workflows/
│       └── hugo.yml          # GitHub Actions: build e deploy automatico
├── archetypes/
│   └── posts.md              # template frontmatter per nuovi articoli
├── content/
│   ├── about.md              # pagina "Chi sono"
│   └── posts/                # articoli del blog
├── themes/
│   └── PaperMod/             # tema (git submodule, non toccare)
└── hugo.toml                 # configurazione Hugo
```

---

## Workflow di pubblicazione

1. Scrivi o modifica un file in `content/posts/`
2. Mentre è bozza: `draft: true` nel frontmatter
3. Quando pronto: `draft: false`
4. `git add . && git commit -m "post: titolo" && git push`
5. GitHub Actions esegue Hugo e pubblica su GitHub Pages (~1 minuto)

Anteprima locale (richiede Hugo installato):

```bash
hugo server -D   # -D mostra anche i draft
```

---

## Frontmatter degli articoli

```yaml
---
title: "Titolo dell'articolo"
date: 2026-01-15
draft: false
tags: ["tag1", "tag2"]
description: "Una frase che descrive l'articolo."
---
```

- `draft: true` = non pubblicato
- `draft: false` = pubblicato al prossimo push
- `date` determina l'ordinamento

### Formato dei post

Ogni post è un file `.md` semplice nella directory `content/posts/`. Niente cartelle, niente `index.md`, niente struttura complessa. Un file, un post.

Questa scelta è voluta: i file devono poter essere aperti, modificati e creati con qualunque editor (Obsidian, VS Code, vim) senza dipendere da Hugo o da strumenti specifici.

Struttura tipica:

```markdown
---
title: "Titolo del post"
date: 2026-01-15
draft: true
tags: ["tag1", "tag2"]
description: "Una frase."
---

Testo del post. Paragrafi. Qualche H2 al massimo. Niente di più.
```

Non serve architettare il contenuto in sezioni e sottosezioni come un manuale tecnico. I post possono essere lineari, narrativi, anche un singolo blocco di testo se funziona.

---

## Contenuto del blog

**Argomento**: metodologia della documentazione di processo in contesti IT aziendali. Gli strumenti sono secondari — quello che conta è il modo in cui si pensa, struttura e mantiene un processo documentato.

**Pubblico**: IT manager e service manager di medie aziende italiane.

**Lingua**: italiano.

**Tono e stile**: vedi sezione dedicata sotto.

**Temi ricorrenti**:

- Ciclo di vita di un documento di processo
- Differenza tra processo, procedura, policy
- Il formato come scelta architetturale, non estetica
- Responsabilità e ownership della documentazione
- Documentazione as code

---

## Diagrammi

I diagrammi vanno come immagini linkate tramite Kroki (non codice eseguito inline):

```markdown
![Descrizione](https://kroki.io/plantuml/svg/BASE64_DEL_SORGENTE)
```

Non usare Hugo shortcode per i diagrammi.

---

## Regole di scrittura

### Parole vietate

Non usare mai: delve, harness, leverage (verbo), seamlessly, robust, comprehensive, cutting-edge, state-of-the-art, empower, foster, holistic, synergy, utilize, facilitate, transformative, pivotal, crucial, navigate (metaforico), journey (metaforico), unlock, elevate, game-changer.

### Pattern vietati

- Aperture: "Great question!", "Certainly!", "Let's dive in.", "In today's fast-paced world…"
- Strutture: "This isn't X, this is Y.", "X is more than just Y—it's Z.", "It's worth noting that…", "It's important to remember that…", "When it comes to X…"
- Chiusure: "Hope this helps!", "Feel free to ask", "Let me know if you'd like me to elaborate."

### Tono

Diretto. Un'idea per paragrafo. Specifico invece che generico. Le opinioni si esprimono come opinioni, i fatti come fatti. Niente imballo intorno alla risposta.

### Formattazione

- Header H2 per sezioni principali, H3 per sottosezioni. Mai più in profondità nel testo.
- Liste numerate solo se l'ordine conta. Bullet per 4+ elementi paralleli.
- Bold solo per termini genuinamente critici, non per enfasi decorativa.
- Nessuna emoji.
- Codice sempre in fenced block con language specifier.

### La regola d'oro

Niente che non sia verificato. Ogni affermazione verificabile va verificata. Citare le fonti quando necessario.

---

## Aggiornamento tema

```bash
git submodule update --remote --merge themes/PaperMod
git commit -am "chore: aggiorna PaperMod"
git push
```

## Aggiornare la versione di Hugo nel workflow

Modifica `HUGO_VERSION` in `.github/workflows/hugo.yml`.
