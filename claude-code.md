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
