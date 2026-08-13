# AGENTS.md — Blog Instrumenta

Contesto per agenti LLM (CLI, opencode, ecc.) che operano in questa repo. Leggere prima di qualsiasi modifica.

## 1. Stato attuale

Repo `mantamburini.github.io`, pubblicata via GitHub Actions → GitHub Pages. Riavvio completo di un vecchio blog (PaperMod, poi Hugo Theme Stack, poi LoveIt) la cui impostazione è stata abbandonata. Tutto il materiale precedente è stato rimosso: la repo è stata ricostruita da zero con il tema Hugo Bear.

Struttura attuale:

- **Home** (`content/_index.md`): contiene il testo "Chi sono", recuperato dal vecchio sito. Non esiste più una pagina `/about/`.
- **Post**: in `content/blog/`, categorizzati via tag. Nessuna sezione tematica.
- **Menu** in `hugo.toml`: Home, Blog, Tags.
- **`TODO.md`**: backlog dei post e nota sul sottotitolo.

## 2. Cosa deve diventare

Sito personale: **Instrumenta**. Brain dump diretto di 20+ anni di esperienza in IT Operations, ITSM, Service Delivery (ruoli da Head of Operations — SPS Global, Berlin Packaging, Sopra Steria, Beta 80 Group). Target: manager in generale, non solo IT.

Non è un blog consulenziale da LinkedIn. Non aneddoti simpatici. Contenuto su decisioni sbagliate, persone che hanno insegnato qualcosa nel modo peggiore, processi saltati, convinzioni rivelatesi sbagliate col tempo.

Il nome viene dal capitolo IV della Regola di San Benedetto (*"Quae sunt instrumenta bonorum operum"*): gli strumenti concreti da esercitare ogni giorno, con costanza. Non un elenco di precetti dall'alto — coerente con "diretto, pratico, senza pretesa di guru".

Sottotitolo: **non ancora deciso**. Lasciato vuoto di proposito in `hugo.toml` (`params.description`). Non inventarne uno; la cosa è segnalata in `TODO.md`.

## 3. Chi sono / Home

Il testo "Chi sono" è stato recuperato dal vecchio sito e vive nel corpo di `content/_index.md` (non esiste più una pagina dedicata). Regole:

- Non riscriverlo da zero, non inventare fatti biografici.
- Modificarlo solo per coerenza col tono (§6), senza cambiare i fatti.

## 4. Setup tecnico

- **Generatore**: Hugo (versione allineata al workflow, oggi 0.164.0+extended).
- **Tema**: **Hugo Bear** (`janraasch/hugo-bearblog`), installato come git submodule in `themes/hugo-bearblog`. Non proporre alternative, non installare Hugo Terminal.
- **Config**: `hugo.toml` minimale Bear. Usa `locale = "it-IT"`, non `languageCode` (deprecato da Hugo 0.158). Sottotitolo vuoto.
- **Pipeline**: GitHub Actions → GitHub Pages, invariata. Il workflow fa `submodules: recursive`, quindi il tema submodule viene recuperato da solo.
- **Dominio**: nessun dominio custom. Resta `mantamburini.github.io`. Il "flavour tecnico" dell'URL GitHub Pages è voluto, non un difetto da correggere.
- **Editor di riferimento**: nvim (non serve setup particolare lato repo).

## 5. Struttura dei contenuti

Decisione presa in sessione: **niente sezioni tematiche**. Un tentativo a 7 sezioni è stato abbandonato; i contenuti sono organizzati per **tag**.

- I post vivono in `content/blog/` (struttura nativa del tema Bear: solo lì il tipo è `blog` e il tema mostra la data; in `content/posts/` la data sparirebbe).
- Creare un post con `hugo new blog/nome-post.md`: usa gli archetype del tema. Nessun archetype a livello sito.
- Un post con `draft: true` nel front matter non viene pubblicato. Per vederlo in locale: `hugo server -D`.
- I tag funzionano coi default di Hugo, senza configurazione extra: pagina `/tags/`, pagine `/tags/<tag>/`, link `#tag` nei post e nella lista `/blog/`.
- Front matter minimo: `title`, `date`, `draft`, `tags`.

Le aree tematiche del blog (processi, persone, comunicazione, economia e negoziazione, cambiamento organizzativo, reportistica, forma mentis) restano valide come spunto per tag e post — vedi il backlog in `TODO.md`. Non vanno create come sezioni.

## 6. Stile di scrittura — vincolante per qualsiasi contenuto generato

Se produci testo di esempio, placeholder o contenuto reale per le pagine, applica queste regole (derivate dalla skill personale di Marcello, `anti-ai-writing-style`):

- Niente aperture tipo "Ottima domanda", "Bentornati", entusiasmo posticcio.
- Niente costruzioni "Non è solo X, è Y" o "X non è solo un tool, è un mindset".
- Niente parole da marketing/consulenza: *leverage*, *robust*, *seamlessly*, *holistic*, *comprehensive*, *cutting-edge*, *game-changer*, ecc. (e i loro equivalenti italiani: "sinergie", "a 360 gradi", "best practice" usato come riempitivo).
- Niente chiusure tipo "Spero che questo sia utile" o inviti a "esplorare oltre".
- Frasi dirette, un'idea per paragrafo. Se qualcosa è complesso, spiega cosa lo rende complesso — non limitarti a etichettarlo come tale.
- Nessuna emoji.
- Questo vincolo si applica ancora più rigidamente qui rispetto ad altri contesti, per via del tono richiesto dal sito (diretto, senza pretesa di guru, niente linguaggio da consulente).

Se generi solo struttura/scaffolding (file `_index.md` con front matter e titolo, senza corpo) questa sezione si applica comunque a qualsiasi testo descrittivo che scrivi.

## 7. Principi operativi (da rispettare in ogni scelta tecnica)

- **KISS**: se una configurazione, un plugin o uno shortcode non è strettamente necessario, non aggiungerlo. Niente overengineering del setup Hugo.
- Markdown-first: contenuti in `.md` semplice, front matter YAML minimo (`title`, `date`, `draft`, `tags` — non serve altro a meno che il tema Bear lo richieda).
- Workflow reale: la scrittura avviene in una cartella locale dentro un repo Codeberg esistente, poi viene pushata su GitHub per la pubblicazione. La CLI opera direttamente nella cartella del repo GitHub Pages — non serve replicare la sincronizzazione Codeberg, è un processo manuale di Marcello a monte.
- Se una decisione tecnica non è coperta da questo documento, non improvvisare in modo silenzioso: segnala la scelta fatta e perché, così Marcello può correggerla.

## 8. Convenzioni operative

- Il deploy avviene al push su `main` via GitHub Actions. Non committare/pubblicare senza richiesta esplicita di Marcello.
- Prima di un commit, verificare la build locale (`hugo`) e che eventuali post `draft: true` non compaiano in `public/`.
- Se una scelta non è coperta da questo documento, segnalarla invece di decidere in silenzio (§7).
