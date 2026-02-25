# 🚀 Guida Pubblicazione su GitHub
## Step-by-Step per Principianti

**Tempo stimato:** 15-20 minuti per la prima volta

---

## Prerequisiti

1. **Account GitHub:** Se non ce l'hai, crea uno su https://github.com/signup (gratuito)
2. **Git installato:** 
   - Mac: `brew install git` (o già installato)
   - Linux: `sudo apt-get install git`
   - Windows: https://git-scm.com/download/win

3. **File del corso:** I materiali che ho preparato

---

## 🎯 Opzione 1: Pubblicazione Rapida (Raccomandata per iniziare)

### Via GitHub Web Interface (NO command line)

**Vantaggi:** Facile, visuale, no terminal  
**Svantaggi:** Meno controllo, no history locale

#### Step 1: Crea Repository su GitHub

1. Vai su https://github.com
2. Login con tuo account
3. Click su **"+"** in alto a destra → **"New repository"**
4. Compila:
   - **Repository name:** `conway-to-langgraph` (o nome che preferisci)
   - **Description:** `Course: From Conway to LangGraph - Agent Systems for Physicists`
   - **Public** ✓ (o Private se preferisci)
   - **✓ Add README file** (deseleziona - ne hai già uno)
   - **Add .gitignore:** Python
   - **License:** None (aggiungerai manualmente)
5. Click **"Create repository"**

#### Step 2: Upload Files

1. Nel repository appena creato, click **"Add file"** → **"Upload files"**
2. Drag & drop TUTTA la cartella del corso
3. O click "choose your files" e seleziona tutto
4. In fondo, scrivi commit message: `Initial commit - Week 1 materials`
5. Click **"Commit changes"**

✅ **Fatto!** Il tuo corso è online!

---

## 🎯 Opzione 2: Pubblicazione via Git (Più Professionale)

### Via Command Line

**Vantaggi:** Full control, proper git workflow, easier updates  
**Svantaggi:** Richiede terminal

#### Step 1: Prepara i File Localmente

```bash
# Vai nella cartella del corso
cd /path/to/github_repo

# Verifica contenuto
ls
# Dovresti vedere: README.md, week01_elementary_ca/, environment.yml, etc.
```

#### Step 2: Inizializza Git

```bash
# Inizializza repository Git locale
git init

# Aggiungi tutti i file
git add .

# Verifica cosa stai per committare
git status

# Primo commit
git commit -m "Initial commit - Week 1 complete materials"
```

#### Step 3: Crea Repository su GitHub

1. Vai su https://github.com
2. Click **"+"** → **"New repository"**
3. **Nome:** `conway-to-langgraph`
4. **Public** (o Private)
5. **NON** selezionare "Initialize with README" (ne hai già uno!)
6. Click **"Create repository"**

#### Step 4: Connetti Locale a Remoto

GitHub ti mostrerà comandi. Usa questi:

```bash
# Aggiungi remote (sostituisci YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/conway-to-langgraph.git

# Rinomina branch a 'main' (se necessario)
git branch -M main

# Push al remote
git push -u origin main
```

**Inserisci credenziali quando richiesto** (username + personal access token)

✅ **Fatto!** Repository online!

---

## 🔑 Setup Personal Access Token (Se Necessario)

GitHub non accetta più password. Serve un token:

1. GitHub → **Settings** (tuo profilo) → **Developer settings**
2. **Personal access tokens** → **Tokens (classic)**
3. **Generate new token**
4. **Note:** `Course repository access`
5. **Expiration:** 90 days (o No expiration)
6. **Scopes:** Seleziona `repo` (full control)
7. **Generate token**
8. **COPIA IL TOKEN** (lo vedrai una sola volta!)
9. Usalo come password quando push

---

## 📝 Workflow Quotidiano (Dopo Setup Iniziale)

### Quando Aggiungi/Modifichi Materiale

```bash
# 1. Verifica cosa è cambiato
git status

# 2. Aggiungi modifiche
git add .
# O singoli file: git add week02_game_of_life/

# 3. Commit con messaggio descrittivo
git commit -m "Add Week 2: Game of Life materials"

# 4. Push su GitHub
git push
```

### Comandi Utili

```bash
# Vedere cronologia commit
git log --oneline

# Vedere diff prima di committare
git diff

# Annullare modifiche non committate
git checkout -- filename

# Creare un branch per sperimentare
git checkout -b experimental
```

---

## 🎨 Personalizzazione Repository

### 1. Aggiungi Banner/Logo

1. Crea immagine (1200x400 px consigliato)
2. Salva come `assets/images/banner.png`
3. Nel README.md, l'immagine sarà già referenziata

### 2. Abilita GitHub Pages (Opzionale)

Per avere un website del corso:

1. Repository → **Settings** → **Pages**
2. **Source:** Deploy from a branch
3. **Branch:** main → `/docs`
4. Click **Save**

Il sito sarà su: `https://YOUR-USERNAME.github.io/conway-to-langgraph/`

### 3. Abilita Discussions

Per forum studenti:

1. Repository → **Settings** → **Features**
2. **✓ Discussions**
3. Ora hai tab "Discussions" per Q&A

### 4. Abilita Issues (già attivo di default)

Studenti possono segnalare problemi/bugs.

### 5. Aggiungi Topics (Tags)

1. Repository page → Click ⚙️ accanto a "About"
2. **Topics:** `education`, `physics`, `cellular-automata`, `machine-learning`, `langchain`
3. Aiuta altri a trovare il corso

---

## 📦 Distribuzione Materiale agli Studenti

### Opzione A: Repository Pubblico (Raccomandato)

**Studenti fanno:**
```bash
git clone https://github.com/YOUR-USERNAME/conway-to-langgraph.git
cd conway-to-langgraph
conda env create -f environment.yml
```

**Pro:** Semplice, tutti vedono aggiornamenti  
**Contro:** Materiale visibile a tutti

### Opzione B: Repository Privato + Collaborators

1. Repository → **Settings** → **Collaborators**
2. Aggiungi username GitHub studenti
3. Stesso workflow di prima, ma solo invitati vedono

**Pro:** Controllo accesso  
**Contro:** Devi aggiungere ogni studente manualmente

### Opzione C: Releases per Settimana

**Workflow:**
1. Prepara materiale Week 1
2. GitHub → **Releases** → **Create a new release**
3. **Tag:** `v1.0-week1`
4. **Title:** "Week 1: Elementary Cellular Automata"
5. **Attach files:** ZIP con materiale
6. Condividi link release con studenti

**Pro:** Rilascio graduale, download singolo  
**Contro:** No git workflow per studenti

---

## 🔒 Opzioni Privacy

### Repository Pubblico
- ✅ Chiunque può vedere
- ✅ Buono per portfolio docente
- ✅ Altri possono riusare materiale (con attribuzione)
- ⚠️ Studenti vedono esercizi e soluzioni (separa soluzioni!)

### Repository Privato
- ✅ Solo invitati vedono
- ✅ Controllo totale accesso
- ❌ Meno visibilità per tuo lavoro
- ⚠️ GitHub Free: limite a 3 collaborators (o conta come educational account)

### Educational Account (Gratis, Raccomandato)

Richiedi su: https://education.github.com/teachers

**Benefici:**
- ✅ Repository privati illimitati
- ✅ Collaborators illimitati
- ✅ GitHub Classroom (per gestire assignments)
- ✅ GitHub Copilot gratuito

---

## 📊 GitHub Classroom (Opzionale, Avanzato)

Per gestire assignments automaticamente:

1. Vai su https://classroom.github.com/
2. Login con account GitHub
3. **New Classroom** → Link a course organization
4. **New Assignment** → Crea template
5. Studenti accettano link → Fork automatico
6. Tu vedi tutti i submission in una dashboard

**Vantaggi:** Auto-grading, feedback diretto, no email floods

---

## 🐛 Troubleshooting Comune

### Problema: "Permission denied (publickey)"

**Soluzione:** Setup SSH key o usa HTTPS con token.

HTTPS è più semplice:
```bash
git remote set-url origin https://github.com/YOUR-USERNAME/conway-to-langgraph.git
```

### Problema: "Repository not found"

**Soluzione:** Verifica nome repository e che sia pubblico (o sei collaborator).

### Problema: "Large files rejected"

**Soluzione:** GitHub ha limite 100MB per file. Per file grandi:
1. Aggiungi a `.gitignore`
2. Usa Git LFS (Large File Storage)
3. O host su Google Drive/Dropbox e linka

### Problema: "Merge conflict"

**Soluzione:**
```bash
# Pull prima di push
git pull origin main

# Risolvi conflitti manualmente (aprono in editor)
# Poi:
git add .
git commit -m "Resolve merge conflict"
git push
```

---

## ✅ Checklist Pre-Pubblicazione

Prima di rendere repo pubblico, verifica:

- [ ] README.md è chiaro e completo
- [ ] LICENSE file presente
- [ ] .gitignore configurato (no file grandi)
- [ ] Tutti i path relativi funzionano
- [ ] Notebook eseguono senza errori
- [ ] environment.yml testato
- [ ] Contact info aggiornato
- [ ] No informazioni sensibili (email personale, password)
- [ ] Link a risorse esterne funzionano

---

## 📧 Comunicazione con Studenti

**Email tipo:**

```
Oggetto: [Fisica Matematica] Materiale Corso GitHub

Cari studenti,

il materiale del corso "From Conway to LangGraph" è ora disponibile su GitHub:

🔗 https://github.com/YOUR-USERNAME/conway-to-langgraph

**Setup (10 minuti):**
1. Installate Git: https://git-scm.com/downloads
2. Aprite terminal e navigate dove volete il corso
3. Eseguite: git clone [link sopra]
4. Seguite istruzioni in README.md

**Ogni settimana:**
- Aggiorno repository con nuovo materiale
- Voi fate: git pull (dentro cartella corso)
- Nuovo materiale appare automaticamente!

Per domande: usate GitHub Discussions (no email per favore!)

Link discussions: https://github.com/YOUR-USERNAME/conway-to-langgraph/discussions

Ci vediamo lunedì!

Prof. [Nome]
```

---

## 🎓 Risorse Aggiuntive

### Imparare Git
- **Guida interattiva:** https://learngitbranching.js.org/
- **GitHub Skills:** https://skills.github.com/
- **Pro Git Book (gratis):** https://git-scm.com/book/it/v2

### GitHub per Educazione
- **GitHub Education:** https://education.github.com/
- **GitHub Classroom docs:** https://docs.github.com/en/education/manage-coursework-with-github-classroom

---

## 🚀 Prossimi Passi

Dopo aver pubblicato Week 1:

1. ✅ Testa che studenti possano clonare
2. ✅ Chiedi feedback su chiarezza README
3. ✅ Monitora Issues/Discussions
4. ✅ Prepara Week 2 in branch separato
5. ✅ Merge quando pronto

---

**Domande?** Chiedimi pure! Sono qui per aiutare. 🤝

---

*Ultimo aggiornamento: Febbraio 2025*
