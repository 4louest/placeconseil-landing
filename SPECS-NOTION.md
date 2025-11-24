# Landing Page Place Conseil - Spécifications Design

## 📋 Informations projet

**Client :** Norbert Miconnet  
**Projet :** Refonte landing page Place Conseil  
**Date :** 21/11/2025  
**Designer :** Alexandre Saury  
**Statut :** Design completed ✅

---

## 🎯 Objectifs

- Moderniser l'interface avec une couleur primaire #1E40AF
- Supprimer le module de recherche
- Ajouter une section témoignages
- Améliorer la conversion avec des CTA clairs
- Design professionnel et épuré

---

## 🎨 Design System

### Couleurs

| Nom | Hex | Usage |
|-----|-----|-------|
| **Primary** | `#1E40AF` | Boutons, accents, fond hero |
| **Primary Light** | `#3B82F6` | Hover states |
| **Primary Dark** | `#1E3A8A` | Emphasis, gradient |
| **Brand Bordeaux** | `#4d1434` | Logo (existant) |
| **White** | `#FFFFFF` | Backgrounds |
| **Gray 50** | `#F9FAFB` | Backgrounds alternés |
| **Gray 200** | `#E5E7EB` | Borders |
| **Gray 500** | `#6B7280` | Texte secondaire |
| **Gray 900** | `#111827` | Texte principal |
| **Success** | `#10B981` | Validation |

### Typographie

**Font :** Inter (Google Fonts)

| Style | Size | Weight | Line Height |
|-------|------|--------|-------------|
| Hero Title | 56px | 800 | 110% |
| H2 (Sections) | 40px | 700 | 120% |
| H3 (Cards) | 24px | 600 | 130% |
| H4 | 20px | 600 | 140% |
| Body Large | 20px | 400 | 160% |
| Body | 16px | 400 | 160% |
| Body Small | 14px | 400 | 160% |

### Spacing

Système basé sur 8px :  
`8px | 16px | 24px | 32px | 40px | 48px | 64px | 80px | 96px | 128px`

### Border Radius

`4px | 8px | 12px | 16px | 24px`

---

## 📐 Structure des sections

### 1️⃣ Navbar (Sticky)

**Dimensions :**
- Hauteur : 80px
- Position : Fixed top
- Background : White
- Border bottom : 1px solid Gray-200

**Contenu :**
- Logo + "Place Conseil" (left)
- Navigation : Fonctionnalités | Comment ça marche | Témoignages
- Button CTA : "Nous contacter" (primary)

---

### 2️⃣ Hero Section

**Layout :** Grid 2 colonnes (50/50)  
**Padding vertical :** 128px  
**Background :** Linear gradient 135deg, Primary → Primary Dark

**Colonne gauche :**
```
Titre H1 (56px/800/white)
"Optimisez vos approvisionnements en prestations IT"

Sous-titre (20px/400/white 90%)
"La plateforme de gestion des approvisionnements..."

[CTA Primary: Découvrir la plateforme]
[CTA Outline: Contactez-nous]
```

**Colonne droite :**
- Image : COMPETITIVE-IT-009-2880w.jpg
- Border-radius : 24px
- Box-shadow : Large

---

### 3️⃣ Section Bénéfices

**Layout :** Grid 3 colonnes  
**Padding vertical :** 128px  
**Background :** White

**Header :**
```
H2: "Pourquoi choisir Place Conseil ?"
Sous-titre: "Une plateforme pensée par des acheteurs, pour les acheteurs"
```

**6 Cards :**

| Icon | Titre | Description |
|------|-------|-------------|
| psychology | Conçu par des experts | Une solution développée par des acheteurs IT qui comprennent vos enjeux métier au quotidien. |
| verified | Traçabilité complète | Suivez l'intégralité du processus d'approvisionnement de bout en bout avec une visibilité totale. |
| analytics | Tableaux de bord en temps réel | Pilotez vos approvisionnements avec des indicateurs clairs et exploitez votre historique facilement. |
| shield | Respect des tarifs négociés | Garantie du respect des TJM consentis par vos fournisseurs lors de vos appels d'offres. |
| groups | Référencement simplifié | Gérez facilement vos entreprises partenaires et ressources de confiance sur une seule plateforme. |
| tune | Aide à la décision | Comparez compétences, tarifs et disponibilités pour choisir la meilleure ressource pour vos projets. |

**Card specs :**
- Border : 1px solid Gray-200
- Border-radius : 16px
- Padding : 32px
- Hover : translateY(-4px) + shadow-lg + border Primary-light
- Icon : 56×56px, background Primary, border-radius 12px

---

### 4️⃣ Section Comment ça marche

**Layout :** Flex horizontal avec divider  
**Padding vertical :** 128px  
**Background :** Gray-50

**Header :**
```
H2: "Comment ça marche ?"
Sous-titre: "Un processus simple et efficace en 2 étapes"
```

**Step 1 : Trouvez le prestataire idéal**
- Number : 01 (72px/800/Gray-200)
- Icon : search (64×64px, Primary background)
- Titre : "Trouvez le prestataire idéal" (24px/600)
- Description : "Publiez votre demande et recevez des propositions de prestataires qualifiés. Comparez les compétences, les tarifs et les disponibilités pour sélectionner la ressource la plus adaptée à votre projet."

**Divider :** → (Material Icon arrow_forward, 48px, Primary)

**Step 2 : Suivez l'avancement en temps réel**
- Number : 02
- Icon : track_changes
- Titre : "Suivez l'avancement en temps réel" (24px/600)
- Description : "Pilotez vos projets avec nos tableaux de bord intuitifs. Consultez l'historique complet, suivez les indicateurs clés et assurez le bon déroulement de vos approvisionnements."

**Card specs :**
- Background : White
- Border-radius : 16px
- Padding : 40px
- Min-height : 340px
- Box-shadow : Medium

---

### 5️⃣ Section Témoignages

**Layout :** Grid 3 colonnes  
**Padding vertical :** 128px  
**Background :** White

**Header :**
```
H2: "Ils nous font confiance"
Sous-titre: "Découvrez les retours de nos clients"
```

**3 Témoignages (placeholders) :**

**Témoignage 1**
- Avatar : MD (initiales) - Primary background
- Nom : Marie Dubois
- Rôle : Directrice des Achats IT, TechCorp
- Citation : "Place Conseil a transformé notre façon de gérer nos approvisionnements IT. La visibilité en temps réel nous a permis de réduire nos délais de 30%."

**Témoignage 2**
- Avatar : JM
- Nom : Jean Martin
- Rôle : DSI, Innovation Group
- Citation : "Une plateforme intuitive qui nous fait gagner un temps précieux. Le système de comparaison des prestataires est particulièrement efficace."

**Témoignage 3**
- Avatar : SL
- Nom : Sophie Laurent
- Rôle : Responsable Achats, DigitalCo
- Citation : "Enfin une solution pensée par des acheteurs ! La traçabilité complète et les tableaux de bord nous apportent la sérénité dont nous avions besoin."

**Card specs :**
- Border : 1px solid Gray-200
- Border-radius : 16px
- Padding : 32px
- Quote icon : format_quote (48px, Primary-light 20% opacity)
- Avatar : 48×48px circle

---

### 6️⃣ CTA Finale

**Layout :** Center aligned  
**Padding vertical :** 128px  
**Background :** Linear gradient 135deg, Primary → Primary Dark

**Contenu :**
```
H2 (48px/700/white)
"Prêt à optimiser vos approvisionnements IT ?"

Sous-titre (20px/white 90%)
"Rejoignez les entreprises qui font confiance à Place Conseil pour gérer leurs prestations intellectuelles IT"

[CTA Primary: Contactez-nous] (mailto:contact@placeconseil.com)
[CTA Outline White: En savoir plus sur Competitive IT]
```

---

### 7️⃣ Footer

**Layout :** Grid 3 colonnes (2fr 1fr 1fr)  
**Padding :** 64px top, 32px bottom  
**Background :** Gray-900  
**Color :** White

**Colonne 1 : Branding**
- Logo (version blanche)
- "Place Conseil"
- Description courte

**Colonne 2 : Contact**
- Email : contact@placeconseil.com
- Adresse : COMPETITIVE IT, 45 rue de Maubeuge, 75009 Paris

**Colonne 3 : Réseaux sociaux**
- LinkedIn : https://www.linkedin.com/company/place-conseil/

**Footer bottom :**
- Copyright © 2025 Place Conseil. Tous droits réservés.
- Liens : Mentions légales | Cookies | CGV | RGPD

---

## 📦 Livrables

✅ Prototype HTML/CSS fonctionnel  
✅ Design tokens (JSON)  
✅ Documentation technique complète  
✅ Guide d'implémentation Angular Material  
✅ Logo Place Conseil

---

## 🚀 Prochaines étapes

### Phase actuelle : Design Desktop ✅
- [x] Design system complet
- [x] Maquette HTML/CSS
- [x] Documentation technique
- [x] Design tokens

### Phase suivante : Implémentation Angular
- [ ] Setup Angular Material theme
- [ ] Créer composants (navbar, hero, sections, footer)
- [ ] Intégrer contenu réel
- [ ] Tests navigateurs

### Phase ultérieure : Responsive
- [ ] Version tablette (768px)
- [ ] Version mobile (375px)
- [ ] Menu hamburger
- [ ] Grid adaptatif

---

## 📞 Notes

**Important :** Les témoignages sont des placeholders. À remplacer par des vrais témoignages clients.

**Image hero :** Utiliser l'image COMPETITIVE-IT-009-2880w.jpg fournie par le client.

**Responsive :** Non inclus dans cette phase. Fera l'objet d'un projet spécifique.

---

*Document créé le 21/11/2025*
