# Guide d'implémentation Angular Material

## 🔧 Configuration initiale

### 1. Installation Angular Material

```bash
ng add @angular/material
# Choisir "Custom" pour le theme
# Choisir "Yes" pour les animations
# Choisir "Yes" pour les typography defaults
```

---

### 2. Configuration du theme custom

**Fichier : `src/styles.scss`**

```scss
@use '@angular/material' as mat;

// Include core styles
@include mat.core();

// Define custom primary palette (basé sur #1E40AF)
$custom-primary-palette: (
  50: #EEF2FF,
  100: #E0E7FF,
  200: #C7D2FE,
  300: #A5B4FC,
  400: #818CF8,
  500: #6366F1,
  600: #4F46E5,
  700: #4338CA,  // Closest to #1E40AF
  800: #3730A3,
  900: #312E81,
  A100: #8C9EFF,
  A200: #536DFE,
  A400: #3D5AFE,
  A700: #304FFE,
  contrast: (
    50: rgba(black, 0.87),
    100: rgba(black, 0.87),
    200: rgba(black, 0.87),
    300: rgba(black, 0.87),
    400: white,
    500: white,
    600: white,
    700: white,
    800: white,
    900: white,
    A100: rgba(black, 0.87),
    A200: white,
    A400: white,
    A700: white,
  )
);

$primary: mat.define-palette($custom-primary-palette, 700);
$accent: mat.define-palette(mat.$indigo-palette, A200, A100, A400);
$warn: mat.define-palette(mat.$red-palette);

// Create theme
$theme: mat.define-light-theme((
  color: (
    primary: $primary,
    accent: $accent,
    warn: $warn,
  ),
  typography: mat.define-typography-config(
    $font-family: 'Inter, "Helvetica Neue", sans-serif',
  ),
  density: 0,
));

// Include all component themes
@include mat.all-component-themes($theme);

// Custom CSS variables
:root {
  --primary: #1E40AF;
  --primary-light: #3B82F6;
  --primary-dark: #1E3A8A;
  
  --gray-50: #F9FAFB;
  --gray-100: #F3F4F6;
  --gray-200: #E5E7EB;
  --gray-500: #6B7280;
  --gray-700: #374151;
  --gray-900: #111827;
  
  --spacing-1: 8px;
  --spacing-2: 16px;
  --spacing-3: 24px;
  --spacing-4: 32px;
  --spacing-5: 40px;
  --spacing-6: 48px;
  --spacing-8: 64px;
  --spacing-16: 128px;
  
  --radius-base: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 24px;
}

// Global styles
body {
  font-family: 'Inter', sans-serif;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}
```

---

### 3. Importer Google Fonts

**Fichier : `src/index.html`**

```html
<head>
  <!-- ... -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
</head>
```

---

## 🧩 Structure des composants

### Architecture recommandée

```
src/app/
├── components/
│   ├── landing/
│   │   ├── landing.component.ts
│   │   ├── navbar/
│   │   │   └── navbar.component.ts
│   │   ├── hero-section/
│   │   │   └── hero-section.component.ts
│   │   ├── benefits-section/
│   │   │   ├── benefits-section.component.ts
│   │   │   └── benefit-card/
│   │   │       └── benefit-card.component.ts
│   │   ├── how-it-works-section/
│   │   │   ├── how-it-works-section.component.ts
│   │   │   └── step-card/
│   │   │       └── step-card.component.ts
│   │   ├── testimonials-section/
│   │   │   ├── testimonials-section.component.ts
│   │   │   └── testimonial-card/
│   │   │       └── testimonial-card.component.ts
│   │   ├── cta-section/
│   │   │   └── cta-section.component.ts
│   │   └── footer/
│   │       └── footer.component.ts
│   └── shared/
│       └── button/
│           └── button.component.ts
└── models/
    ├── benefit.model.ts
    ├── testimonial.model.ts
    └── step.model.ts
```

---

## 📝 Modèles de données

### benefit.model.ts

```typescript
export interface Benefit {
  icon: string;           // Material Icon name
  title: string;
  description: string;
}

export const BENEFITS: Benefit[] = [
  {
    icon: 'psychology',
    title: 'Conçu par des experts',
    description: 'Une solution développée par des acheteurs IT qui comprennent vos enjeux métier au quotidien.'
  },
  {
    icon: 'verified',
    title: 'Traçabilité complète',
    description: 'Suivez l\'intégralité du processus d\'approvisionnement de bout en bout avec une visibilité totale.'
  },
  {
    icon: 'analytics',
    title: 'Tableaux de bord en temps réel',
    description: 'Pilotez vos approvisionnements avec des indicateurs clairs et exploitez votre historique facilement.'
  },
  {
    icon: 'shield',
    title: 'Respect des tarifs négociés',
    description: 'Garantie du respect des TJM consentis par vos fournisseurs lors de vos appels d\'offres.'
  },
  {
    icon: 'groups',
    title: 'Référencement simplifié',
    description: 'Gérez facilement vos entreprises partenaires et ressources de confiance sur une seule plateforme.'
  },
  {
    icon: 'tune',
    title: 'Aide à la décision',
    description: 'Comparez compétences, tarifs et disponibilités pour choisir la meilleure ressource pour vos projets.'
  }
];
```

### testimonial.model.ts

```typescript
export interface Testimonial {
  initials: string;
  name: string;
  role: string;
  company: string;
  quote: string;
}

export const TESTIMONIALS: Testimonial[] = [
  {
    initials: 'MD',
    name: 'Marie Dubois',
    role: 'Directrice des Achats IT',
    company: 'TechCorp',
    quote: 'Place Conseil a transformé notre façon de gérer nos approvisionnements IT. La visibilité en temps réel nous a permis de réduire nos délais de 30%.'
  },
  {
    initials: 'JM',
    name: 'Jean Martin',
    role: 'DSI',
    company: 'Innovation Group',
    quote: 'Une plateforme intuitive qui nous fait gagner un temps précieux. Le système de comparaison des prestataires est particulièrement efficace.'
  },
  {
    initials: 'SL',
    name: 'Sophie Laurent',
    role: 'Responsable Achats',
    company: 'DigitalCo',
    quote: 'Enfin une solution pensée par des acheteurs ! La traçabilité complète et les tableaux de bord nous apportent la sérénité dont nous avions besoin.'
  }
];
```

### step.model.ts

```typescript
export interface Step {
  number: string;
  icon: string;
  title: string;
  description: string;
}

export const STEPS: Step[] = [
  {
    number: '01',
    icon: 'search',
    title: 'Trouvez le prestataire idéal',
    description: 'Publiez votre demande et recevez des propositions de prestataires qualifiés. Comparez les compétences, les tarifs et les disponibilités pour sélectionner la ressource la plus adaptée à votre projet.'
  },
  {
    number: '02',
    icon: 'track_changes',
    title: 'Suivez l\'avancement en temps réel',
    description: 'Pilotez vos projets avec nos tableaux de bord intuitifs. Consultez l\'historique complet, suivez les indicateurs clés et assurez le bon déroulement de vos approvisionnements.'
  }
];
```

---

## 🎨 Exemples de composants

### benefit-card.component.ts

```typescript
import { Component, Input } from '@angular/core';
import { Benefit } from '../../../models/benefit.model';

@Component({
  selector: 'app-benefit-card',
  template: `
    <mat-card class="benefit-card">
      <mat-card-header>
        <div mat-card-avatar class="benefit-icon">
          <mat-icon>{{ benefit.icon }}</mat-icon>
        </div>
      </mat-card-header>
      <mat-card-content>
        <h3 class="benefit-title">{{ benefit.title }}</h3>
        <p class="benefit-description">{{ benefit.description }}</p>
      </mat-card-content>
    </mat-card>
  `,
  styles: [`
    .benefit-card {
      height: 100%;
      transition: all 0.3s ease;
      cursor: default;
    }
    
    .benefit-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
      border-color: var(--primary-light);
    }
    
    .benefit-icon {
      width: 56px;
      height: 56px;
      background: var(--primary);
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    
    .benefit-icon mat-icon {
      color: white;
      font-size: 32px;
      width: 32px;
      height: 32px;
    }
    
    .benefit-title {
      font-size: 20px;
      font-weight: 600;
      color: var(--gray-900);
      margin-bottom: 16px;
    }
    
    .benefit-description {
      font-size: 16px;
      color: var(--gray-500);
      line-height: 1.6;
      margin: 0;
    }
  `]
})
export class BenefitCardComponent {
  @Input() benefit!: Benefit;
}
```

### benefits-section.component.ts

```typescript
import { Component } from '@angular/core';
import { BENEFITS, Benefit } from '../../../models/benefit.model';

@Component({
  selector: 'app-benefits-section',
  template: `
    <section class="benefits-section">
      <div class="container">
        <div class="section-header">
          <h2>Pourquoi choisir Place Conseil ?</h2>
          <p class="section-subtitle">
            Une plateforme pensée par des acheteurs, pour les acheteurs
          </p>
        </div>
        
        <div class="benefits-grid">
          <app-benefit-card 
            *ngFor="let benefit of benefits"
            [benefit]="benefit">
          </app-benefit-card>
        </div>
      </div>
    </section>
  `,
  styles: [`
    .benefits-section {
      padding: 128px 0;
      background: white;
    }
    
    .section-header {
      text-align: center;
      margin-bottom: 64px;
    }
    
    .section-header h2 {
      font-size: 40px;
      font-weight: 700;
      color: var(--gray-900);
      margin-bottom: 16px;
    }
    
    .section-subtitle {
      font-size: 18px;
      color: var(--gray-500);
      max-width: 700px;
      margin: 0 auto;
    }
    
    .benefits-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 32px;
    }
    
    .container {
      max-width: 1440px;
      margin: 0 auto;
      padding: 0 48px;
    }
  `]
})
export class BenefitsSectionComponent {
  benefits: Benefit[] = BENEFITS;
}
```

---

## 🔘 Composants Material à utiliser

### Buttons

```html
<!-- Primary button -->
<button mat-raised-button color="primary">
  Nous contacter
</button>

<!-- Outline button -->
<button mat-stroked-button>
  En savoir plus
</button>

<!-- Large button -->
<button mat-raised-button color="primary" class="btn-large">
  Découvrir la plateforme
</button>
```

**CSS custom pour buttons :**

```scss
.btn-large {
  padding: 16px 32px !important;
  font-size: 18px !important;
  height: auto !important;
  line-height: normal !important;
}

.mat-raised-button.mat-primary {
  background-color: var(--primary) !important;
}

.mat-stroked-button {
  border-color: white !important;
  color: white !important;
}
```

---

### Cards

```html
<mat-card>
  <mat-card-header>
    <div mat-card-avatar class="custom-avatar">
      <mat-icon>psychology</mat-icon>
    </div>
  </mat-card-header>
  <mat-card-content>
    <h3>Titre de la card</h3>
    <p>Description</p>
  </mat-card-content>
</mat-card>
```

---

### Icons

```html
<mat-icon>search</mat-icon>
<mat-icon>track_changes</mat-icon>
<mat-icon>verified</mat-icon>
<mat-icon>analytics</mat-icon>
```

---

## 📦 Modules à importer

**Fichier : `app.module.ts` ou module dédié**

```typescript
import { MatButtonModule } from '@angular/material/button';
import { MatCardModule } from '@angular/material/card';
import { MatIconModule } from '@angular/material/icon';
import { MatToolbarModule } from '@angular/material/toolbar';

@NgModule({
  imports: [
    MatButtonModule,
    MatCardModule,
    MatIconModule,
    MatToolbarModule,
  ],
  // ...
})
```

---

## ✅ Checklist d'implémentation

### Setup (30min)
- [ ] `ng add @angular/material`
- [ ] Configurer theme custom dans `styles.scss`
- [ ] Ajouter Google Fonts dans `index.html`
- [ ] Créer variables CSS custom

### Composants (4-6h)
- [ ] Créer structure dossiers
- [ ] Créer modèles de données
- [ ] Implémenter `navbar.component`
- [ ] Implémenter `hero-section.component`
- [ ] Implémenter `benefits-section.component` + `benefit-card.component`
- [ ] Implémenter `how-it-works-section.component` + `step-card.component`
- [ ] Implémenter `testimonials-section.component` + `testimonial-card.component`
- [ ] Implémenter `cta-section.component`
- [ ] Implémenter `footer.component`

### Intégration (2h)
- [ ] Assembler dans `landing.component`
- [ ] Configurer routing
- [ ] Ajouter logo assets
- [ ] Ajouter image hero
- [ ] Tester smooth scroll

### Tests (1h)
- [ ] Test navigation
- [ ] Test hover states
- [ ] Test liens externes
- [ ] Test compatibilité navigateurs

---

## 🚀 Commandes utiles

```bash
# Générer un composant
ng g c components/landing/hero-section

# Générer un modèle
ng g interface models/benefit

# Lancer en dev
ng serve

# Build production
ng build --prod
```

---

## 📞 Notes techniques

- **Smooth scroll :** Ajouter `scroll-behavior: smooth` dans le CSS global ou utiliser `ViewportScroller`
- **Sticky navbar :** Utiliser `position: sticky` ou Material Toolbar avec custom CSS
- **Hover animations :** Utiliser transitions CSS (200-300ms ease)
- **Performance :** Lazy load les images, utiliser `trackBy` dans les `*ngFor`

---

*Guide créé le 21/11/2025*
