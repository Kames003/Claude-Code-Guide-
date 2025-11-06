📋 Terminal Guide (/terminal-guide)

Toto je super dôležitý príkaz pre prácu s terminálom v Claude Code!
bash# V Claude Code session napíš:
/terminal-guide
```

**Čo to robí:**
- Dá Claude Code prístup k terminálu
- Môže spúšťať príkazy (build, test, git, npm, atď.)
- Vidí output z príkazov
- Dokáže debugovať chyby z terminálu

**Príklad použitia:**
```
Ty: "/terminal-guide"
Claude: [aktivuje terminal access]

Ty: "Spusti npm install a potom npm run build"
Claude: [vykoná príkazy a povie ti výsledok]

Ty: "Testy failujú, oprav to"
Claude: [vidí error output z testov a opraví kód]

🎯 Init príkaz (./init = CLAUDE.md)
Toto je game changer pre poskytovanie kontextu!
Čo je CLAUDE.md?
CLAUDE.md je špeciálny súbor v roote projektu, kde definuješ:

Architektúru projektu
Coding standards
Pravidlá a konvencie
Context o projekte
Štruktúru kde čo má byť

Vytvorenie CLAUDE.md:
bash# V Claude Code:
./init
Alebo manuálne vytvor súbor CLAUDE.md v roote projektu.
📝 Príklad CLAUDE.md:
markdown# Project: Moja E-commerce Aplikácia

## Architektúra
- Frontend: React 18 + TypeScript + Vite
- Styling: Tailwind CSS + CSS Modules
- State: Zustand
- Backend: Node.js + Express
- Database: PostgreSQL + Prisma

## Štruktúra projektu
```
src/
├── components/     # React komponenty
│   ├── ui/        # Reusable UI komponenty
│   └── features/  # Feature-specific komponenty
├── pages/         # Page komponenty
├── hooks/         # Custom React hooks
├── utils/         # Helper funkcie
├── api/           # API calls
└── types/         # TypeScript typy
```

## Coding Standards
- Používaj funkcionálne komponenty s hooks
- Každý komponent má vlastný test súbor
- Props destructuring na začiatku komponentu
- Named exports (nie default)
- Camel case pre premenné, Pascal case pre komponenty

## Konvencie pomenovávania
- Komponenty: `UserProfile.tsx`
- Hooks: `useUserData.ts`
- Utils: `formatDate.ts`
- Types: `user.types.ts`
- Tests: `UserProfile.test.tsx`

## Pravidlá
- Vždy TypeScript strict mode
- ESLint + Prettier pre formatting
- Všetky komponenty musia mať PropTypes/TypeScript types
- API calls cez centralizovaný api/ folder
- Error handling everywhere
- Loading states pre async operácie

## Stack-specific notes
- Icons: Používaj lucide-react
- Forms: React Hook Form + Zod validácia
- Routing: React Router v6
- API: Axios s interceptormi
🎯 Prečo je to dôležité?
Claude Code automaticky číta CLAUDE.md a:

✅ Dodržiava tvoje pravidlá
✅ Vytvára súbory na správnych miestach
✅ Používa tvoje konvencie
✅ Rozumie architektúre projektu
✅ Nepýta sa na veci ktoré si už definoval


🌳 Tree Structure - Definovanie kde čo vytvoriť
V CLAUDE.md môžeš definovať stromovú štruktúru:
markdown## File Structure Template

Keď vytváraš nový feature:
```
src/features/[feature-name]/
├── components/
│   ├── [Feature]List.tsx
│   ├── [Feature]Detail.tsx
│   └── [Feature]Form.tsx
├── hooks/
│   └── use[Feature].ts
├── api/
│   └── [feature].api.ts
├── types/
│   └── [feature].types.ts
└── index.ts
```

## Component Template
Každý nový komponent:
```typescript
import { FC } from 'react';
import styles from './[Component].module.css';

interface [Component]Props {
  // props tu
}

export const [Component]: FC = ({ }) => {
  return (
    
      {/* content */}
    
  );
};
```
```

**Príklad použitia:**
```
Ty: "Vytvor feature pre Product management"

Claude: [automaticky vytvorí celú štruktúru]:
src/features/product/
├── components/
│   ├── ProductList.tsx
│   ├── ProductDetail.tsx
│   └── ProductForm.tsx
├── hooks/
│   └── useProduct.ts
├── api/
│   └── product.api.ts
├── types/
│   └── product.types.ts
└── index.ts

📎 Manual File Reference (@mention)
Môžeš manuálne špecifikovať súbory ktoré chceš aby Claude videl:
bash# V Claude Code session:

Ty: "@src/components/Header.tsx skontroluj tento komponent"
Claude: [načíta a analyzuje Header.tsx]

Ty: "@src/utils/api.ts @src/types/user.types.ts 
     updatuj API aby používalo nové user typy"
Claude: [pracuje s oboma súbormi]

# Multiple files:
Ty: "@src/components/*.tsx pridaj error boundaries do všetkých"
```

**Prečo to používať:**
- Explicitne ukážeš Claude čo potrebuje
- Rýchlejšie ako opisovať kde čo je
- Presné targeting pri veľkých projektoch

---

## 🔄 Git Operations - Merging & Committing

### Commitovanie:
```
Ty: "Commitni zmeny s message 'Add user authentication'"

# Alebo kompletnejšie:
Ty: "Stagni všetky zmeny, commitni s message 
     'feat: add user login and registration' 
     a pushni do origin/feature-auth"
```

### Merging:
```
Ty: "Mergni feature-auth branch do main"

Ty: "Ukáž mi diff medzi main a feature-auth pred mergom"

Ty: "Resolvni merge konflikty v src/App.tsx"
```

### Git Workflow príklad:
```
Ty: "Vytvor nový branch feature-payments"
Claude: [vytvorí branch]

Ty: "Implementuj Stripe payment integration"
Claude: [naprogramuje feature]

Ty: "Vytvor testy pre payment flow"
Claude: [vytvorí testy]

Ty: "Spusti testy, ak passujú, commitni a pushni"
Claude: [vykoná všetko automaticky]

Ty: "Vytvor pull request description"
Claude: [vygeneruje PR description s changelogom]

🎨 Komplexný Real-World Example
Setup:
1. Inicializuj projekt s CLAUDE.md:
bashcd ~/projects/moj-eshop
claude-code

# V Claude Code:
./init
2. CLAUDE.md obsah:
markdown# E-shop Project

## Stack
React + TypeScript + Tailwind + Zustand + React Query

## Structure
src/
├── features/        # Feature-based architecture
├── components/ui/   # Shared UI components
├── lib/            # Utilities, configs
└── types/          # Global types

## Rules
- shadcn/ui pre UI komponenty
- TanStack Query pre data fetching
- Zod pre validácie
- Všetko TypeScript strict
```

**3. Práca s projektom:**
```
Ty: "/terminal-guide"
Ty: "Vytvor feature pre shopping cart podľa našej štruktúry"

Claude: [vytvorí kompletnú feature]:
- features/cart/components/
- features/cart/hooks/useCart.ts
- features/cart/store/cartStore.ts
- features/cart/types/

Ty: "@features/cart/hooks/useCart.ts 
     pridaj funkciu na kalkuláciu shipping cost"

Claude: [upraví hook]

Ty: "Spusti npm run build a oprav akékoľvek TypeScript errors"

Claude: [buildne, vidí errors, opraví ich]

Ty: "Commitni všetko: 'feat: add shopping cart with 
     shipping calculation'"

Claude: [commitne]
```

---

## 💪 Pro Tips

**1. Kombinuj príkazy:**
```
Ty: "/terminal-guide"
Ty: "@CLAUDE.md @src/features/user/*.tsx 
     refaktoruj user feature podľa aktuálnych standards"
```

**2. Iteratívny development:**
```
Ty: "Vytvor payment feature skeleton"
→ Claude vytvorí štruktúru

Ty: "Teraz implementuj Stripe integration"
→ Claude doprogramuje

Ty: "Pridaj error handling a loading states"
→ Claude vylepší

Ty: "Vytvor tests"
→ Claude otestuje

Ty: "Spusti testy, oprav bugs, commitni"
→ Claude finalizuje
3. Documentation-first approach:
Najprv vytvor dobrý CLAUDE.md, potom nechaj Claude robiť!


---- 

  prakticky pre spustenie novej konverzácie stačí napísať : claude 
  je to čistý štart bez historie 

  # Automaticky pokračuje v poslednej konverzácii
  claude --continue

  # Interaktívny picker - zobrazí zoznam konverzácií s popisom, časom, počtom správ
  claude --resume

  ----

   Scenár B: Worktrees (pokročilé) 🚀

  | Situácia                     | Postup                           | Výhoda                     | Nevýhoda                  |
  |------------------------------|----------------------------------|----------------------------|---------------------------|
  | Implementuješ API na vetva   | Vytvoríš worktree feature-api    | Dva Claude sessions naraz! | Zložitejší setup          |
  | Súčasne refaktoruješ DB      | Vytvoríš worktree refactor-db    | Každý má vlastnú Git vetvu | Viac disk space           |
  | Obe sessions bežia paralelne | Každý worktree = vlastný adresár | Žiadne Git konflikty       | Musíš spravovať worktrees |

  Každý worktree má svoj Git stav (branch, súbory, Claude session)

  ---
  Kedy použiť čo?

  ✅ Resume - Použiť keď:

  - Pracuješ na jednej veci v danom čase
  - Chceš len organizovať konverzácie tematicky
  - Nechceš riešiť Git vetvy/worktrees
  - → Tvoj prípad: teória vs. implementácia v rôznych časoch

  ✅ Worktrees - Použiť keď:

  - Chceš súčasne pracovať na viacerých vetvách (napr. feature-api a bugfix-parser)
  - Potrebuješ dva Claude sessions naraz (jeden na API, druhý na frontend)
  - Chceš izolovať zmeny v súboroch (aby si nepretekali)
  - → Príklad: Backend dev na feature-api + Frontend dev na feature-ui súčasne

  ---
  Setup Worktrees (ak by si ich chcel skúsiť neskôr):

  # 1. Si v hlavnom projekte
  cd /home/tomasmucha/event-tracker-project

  # 2. Vytvor worktree pre implementáciu API (nová vetva feature-api)
  git worktree add backend-api-dev -b feature-api

  # 3. Vytvor worktree pre refaktoring DB (nová vetva refactor-db)
  git worktree add backend-db-refactor -b refactor-db

  # 4. Zoznam worktrees
  git worktree list
  # Výstup:
  # /home/tomasmucha/event-tracker-project        ae5bb90 [master]
  # /home/tomasmucha/backend-api-dev              ae5bb90 [feature-api]
  # /home/tomasmucha/backend-db-refactor          ae5bb90 [refactor-db]

  # 5. V každom adresári spusť Claude
  cd backend-api-dev
  claude  # Session 1 - API implementácia

  # V druhom termináli
  cd ../backend-db-refactor
  claude  # Session 2 - DB refaktoring

  # 6. Keď skončíš, vymaž worktree
  git worktree remove backend-api-dev

  ---
----


 Worktrees + Claude sessions = Multi-agent systém v praxi:

  Analógia s Multi-Agent systémom:

  | Multi-Agent koncept           | Worktree + Claude implementácia             |
  |-------------------------------|---------------------------------------------|
  | Agent 1 (Backend specialist)  | Worktree backend-api + Claude session 1     |
  | Agent 2 (Frontend specialist) | Worktree frontend-ui + Claude session 2     |
  | Agent 3 (Database expert)     | Worktree db-optimization + Claude session 3 |
  | Vlastný workspace             | Každý worktree = izolovaný adresár          |
  | Vlastná pamäť/kontext         | Každá Claude session = vlastná história     |
  | Paralelná práca               | Všetky sessions bežia súčasne               |
  | Komunikácia/integrácia        | Git merge branches na konci                 |
  | Task assignment               | Ty rozdeľuješ úlohy medzi sessions          |

  ---
  Praktický príklad multi-agent workflow:

  # Agent 1: Backend API Developer
  cd /home/tomasmucha/event-tracker-project
  git worktree add agent-backend -b feature/rest-api
  cd agent-backend
  claude
  # → Úloha: "Implementuj REST API endpointy pre positions a trackers"

  # Agent 2: Frontend Developer (v druhom termináli)
  cd /home/tomasmucha/event-tracker-project
  git worktree add agent-frontend -b feature/web-ui
  cd agent-frontend
  claude
  # → Úloha: "Vytvor React komponent pre zobrazenie mapy s trackermi"

  # Agent 3: Database Optimizer (v treťom termináli)
  cd /home/tomasmucha/event-tracker-project
  git worktree add agent-db -b optimize/timescaledb
  cd agent-db
  clau

  # Všetci traja pracujú SÚČASNE na rôznych častiach projektu!

  ---
  Výhody tohto "multi-agent" prístupu:

  ✅ Paralelizmus - viacero úloh súčasne✅ Izolácia - žiadne Git konflikty medzi agentmi✅ Špecializácia - každý agent má jasne definovanú úlohu✅ Kontext - každý agent si pamätá len svoj task (nie je
  zahltený inými témami)✅ Integrácia - nakoniec merge všetko cez Git

  ---
  Reálny use case pre tvoj projekt:

  # Agent 1: "MQTT Parser Expert"
  # Worktree: parser-improvements
  # Task: Doladenie validácií, bug fixing, edge cases

  # Agent 2: "API Developer"  
  # Worktree: rest-api
  # Task: Flask endpointy, WebSocket real-time updates

  # Agent 3: "Frontend Engineer"
  # Worktree: web-app
  # Task: React UI, mapa, dashboard, grafy

  Každý agent má:
  - Vlastnú Git vetvu (bez konfliktov)
  - Vlastnú Claude session (špecializovaný kontext)
  - Vlastný working directory (izolácia súborov)

  Na konci:
  git checkout master
  git merge parser-improvements
  git merge rest-api
  git merge web-app
  # → Všetko integrované! 🎉

  ---
  Porovnanie s "klasickým" multi-agent frameworkom:

  | Framework (napr. CrewAI, AutoGen)  | Worktree + Claude                         |
  |------------------------------------|-------------------------------------------|
  | Agenti komunikujú cez API/messages | Komunikujú cez Git (commits, branches)    |
  | Orchestrátor riadi workflow        | Ty riadeš workflow manuálne               |
  | Automatická koordinácia            | Manuálna koordinácia (merge)              |
  | Jeden proces, viacero agentov      | Viacero procesov, každý = agent           |
  | Vysoká komplexita                  | Nízka komplexita, prirodzený Git workflow |

  ---
  Takže áno - máš pravdu! 🎯

  Worktrees sú low-tech, praktická implementácia multi-agent systému, kde:
  - Git = koordinačný mechanizmus
  - Worktrees = workspaces pre agentov
  - Claude sessions = samotní agenti

  Je to elegantné, jednoduché, a funguje s nástrojmi, ktoré už poznáš (Git)!

---

