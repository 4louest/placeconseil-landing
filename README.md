# Documentation technique - Landing Page Place Conseil

## 📋 Vue d'ensemble

Refonte complète de la landing page Place Conseil avec un design moderne, une couleur primaire #1E40AF (indigo blue), et une structure optimisée pour la conversion.

---

## 🎨 Design System

### Palette de couleurs

#### Couleurs primaires
```css
--primary: #1E40AF        /* Indigo blue principal */
--primary-light: #3B82F6  /* Variante claire (hover states) */
--primary-dark: #1E3A8A   /* Variante foncée (emphasis) */
```

#### Couleurs de marque (logo)
```css
--brand-bordeaux: #4d1434       /* Couleur logo existant */
--brand-bordeaux-light: #6B1D4A /* Variante claire */
```

#### Couleurs neutres
```css
--white: #FFFFFF
--gray-50: #F9FAFB    /* Backgrounds alternés */
--gray-100: #F3F4F6
--gray-200: #E5E7EB   /* Borders */
--gray-300: #D1D5DB
--gray-500: #6B7280   /* Text secondaire */
--gray-700: #374151
--gray-900: #111827   /* Text principal */
```

#### Couleurs d'accent
```css
--success: #10B981    /* Validation, success states */
```

---

### Typographie

**Font family :** Inter (Google Fonts)
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
```

**Échelle typographique :**
```css
Hero title:    56px / 800 / line-height: 1.1
H2 (sections): 40px / 700 / line-height: 1.2
H3 (cards):    24px / 600 / line-height: 1.3
H4 (footer):   16px / 600 / line-height: 1.4
Body large:    20px / 400 / line-height: 1.6
Body:          16px / 400 / line-height: 1.6
Body small:    14px / 400 / line-height: 1.6
```

---

### Spacing System

Système basé sur un multiple de 8px :
```css
--spacing-1: 8px
--spacing-2: 16px
--spacing-3: 24px
--spacing-4: 32px
--spacing-5: 40px
--spacing-6: 48px
--spacing-8: 64px
--spacing-10: 80px
--spacing-12: 96px
--spacing-16: 128px
```

---

### Border Radius
```css
--radius-sm: 4px
--radius-base: 8px
--radius-md: 12px
--radius-lg: 16px
--radius-xl: 24px
```

---

### Shadows
```css
--shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05)
--shadow-base: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06)
--shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06)
--shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05)
```

---

## 📐 Structure de la page

### 1. Navbar (Sticky)
**Hauteur :** 80px
**Position :** Sticky top
**Contenu :**
- Logo + nom de marque (left)
- Navigation : Fonctionnalités | Comment ça marche | Témoignages
- CTA : "Nous contacter" (button primary)

**Specs techniques :**
```css
background: white
border-bottom: 1px solid gray-200
box-shadow: shadow-sm
z-index: 1000
```

---

### 2. Hero Section
**Padding vertical :** 128px (spacing-16)
**Background :** Linear gradient 135deg, primary → primary-dark
**Layout :** Grid 2 colonnes (50/50)

**Colonne gauche (texte) :**
- Titre H1 : 56px / 800 / color: white
- Sous-titre : 20px / 400 / color: white 90% opacity
- 2 CTA buttons :
  - Primary : "Découvrir la plateforme"
  - Secondary outline : "Contactez-nous"

**Colonne droite (image) :**
- Image illustration bureau/équipe
- Border-radius: 24px
- Box-shadow: lg

---

### 3. Section Bénéfices
**Padding vertical :** 128px
**Background :** White
**Layout :** Grid 3 colonnes

**Header :**
- Titre : "Pourquoi choisir Place Conseil ?"
- Sous-titre : "Une plateforme pensée par des acheteurs, pour les acheteurs"

**6 Cards :**
Chaque card :
- Border: 1px solid gray-200
- Border-radius: 16px
- Padding: 32px
- Hover: translateY(-4px) + shadow-lg + border primary-light

**Contenu card :**
- Icon : 56×56px, background primary, border-radius 12px, Material Icons 32px white
- Titre : 20px / 600 / gray-900
- Description : 16px / 400 / gray-500

**Liste des 6 bénéfices :**
1. **Conçu par des experts** (psychology)
2. **Traçabilité complète** (verified)
3. **Tableaux de bord en temps réel** (analytics)
4. **Respect des tarifs négociés** (shield)
5. **Référencement simplifié** (groups)
6. **Aide à la décision** (tune)

---

### 4. Section Comment ça marche
**Padding vertical :** 128px
**Background :** Gray-50
**Layout :** Flex horizontal avec divider

**Header :**
- Titre : "Comment ça marche ?"
- Sous-titre : "Un processus simple et efficace en 2 étapes"

**2 Steps :**

**Step 1 : Trouvez le prestataire idéal**
- Number: 01 (72px / 800 / gray-200 / absolute position)
- Icon: search (64×64px, primary background)
- Titre: 24px / 600
- Description: 16px / 400 / gray-500

**Step 2 : Suivez l'avancement en temps réel**
- Number: 02
- Icon: track_changes
- Titre: 24px / 600
- Description: 16px / 400 / gray-500

**Divider :** Material Icon arrow_forward (48px, primary)

**Card specs :**
- Background: white
- Border-radius: 16px
- Padding: 40px
- Min-height: 340px
- Box-shadow: md

---

### 5. Section Témoignages
**Padding vertical :** 128px
**Background :** White
**Layout :** Grid 3 colonnes

**Header :**
- Titre : "Ils nous font confiance"
- Sous-titre : "Découvrez les retours de nos clients"

**3 Cards témoignages :**

**Témoignage 1 :**
- Auteur : Marie Dubois
- Rôle : Directrice des Achats IT, TechCorp
- Citation : "Place Conseil a transformé notre façon de gérer nos approvisionnements IT. La visibilité en temps réel nous a permis de réduire nos délais de 30%."

**Témoignage 2 :**
- Auteur : Jean Martin
- Rôle : DSI, Innovation Group
- Citation : "Une plateforme intuitive qui nous fait gagner un temps précieux. Le système de comparaison des prestataires est particulièrement efficace."

**Témoignage 3 :**
- Auteur : Sophie Laurent
- Rôle : Responsable Achats, DigitalCo
- Citation : "Enfin une solution pensée par des acheteurs ! La traçabilité complète et les tableaux de bord nous apportent la sérénité dont nous avions besoin."

**Card specs :**
- Border: 1px solid gray-200
- Border-radius: 16px
- Padding: 32px
- Quote icon: Material Icons format_quote (48px, primary-light, opacity 20%)
- Avatar: 48×48px circle, primary background, initiales white

---

### 6. CTA Finale
**Padding vertical :** 128px
**Background :** Linear gradient 135deg, primary → primary-dark
**Layout :** Center aligned

**Contenu :**
- Titre : "Prêt à optimiser vos approvisionnements IT ?" (48px / 700 / white)
- Sous-titre : "Rejoignez les entreprises qui font confiance à Place Conseil..." (20px / white 90%)
- 2 CTA buttons :
  - Primary : "Contactez-nous" (mailto)
  - Outline white : "En savoir plus sur Competitive IT"

---

### 7. Footer
**Padding :** 64px top, 32px bottom
**Background :** Gray-900
**Color :** White
**Layout :** Grid 3 colonnes (2fr 1fr 1fr)

**Colonne 1 : Branding**
- Logo (filter: brightness(0) invert(1) pour version blanche)
- Nom de marque
- Description courte

**Colonne 2 : Contact**
- Email : contact@placeconseil.com
- Adresse : COMPETITIVE IT, 45 rue de Maubeuge, 75009 Paris

**Colonne 3 : Réseaux sociaux**
- LinkedIn

**Footer bottom :**
- Copyright © 2025
- Liens légaux : Mentions légales | Cookies | CGV | RGPD

---

## 🔧 Mapping Angular Material

### Theme configuration
```typescript
// angular.json ou styles.scss
@use '@angular/material' as mat;

$custom-primary: mat.define-palette((
  50: #EEF2FF,
  100: #E0E7FF,
  200: #C7D2FE,
  300: #A5B4FC,
  400: #818CF8,
  500: #6366F1,
  600: #4F46E5,
  700: #4338CA,
  800: #3730A3,
  900: #312E81,
  contrast: (
    50: #000000,
    100: #000000,
    200: #000000,
    300: #000000,
    400: #FFFFFF,
    500: #FFFFFF,
    600: #FFFFFF,
    700: #FFFFFF,
    800: #FFFFFF,
    900: #FFFFFF,
  )
), 700); // default: 700 (#1E40AF proche)

$custom-accent: mat.define-palette(mat.$indigo-palette, A200, A100, A400);
$custom-warn: mat.define-palette(mat.$red-palette);

$custom-theme: mat.define-light-theme((
  color: (
    primary: $custom-primary,
    accent: $custom-accent,
    warn: $custom-warn,
  ),
  typography: mat.define-typography-config(
    $font-family: 'Inter, sans-serif',
  ),
));

@include mat.all-component-themes($custom-theme);
```

### Composants Angular Material à utiliser

**Buttons :**
```html
<button mat-raised-button color="primary">Primary</button>
<button mat-stroked-button>Outline</button>
```

**Cards :**
```html
<mat-card>
  <mat-card-header>
    <mat-icon mat-card-avatar>psychology</mat-icon>
  </mat-card-header>
  <mat-card-content>...</mat-card-content>
</mat-card>
```

**Icons :**
```html
<mat-icon>search</mat-icon>
<mat-icon>track_changes</mat-icon>
```

---

## 📦 Fichiers livrés

```
placeconseil-landing/
├── index.html              # Page complète HTML
├── styles.css              # Tous les styles CSS
├── logo.png                # Logo Place Conseil
├── design-tokens.json      # Tokens de design (couleurs, typo, spacing)
└── README.md              # Cette documentation
```

---

## ✅ Checklist d'implémentation Angular

### Phase 1 : Setup
- [ ] Installer Angular Material : `ng add @angular/material`
- [ ] Configurer le theme custom avec la palette #1E40AF
- [ ] Importer Google Fonts Inter dans index.html
- [ ] Importer Material Icons

### Phase 2 : Structure
- [ ] Créer composant `navbar`
- [ ] Créer composant `hero-section`
- [ ] Créer composant `benefits-section`
- [ ] Créer composant `how-it-works-section`
- [ ] Créer composant `testimonials-section`
- [ ] Créer composant `cta-section`
- [ ] Créer composant `footer`

### Phase 3 : Composants réutilisables
- [ ] Créer composant `benefit-card` (atom)
- [ ] Créer composant `testimonial-card` (atom)
- [ ] Créer composant `step-card` (atom)
- [ ] Créer composant `button` custom si besoin

### Phase 4 : Contenu
- [ ] Remplacer placeholders témoignages par vrais témoignages
- [ ] Ajouter vraie image hero
- [ ] Vérifier tous les liens (mailto, LinkedIn, etc.)

### Phase 5 : Tests
- [ ] Test navigation smooth scroll
- [ ] Test hover states sur tous les éléments interactifs
- [ ] Test liens externes (Competitive IT, LinkedIn)
- [ ] Test compatibilité navigateurs (Chrome, Firefox, Safari, Edge)

---

## 🚀 Next Steps (Non inclus dans cette phase)

### Responsive Design
- Version tablette (768px)
- Version mobile (375px)
- Menu hamburger mobile
- Grid adaptatif

### Animations
- Scroll reveal animations (AOS ou GSAP)
- Hover animations avancées
- Transitions entre sections
- Parallax hero

### Features avancées
- Formulaire de contact intégré
- Carousel témoignages
- Statistiques animées
- Video hero
- Chat widget

---

## 📞 Support

Pour toute question sur l'implémentation :
1. Consulter le prototype HTML/CSS fourni
2. Référencer les design tokens JSON
3. Suivre la checklist d'implémentation

**Temps estimé d'implémentation Angular :** 2-3 jours pour un dev confirmé

---

*Documentation générée le 21/11/2025*
