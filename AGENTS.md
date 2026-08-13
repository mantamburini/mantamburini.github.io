# AGENTS.md — Blog Instrumenta

Contesto per agenti LLM (CLI, opencode, ecc.) che operano in questa repo. Leggere prima di qualsiasi modifica.

## 1. Cosa stai guardando

Repo `mantamburini.github.io`, pubblicata via GitHub Actions → GitHub Pages. Non è un progetto nuovo: è il riavvio di un blog che esisteva già con tema PaperMod, tono ironico, contenuti su metodologia della documentazione (post tipo "Chiedi a Mario", "Word ha vinto ma non ha ragione"). Quell'impostazione è stata abbandonata dopo un paio di post — non ha retto.

Quello che trovi nella cartella al momento è quel primo tentativo: config Hugo con tema PaperMod, eventuali contenuti vecchi. **Non è materiale da conservare**, tranne un'eccezione (vedi §3).

## 2. Cosa deve diventare

Sito personale: **Instrumenta**. Brain dump diretto di 20+ anni di esperienza in IT Operations, ITSM, Service Delivery (ruoli da Head of Operations — SPS Global, Berlin Packaging, Sopra Steria, Beta 80 Group). Target: manager in generale, non solo IT.

Non è un blog consulenziale da LinkedIn. Non aneddoti simpatici. Contenuto su decisioni sbagliate, persone che hanno insegnato qualcosa nel modo peggiore, processi saltati, convinzioni rivelatesi sbagliate col tempo.

Il nome viene dal capitolo IV della Regola di San Benedetto (*"Quae sunt instrumenta bonorum operum"*): gli strumenti concreti da esercitare ogni giorno, con costanza. Non un elenco di precetti dall'alto — coerente con "diretto, pratico, senza pretesa di guru".

Sottotitolo: **non ancora deciso**. Non inventarne uno nel `config.toml` — lascia il campo vuoto o commentato e segnala la cosa nel README/task list della repo.

## 3. Riutilizzo dal sito precedente: SOLO "Chi Sono"

L'unico contenuto da portare avanti dalla versione precedente è la pagina/sezione "Chi Sono" (o "About"), se esiste nella repo attuale (es. `content/about.md`, `content/chi-sono.md`, o pagina statica equivalente — cercala prima di procedere).

Regole:

- Recupera il testo esistente da dove si trova nella repo (non riscriverlo da zero, non inventarlo).
- Aggiornalo solo per coerenza col nuovo tono (diretto, niente frasi fatte) se il testo attuale è scritto nello stile ironico del vecchio blog — ma senza cambiare i fatti biografici.
- Tutto il resto del vecchio sito (post, tema, config PaperMod) va rimosso, non migrato.
- Se non trovi nessun contenuto "Chi Sono" preesistente nella repo, **fermati e chiedi a Marcello il testo** — non generarlo.

## 4. Setup tecnico

- **Generatore**: Hugo.
- **Tema**: **Hugo Bear** (deciso — sostituisce PaperMod). Non proporre alternative, non installare Hugo Terminal.
- **Pipeline**: GitHub Actions → GitHub Pages, invariata rispetto a prima. Verifica che il workflow esistente in `.github/workflows/` sia ancora coerente col nuovo tema (percorsi, versione Hugo, modulo del tema) e aggiornalo se necessario.
- **Dominio**: nessun dominio custom. Resta `mantamburini.github.io`. Il "flavour tecnico" dell'URL GitHub Pages è voluto, non un difetto da correggere.
- **Editor di riferimento**: nvim (non serve setup particolare lato repo).
- **Installazione tema**: seguire il metodo standard Hugo Modules o git submodule per Hugo Bear — usa quello raccomandato dalla documentazione ufficiale del tema, non improvvisare varianti.

## 5. Struttura dei contenuti da creare

Alberatura confermata — sette sezioni di primo livello. Creale come sezioni Hugo (`content/<sezione>/_index.md` + struttura per i post), con slug in italiano coerenti coi titoli sotto. Non aggiungere sezioni non elencate, non riordinare.

1. **Processi**
   - Perché lavorare per processi (sicurezza, ripetibilità, economia)
   - I trigger per le eccezioni
   - Misurazioni, KPI, SLA
   - Efficientamento
2. **Persone**
   - Gestione operativa del team
   - Percorsi di crescita e responsabilità
   - Assunzioni sbagliate
   - Gestione della crisi/incidente
3. **Comunicazione**
   - Verso il cliente/fornitore
   - Verso il basso (strategia condivisa)
   - Branding nei documenti e template
4. **Economia e negoziazione**
   - Accordi e contratti
   - Vendor management
   - Produttività delle commesse
   - Budget e negoziazione interna
5. **Cambiamento organizzativo**
   - Riorganizzazioni, fusioni, cambi di management sopra di te
6. **Reportistica**
   - Fonti dati e come collegarcisi
   - Scelta dello span temporale
   - Cosa presentare per dire cosa
   - Come presentare (formato, livello di dettaglio)
7. **Forma mentis / strumenti**
   - Perché markdown (e la forma mentis dietro la scelta)
   - Semplicità come scelta, non come limite

Nota: la sezione 6 (Reportistica) è volutamente più densa delle altre — non è un difetto della struttura, non uniformare artificialmente.

I sotto-punti elencati sono temi/possibili post, non necessariamente sotto-sezioni Hugo — a meno che il tema Bear preveda una gerarchia a due livelli che renda sensato crearle come tali. In caso di dubbio, crea solo le 7 sezioni di primo livello con `_index.md` e lascia i sotto-temi come backlog di post futuri (es. in un commento nel `_index.md` o in un file `TODO.md` nella root).

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
- Markdown-first: contenuti in `.md` semplice, front matter YAML minimo (titolo, data, sezione — non serve altro a meno che il tema Bear lo richieda).
- Workflow reale: la scrittura avviene in una cartella locale dentro un repo Codeberg esistente, poi viene pushata su GitHub per la pubblicazione. La CLI opera direttamente nella cartella del repo GitHub Pages — non serve replicare la sincronizzazione Codeberg, è un processo manuale di Marcello a monte.
- Se una decisione tecnica non è coperta da questo documento (es. dettagli di configurazione di Hugo Bear non specificati qui), non improvvisare in modo silenzioso: segnala la scelta fatta e perché, così Marcello può correggerla.

## 8. Task per questa sessione

1. Ispezionare la repo attuale: individuare tema installato (PaperMod), eventuale contenuto "Chi Sono", struttura esistente.
2. Rimuovere PaperMod e i contenuti del vecchio blog (post, config specifica del tema vecchio).
3. Installare Hugo Bear come tema.
4. Recuperare e portare avanti il "Chi Sono" esistente (§3) — fermarsi e chiedere se non lo trovi.
5. Creare le 7 sezioni di primo livello (§5) con `_index.md` minimale (titolo, front matter, nessun corpo lungo salvo eventuale descrizione breve della sezione).
6. Verificare/aggiornare il workflow GitHub Actions per il nuovo tema.
7. Riportare un riepilogo di cosa è stato fatto, cosa è stato rimosso, e ogni scelta presa in autonomia che merita revisione (sottotitolo, dettagli di config Hugo Bear, eventuale "Chi Sono" mancante).

Non pubblicare/mergiare automaticamente senza revisione esplicita di Marcello — questa sessione prepara lo scaffolding, non il deploy definitivo.
