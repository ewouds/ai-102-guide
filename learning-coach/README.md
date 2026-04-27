# AI Learning Coach — Drop-in Kit

Een AI-gestuurde studiecoach voor Azure certificeringen en tech learning paths.
Oorspronkelijk gebouwd voor AI-102 prep, maar werkt voor elke certificering.

---

## Quick Start — Stap voor stap

### Stap 1: Fork deze repo

1. Ga naar deze repo op GitHub
2. Klik **Fork** (rechtsboven)
3. Kies je eigen account
4. Je hebt nu `<jouw-username>/ai-102-guide` (hernoem eventueel naar je eigen cert)

### Stap 2: Clone lokaal

```bash
git clone https://github.com/<jouw-username>/ai-102-guide.git
cd ai-102-guide
```

### Stap 3: GitHub Pages aanzetten

1. Ga naar je repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main`, folder: `/ (root)`
4. Save
5. Na ~1 minuut is je guide live op `https://<jouw-username>.github.io/ai-102-guide/`

### Stap 4: Git credentials instellen

Je hebt een **Personal Access Token (PAT)** nodig om te kunnen pushen:

1. Ga naar <https://github.com/settings/tokens?type=beta> (Fine-grained tokens)
2. Klik **Generate new token**
3. Naam: bijv. `ai-learning-coach`
4. Expiration: 90 dagen (of langer)
5. Repository access: **Only select repositories** → kies je fork
6. Permissions → Repository permissions:
   - **Contents**: Read and write
   - **Pages**: Read and write
7. Generate token → **kopieer het token** (je ziet het maar 1x!)

**Credentials opslaan** (zodat je niet elke keer het token moet invoeren):

```bash
# Optie A: Git credential helper (slaat token op na eerste keer invoeren)
git config --global credential.helper store

# Bij eerste push: username = je GitHub username, password = je PAT
git push origin main
# Username: <jouw-username>
# Password: <plak hier je PAT>

# Optie B: Token direct in remote URL (handig voor automation)
git remote set-url origin https://<jouw-username>:<PAT>@github.com/<jouw-username>/ai-102-guide.git
```

> ⚠️ **Bewaar je PAT veilig!** Zet het niet in bestanden die je commit. Gebruik een password manager of environment variable.

### Stap 5: Studieplan invullen

1. Open `learning-coach/study-plan-template.md`
2. Vul in voor jouw certificering (zie voorbeeld hieronder)
3. Commit en push:

```bash
git add -A
git commit -m "Studieplan ingevuld voor [cert]"
git push origin main
```

### Stap 6: Start met studeren!

Open een chat in **GitHub Copilot** of **Microsoft Copilot** en plak:

```
Lees dit bestand als je instructies: [plak inhoud van COACH.md]

Hier is mijn studieplan: [plak inhoud van study-plan-template.md]

Ik wil beginnen met [topic]. Start met een intake quiz.
```

**GitHub Copilot in VS Code:**
- Open je repo in VS Code
- Kopieer `learning-coach/COACH.md` naar `.github/copilot-instructions.md` in je repo root
- Nu heeft elke Copilot Chat automatisch de coach context
- Verwijs naar je studieplan met `#file:learning-coach/study-plan-template.md`

---

## Voorbeeld: AZ-900 Azure Fundamentals

Zo zou je het studieplan invullen voor AZ-900:

```markdown
# Studieplan — AZ-900 Azure Fundamentals

Status: 🔴 todo | 🟡 bezig | ✅ done
Tempo: ~4 uur/week
Start: mei 2026
Exam guide: https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-900

## Fase 1: Cloud Concepts (25-30%)
### Week 1: Cloud fundamentals
- [ ] Wat is cloud computing (IaaS, PaaS, SaaS)
- [ ] Shared responsibility model
- [ ] Public/private/hybrid cloud
- [ ] Benefits of cloud (HA, scalability, elasticity, agility)
- 📚 MS Learn: Azure Fundamentals learning path

### Week 2: Azure architecture
- [ ] Regions, availability zones, region pairs
- [ ] Subscriptions, management groups, resource groups
- [ ] Azure Resource Manager (ARM)
- 🔨 Lab: Maak een resource group + storage account via de portal

## Fase 2: Azure Services (15-20%)
### Week 3-4: Compute & Networking
- [ ] VMs, App Service, Containers, AKS, Functions
- [ ] VNet, subnets, NSG, load balancer, VPN, ExpressRoute
- 🔨 Lab: Deploy een VM + configureer NSG
...
```

---

## Na elke studiesessie

Dit is het belangrijkste deel — na elke sessie doe je altijd:

1. ✅ **Studieplan updaten** — checkboxes afvinken, quiz scores toevoegen
2. ✅ **Reference guide updaten** — samenvatting van geleerde stof in HTML
3. ✅ **Pushen naar GitHub** — guide wordt automatisch gepubliceerd

```bash
cd <repo-dir>
# ... update bestanden ...
git add -A
git commit -m "Sessie [datum]: [topic] — [korte samenvatting]"
git push origin main
# GitHub Pages updatet automatisch binnen ~1 minuut
```

---

## GitHub Pages Reference Guide

Een belangrijk onderdeel van deze aanpak: na elke studiesessie wordt een **reference guide** bijgewerkt en gepubliceerd via GitHub Pages. Dit geeft je:

- Een levende samenvatting die meegroeit met je studie
- Een doorzoekbare referentie voor exam prep
- Zichtbare voortgang

### Structuur

```
repo/
├── index.html              ← hoofdpagina met overzicht + voortgang
├── cheatsheet.html         ← snelle referentie (commands, concepten, tips)
├── services.html           ← per-topic pagina (voorbeeld)
├── learning-coach/
│   ├── COACH.md            ← system prompt voor je AI coach
│   ├── README.md           ← dit bestand
│   └── study-plan-template.md  ← studieplan template
```

---

## Wat zit erin?

| File | Wat doet het |
|------|-------------|
| `COACH.md` | System prompt — laad dit in je AI tool als instructies |
| `study-plan-template.md` | Studieplan framework met quiz systeem en fases |
| `README.md` | Deze handleiding |

## Aanpassen

- Pas het studieplan aan voor jouw certificering (fases, topics, tijdlijn)
- De coach werkt voor elke Azure cert (AZ-104, AZ-305, AI-102, DP-100, etc.)
- Voeg je eigen resources toe (MS Learn paths, YouTube, labs)
- Pas de HTML template aan naar je eigen stijl
