# Setup: mantamburini.github.io

## Prerequisiti

- Account GitHub: `mantamburini`
- Hugo installato su Arch Linux
- Git configurato

---

## 1. Installa Hugo su Arch

```bash
sudo pacman -S hugo
hugo version   # verifica: deve essere >= 0.147
```

---

## 2. Crea il repo su GitHub

1. Vai su https://github.com/new
2. Nome repo: **`mantamburini.github.io`** (esatto, con il punto)
3. Visibilità: **Public** (obbligatorio per GitHub Pages gratuito)
4. Non inizializzare con README
5. Crea il repo

Poi vai su **Settings → Pages → Source** e seleziona **GitHub Actions**.

---

## 3. Inizializza il sito Hugo in locale

```bash
cd ~   # o dove vuoi mettere il progetto
hugo new site mantamburini.github.io
cd mantamburini.github.io
git init
git remote add origin https://github.com/mantamburini/mantamburini.github.io.git
```

---

## 4. Aggiungi il tema PaperMod

```bash
git submodule add --depth=1 \
  https://github.com/adityatelange/hugo-PaperMod.git \
  themes/PaperMod
git submodule update --init --recursive
```

---

## 5. Copia i file di configurazione

Copia i file forniti nella root del progetto:

```
mantamburini.github.io/
├── .github/
│   └── workflows/
│       └── hugo.yml          ← da copiare
├── archetypes/
│   └── posts.md              ← da copiare
├── content/
│   ├── about.md              ← da copiare
│   └── posts/                ← qui vanno gli articoli
└── hugo.toml                 ← da copiare, poi editare
```

Edita `hugo.toml`: sostituisci i campi `TITOLO`, `DESCRIZIONE` con i valori reali.

---

## 6. Primo commit e deploy

```bash
git add .
git commit -m "init: struttura base Hugo + PaperMod"
git branch -M main
git push -u origin main
```

GitHub Actions si avvia automaticamente. Dopo ~1 minuto il sito è live su:
**https://mantamburini.github.io**

Controlla lo stato su: `https://github.com/mantamburini/mantamburini.github.io/actions`

---

## 7. Integrazione Obsidian

Il modo più pulito: tieni il repo Hugo dentro una sottocartella del vault.

```
VaultObsidian/
└── blog/                         ← è il repo git mantamburini.github.io
    ├── content/
    │   └── posts/                ← scrivi qui da Obsidian
    └── hugo.toml
```

Obsidian vede `content/posts/` come normali file markdown.
Quando sei pronto a pubblicare, togli `draft: true` dal frontmatter e fai push.

---

## Workflow pubblicazione

```bash
# Nuovo articolo
hugo new content posts/titolo-articolo.md
# oppure crea direttamente il file in content/posts/

# Anteprima locale
hugo server -D   # -D mostra anche i draft

# Pubblica
# 1. Edita il file: draft: false
# 2. git add . && git commit -m "post: titolo articolo"
# 3. git push
# GitHub Actions fa il resto
```

---

## Note

- **Draft**: finché `draft: true` nel frontmatter, il file non viene pubblicato dal build di produzione.
- **RSS**: disponibile automaticamente su `/index.xml` — utile per Substack/LinkedIn.
- **Aggiornare Hugo**: cambia `HUGO_VERSION` in `.github/workflows/hugo.yml`.
- **Aggiornare PaperMod**: `git submodule update --remote --merge themes/PaperMod`
