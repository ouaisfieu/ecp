# Documentation Technique — ECP

> Documentation complète du projet Économie Contributive Provisionnée

**Version** : 1.0.0  
**Date** : Janvier 2026  
**Auteur** : CCPLC  

---

## Table des matières

1. [Vue d'ensemble](#1-vue-densemble)
2. [Architecture du site](#2-architecture-du-site)
3. [Design System](#3-design-system)
4. [Contenu éditorial](#4-contenu-éditorial)
5. [Données et fact-checking](#5-données-et-fact-checking)
6. [Analyse juridique détaillée](#6-analyse-juridique-détaillée)
7. [Partenaires potentiels](#7-partenaires-potentiels)
8. [Déploiement](#8-déploiement)
9. [Maintenance](#9-maintenance)
10. [Annexes](#10-annexes)

---

## 1. Vue d'ensemble

### 1.1 Objectif du projet

L'ECP (Économie Contributive Provisionnée) vise à créer un nouveau modèle permettant aux personnes hors emploi de contribuer à des projets d'utilité sociale sans perdre leurs droits sociaux.

### 1.2 Public cible

| Segment | Besoin | Message clé |
|---------|--------|-------------|
| **Décideurs politiques** | Comprendre le modèle et son cadre légal | "Un dispositif compatible avec le droit existant" |
| **Mutuelles & syndicats** | Évaluer le partenariat | "Un écosystème déjà structuré" |
| **ASBL & porteurs de projet** | Recruter des contributeurs | "Des ressources humaines sans coût salarial" |
| **Personnes hors emploi** | Comprendre leurs droits | "Contribuer sans risquer vos allocations" |
| **Grand public** | Soutenir le mouvement | "975 000 vies en suspens, une solution existe" |

### 1.3 Positionnement

```
                    TECHNIQUE ←────────────────────────→ GRAND PUBLIC
                         │                                    │
                         │      ┌─────────────────────┐      │
            Rapport      │      │                     │      │   Campagne
            juridique    │      │   SITE ECP          │      │   médias
            INAMI        │      │   (notre position)  │      │   sociaux
                         │      │                     │      │
                         │      └─────────────────────┘      │
                         │                                    │
                    INSTITUTIONNEL ←──────────────────→ CITOYEN
```

Le site ECP se positionne au centre : accessible au grand public mais rigoureux dans les données.

---

## 2. Architecture du site

### 2.1 Structure des sections

```
┌─────────────────────────────────────────────────────────────────┐
│ HERO                                                            │
│ • Accroche émotionnelle (975 000 vies)                         │
│ • Badge fact-checké                                             │
│ • CTA principal + secondaire                                    │
│ • Strip de 4 statistiques clés                                  │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 01 — LE PROBLÈME                                                │
│ • Visualisation du "piège" (3 boxes)                           │
│ • 3 cartes avec chiffres détaillés                             │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 02 — LE COÛT                                                    │
│ • 3 barres de coût animées                                      │
│ • Encart total (21-24 Mrd€)                                    │
│ • Alerte correction                                             │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 03 — LA SOLUTION                                                │
│ • Flow en 5 étapes (cercles + ligne)                           │
│ • Fond sombre pour contraste                                    │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 04 — ANALYSE JURIDIQUE                                          │
│ • 6 cartes (2 danger, 2 warning, 2 success)                    │
│ • Bordure supérieure colorée selon statut                       │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 05 — FACT-CHECK                                                 │
│ • Résumé (16 confirmés, 8 approx, 5 corrigés)                  │
│ • Tableau complet des données                                   │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 06 — FEUILLE DE ROUTE                                           │
│ • Timeline verticale (2025, 2026, 2027-2029)                   │
│ • Ligne gradient vermillon → émeraude                          │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ 07 — PARTENAIRES                                                │
│ • Grid de 8 cartes                                              │
│ • Type + nom + chiffre                                          │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ CTA FINAL                                                       │
│ • Fond sombre                                                   │
│ • 2 boutons (contact + téléchargement)                         │
└─────────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────────┐
│ FOOTER                                                          │
│ • 4 colonnes (brand, nav, ressources, sources)                 │
│ • Licence + date                                                │
└─────────────────────────────────────────────────────────────────┘
```

### 2.2 Navigation

| Élément | Comportement |
|---------|--------------|
| Logo | Retour en haut (smooth scroll) |
| Liens sections | Smooth scroll vers ancre |
| État actif | Détection via IntersectionObserver |
| CTA "Rejoindre" | Style bouton plein |
| Scroll > 50px | Background blur + shadow |

### 2.3 Responsive breakpoints

| Breakpoint | Comportement |
|------------|--------------|
| `> 1024px` | Layout complet, grilles 4 colonnes |
| `768px - 1024px` | Grilles 2 colonnes, nav complète |
| `< 768px` | Grilles 1 colonne, nav masquée |

---

## 3. Design System

### 3.1 Palette de couleurs

#### Couleurs principales

```css
/* Encre (texte) */
--ink: #0f0f0f;
--ink-80: #2a2a2a;
--ink-60: #4a4a4a;
--ink-40: #7a7a7a;
--ink-20: #b0b0b0;
--ink-10: #d8d8d8;
--ink-05: #ececec;

/* Papier (fond) */
--paper: #FDFCFA;
--paper-warm: #F8F6F1;
--paper-dark: #EFECE5;

/* Accent principal */
--vermillon: #E63B2E;
--vermillon-soft: rgba(230, 59, 46, 0.1);
--vermillon-glow: rgba(230, 59, 46, 0.3);
```

#### Couleurs sémantiques

```css
/* Succès / Confirmé */
--emerald: #0D9668;
--emerald-soft: rgba(13, 150, 104, 0.1);

/* Attention / Approximatif */
--amber: #D97706;
--amber-soft: rgba(217, 119, 6, 0.1);

/* Accent secondaire */
--sapphire: #2563EB;
--sapphire-soft: rgba(37, 99, 235, 0.08);
```

### 3.2 Typographie

#### Familles

| Usage | Police | Fallback |
|-------|--------|----------|
| Titres éditoriaux | Newsreader | Georgia, serif |
| Corps de texte | Inter | system-ui, sans-serif |
| Données/code | JetBrains Mono | monospace |

#### Échelle typographique

```css
/* Titres */
.hero-title     { font-size: clamp(2.75rem, 7vw, 5rem); }
.section-title  { font-size: clamp(2rem, 4vw, 3rem); }
.card-title     { font-size: 1.25rem; }

/* Corps */
.body           { font-size: 1rem; /* 16px */ }
.small          { font-size: 0.875rem; }
.caption        { font-size: 0.8125rem; }
.micro          { font-size: 0.6875rem; }
```

### 3.3 Espacements

```css
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
--space-24: 6rem;     /* 96px */
--space-32: 8rem;     /* 128px */
```

### 3.4 Composants

#### Boutons

```html
<!-- Primaire -->
<a href="#" class="btn btn-primary">Texte →</a>

<!-- Secondaire -->
<a href="#" class="btn btn-secondary">Texte</a>
```

#### Badges

```html
<!-- Statut confirmé -->
<span class="factcheck-badge confirmed">✓ Confirmé</span>

<!-- Statut attention -->
<span class="factcheck-badge warning">⚠️ Approximatif</span>

<!-- Statut erreur -->
<span class="factcheck-badge error">✗ Corrigé</span>
```

#### Cartes juridiques

```html
<div class="legal-card success">  <!-- ou warning, danger -->
    <div class="legal-card-status">✅ Compatible</div>
    <h3 class="legal-card-title">Titre</h3>
    <div class="legal-card-content">Contenu</div>
    <div class="legal-card-source">Source</div>
</div>
```

### 3.5 Animations

#### Reveal au scroll

```css
.reveal {
    opacity: 0;
    transform: translateY(24px);
    transition: all 0.6s cubic-bezier(0, 0, 0.2, 1);
}

.reveal.visible {
    opacity: 1;
    transform: translateY(0);
}
```

#### Barres de progression

```css
.cost-item-bar-fill {
    transition: width 1s cubic-bezier(0, 0, 0.2, 1);
}
```

---

## 4. Contenu éditorial

### 4.1 Ton et voix

| Attribut | Description | Exemple |
|----------|-------------|---------|
| **Factuel** | Données sourcées, pas d'affirmations gratuites | "526 507 personnes (INAMI 2023)" |
| **Accessible** | Jargon expliqué, phrases courtes | "Le provisionnement = épargne différée" |
| **Engagé** | Point de vue assumé mais nuancé | "Il existe une solution" (pas "LA solution") |
| **Honnête** | Risques et limites explicités | Section "Alertes critiques" |

### 4.2 Hiérarchie de l'information

```
NIVEAU 1 : Chiffre choc (975 000, 21-24 Mrd€)
    │
    └─→ NIVEAU 2 : Explication courte (1-2 phrases)
            │
            └─→ NIVEAU 3 : Détail (liste, tableau)
                    │
                    └─→ NIVEAU 4 : Source (mono, discret)
```

### 4.3 Formulations clés

| À éviter | Préférer |
|----------|----------|
| "Les chômeurs" | "Les personnes au chômage" |
| "Les invalides" | "Les personnes en incapacité" |
| "LA solution" | "Une solution existe" |
| "C'est gratuit" | "Sans perte de droits" |
| "Révolutionnaire" | "Innovant" |

---

## 5. Données et fact-checking

### 5.1 Sources officielles

#### Statistiques population

| Donnée | Valeur | Source | Date | URL |
|--------|--------|--------|------|-----|
| Incapacité >1 an | 526 507 | INAMI | 2023 | inami.fgov.be |
| Chômeurs indemnisés | 292 790 | ONEM | 2024 | onem.be |
| Bénéficiaires RIS | 158 697 | SPP Int. Sociale | 2023 | mi-is.be |
| Aidants proches reconnus | ~150 000 | INAMI | 2023 | inami.fgov.be |
| Bénévoles | 1 166 000 | FRB | 2019 | kbs-frb.be |

#### Coûts budgétaires

| Poste | Montant | Source | Référence exacte |
|-------|---------|--------|------------------|
| Incapacité de travail | 13-15 Mrd € | Cour des Comptes | 181e Cahier, oct. 2024 |
| Allocations chômage | 6,4-7 Mrd € | Cour des Comptes | Tableau 6, dépenses 2023 |
| RIS/CPAS | ~2-2,5 Mrd € | Estimation | 158 697 × ~1 300€/mois × 12 |

### 5.2 Corrections apportées

| Donnée | Valeur originale | Valeur corrigée | Écart | Justification |
|--------|------------------|-----------------|-------|---------------|
| Chômeurs | ~230 000 | 292 790 | +27% | Chiffre 2024 vs estimation ancienne |
| Coût incapacité | ~8 Mrd € | 13-15 Mrd € | +62% | Cour Comptes vs estimation partielle |
| Total coûts | ~15,5 Mrd € | 21-24 Mrd € | +45% | Somme des postes corrigés |
| Solidaris | 4,2 M | ~3 M | -29% | LinkedIn corporate vs estimation |
| Évolution invalides | +40%/10 ans | +65%/10 ans | +25pts | INAMI série longue |

### 5.3 Données à surveiller

| Donnée | Fréquence mise à jour | Source à consulter |
|--------|----------------------|---------------------|
| Chômeurs indemnisés | Mensuelle | ONEM rapports mensuels |
| Incapacité travail | Annuelle | INAMI rapport annuel |
| RIS/CPAS | Annuelle | SPP bulletin statistique |
| Plafonds volontariat | Annuelle (janvier) | SPF Finances indexation |

---

## 6. Analyse juridique détaillée

### 6.1 Incapacité de travail + volontariat

#### Cadre légal

- **Texte** : Loi du 3 juillet 2005 relative aux droits des volontaires
- **Circulaire INAMI** : 2018/223

#### Conditions

| Condition | Détail |
|-----------|--------|
| Autorisation préalable | Non obligatoire, mais médecin-conseil peut constater |
| Compatibilité médicale | L'activité ne doit pas aggraver l'état de santé |
| Défraiements | Max 36,84€/jour, 1 473,37€/an (2025) |
| Nature activité | Bénévole, non rémunérée, non obligatoire |

#### Risques

| Risque | Probabilité | Impact | Mitigation |
|--------|-------------|--------|------------|
| Perte allocations | Faible | Élevé | Rester dans plafonds défraiement |
| Contrôle médecin-conseil | Moyen | Moyen | Documentation préalable |
| Requalification | Faible | Élevé | Pas de subordination |

### 6.2 Chômage + bénévolat

#### Cadre légal

- **Texte** : AR du 25 novembre 1991, article 45bis
- **Document** : Feuille info ONEM T42

#### Procédure obligatoire

```
1. Remplir formulaire C45B
           │
           ▼
2. Envoyer à l'ONEM (bureau local)
           │
           ▼
3. Attendre 12 jours (accord tacite si pas de réponse)
           │
           ▼
4. Commencer l'activité
```

#### Critères d'évaluation ONEM

| Critère | Acceptable | Problématique |
|---------|------------|---------------|
| Horaires | Occasionnels, flexibles | Fixes, réguliers |
| Encadrement | Coordination légère | Hiérarchie structurée |
| Activité | Différente du métier recherché | Identique au métier |
| Durée | Limitée | Illimitée |

### 6.3 RIS/CPAS + activité

#### Exonérations socioprofessionnelles (2025)

| Type | Montant mensuel | Montant annuel |
|------|-----------------|----------------|
| Reprise travail/formation | 309,48 € | 3 713,76 € |
| Métier en pénurie | 443,52 € | 5 322,24 € |
| Activité artistique | 309,48 € | 3 713,76 € |

#### Calcul impact

```
RIS isolé (2025) : 1 263,17 €/mois

Avec exonération socioprofessionnelle :
- Revenus bruts : 309,48 €
- Exonération : 309,48 € (100%)
- Impact sur RIS : 0 €
- Total perçu : 1 263,17 € + 309,48 € = 1 572,65 €/mois

→ Le contributeur gagne 24% de plus qu'avec le RIS seul
```

### 6.4 Question fiscale (CRITIQUE)

#### Principe du fait générateur

> En droit fiscal belge, un revenu est imposable l'année où le **droit est acquis**, pas l'année où il est **encaissé**.

#### Application au provisionnement ECP

| Scénario | Traitement fiscal probable |
|----------|---------------------------|
| Contribution 2025, versement 2030 | Imposable en 2025 |
| Provisionnement = simple comptabilité | Imposable année contribution |
| Provisionnement = libéralité conditionnelle | Zone grise |

#### Action requise

1. **Demander un ruling** au SPF Finances (Service des Décisions Anticipées)
2. **Questions à poser** :
   - Le provisionnement différé est-il un revenu imposable immédiatement ?
   - Quelle qualification : revenu professionnel, divers, ou exonéré ?
   - Quelle base imposable si le versement n'est jamais effectué ?

### 6.5 Requalification en contrat de travail

#### Critères jurisprudentiels

| Élément | Volontariat | Contrat de travail |
|---------|-------------|-------------------|
| Subordination | Aucune | Oui (lien d'autorité) |
| Horaires | Libres | Imposés |
| Lieu | Choisi | Déterminé |
| Rémunération | Défraiement forfaitaire | Contrepartie du travail |
| Sanctions | Aucune | Possibles |
| Intégration | Externe | Dans l'organisation |

#### Conséquences d'une requalification

**Pour l'ASBL :**
- Rappel de salaire (SMIC minimum)
- Cotisations ONSS rétroactives (±38%)
- Pénalités de retard
- Risque pénal (travail dissimulé)

**Pour le contributeur :**
- Perte allocations rétroactive
- Remboursement indus
- Exclusion temporaire

---

## 7. Partenaires potentiels

### 7.1 Mutuelles

| Organisation | Affiliés | Contact type | Intérêt potentiel |
|--------------|----------|--------------|-------------------|
| Mutualité Chrétienne | 4,6 M | Direction générale | Élevé (mission sociale) |
| Solidaris | ~3 M | Service projets | Élevé (lien FGTB) |
| Mutualités Libres | 2,2 M | Innovation | Moyen |
| Mutualité Neutre | ~0,5 M | Direction | Moyen |

### 7.2 Syndicats

| Organisation | Affiliés | Structure EP | Intérêt potentiel |
|--------------|----------|--------------|-------------------|
| FGTB | 1,52 M | CEPAG | Élevé |
| CSC | ~1,6 M | CIEP/MOC | Élevé |
| CGSLB | ~0,3 M | - | Moyen |

### 7.3 Économie sociale

| Organisation | Description | Rôle potentiel |
|--------------|-------------|----------------|
| SAW-B | Fédération économie sociale | Réseau ASBL porteuses |
| Financité | Finance solidaire | Gestion Fonds |
| CESEP | Formation | Accompagnement contributeurs |
| Les Petits Riens | ASBL insertion | Pilote terrain |

### 7.4 Institutions

| Organisation | Rôle potentiel |
|--------------|----------------|
| Fondation Roi Baudouin | Financement recherche + pilote |
| IWEPS | Évaluation d'impact |
| UCLouvain/ULB | Recherche académique |
| Cabinet Prévost (Wallonie) | Relais politique |

---

## 8. Déploiement

### 8.1 Checklist pré-déploiement

- [ ] Vérifier tous les liens (internes et externes)
- [ ] Tester sur Chrome, Firefox, Safari, Edge
- [ ] Tester sur mobile (iOS Safari, Chrome Android)
- [ ] Valider HTML (W3C Validator)
- [ ] Vérifier contraste accessibilité (WCAG AA)
- [ ] Compresser images (si ajoutées)
- [ ] Minifier CSS/JS (optionnel)
- [ ] Configurer meta OG (Open Graph)
- [ ] Configurer favicon

### 8.2 Configuration DNS

```
# Exemple pour ecp.be
@ IN A 185.199.108.153      # GitHub Pages
@ IN A 185.199.109.153
@ IN A 185.199.110.153
@ IN A 185.199.111.153

www IN CNAME ccplc.github.io.
```

### 8.3 GitHub Pages

```bash
# Dans le repo
git checkout -b gh-pages
cp site/ECP-ULTIMATE.html index.html
git add .
git commit -m "Deploy site"
git push origin gh-pages

# Activer dans Settings > Pages
# Source: gh-pages branch
```

### 8.4 Netlify

```toml
# netlify.toml
[build]
  publish = "site/"
  command = "echo 'No build needed'"

[[redirects]]
  from = "/*"
  to = "/ECP-ULTIMATE.html"
  status = 200
```

---

## 9. Maintenance

### 9.1 Mises à jour planifiées

| Fréquence | Action |
|-----------|--------|
| Mensuelle | Vérifier chiffres ONEM |
| Trimestrielle | Actualiser roadmap |
| Annuelle | Mettre à jour plafonds volontariat |
| Annuelle | Vérifier rapports Cour des Comptes |

### 9.2 Processus de correction

```
1. Identifier l'erreur (source, valeur correcte)
           │
           ▼
2. Documenter dans data/corrections.json
           │
           ▼
3. Mettre à jour le site (HTML)
           │
           ▼
4. Commit avec message "[FIX] Correction donnée X"
           │
           ▼
5. Déployer
```

### 9.3 Suivi des versions

| Version | Date | Changements majeurs |
|---------|------|---------------------|
| 1.0.0 | Jan 2026 | Version initiale |
| - | - | - |

---

## 10. Annexes

### 10.1 Glossaire

| Terme | Définition |
|-------|------------|
| **BIM** | Bénéficiaire de l'Intervention Majorée (statut mutuelle) |
| **C45B** | Formulaire ONEM pour déclarer une activité bénévole |
| **CPAS** | Centre Public d'Action Sociale |
| **ECP** | Économie Contributive Provisionnée |
| **INAMI** | Institut National d'Assurance Maladie-Invalidité |
| **ONEM** | Office National de l'Emploi |
| **Provisionnement** | Mécanisme d'épargne différée de la valorisation |
| **RIS** | Revenu d'Intégration Sociale |
| **Ruling** | Décision anticipée de l'administration fiscale |

### 10.2 Contacts utiles

| Service | Contact |
|---------|---------|
| INAMI Incapacité | inami.fgov.be/fr/professionnels |
| ONEM Questions | onem.be/contact |
| SPF Finances Ruling | ruling.be |
| SPP Intégration Sociale | mi-is.be |

### 10.3 Ressources complémentaires

- [Loi volontariat 2005](https://www.ejustice.just.fgov.be/eli/loi/2005/07/03/2005022674/justel)
- [AR chômage 1991](https://www.ejustice.just.fgov.be/eli/arrete/1991/11/25/1991013073/justel)
- [Loi RIS 2002](https://www.ejustice.just.fgov.be/eli/loi/2002/05/26/2002022559/justel)
- [181e Cahier Cour des Comptes](https://www.courdescomptes.be)

---

<p align="center">
<em>Documentation maintenue par le CCPLC</em><br>
Dernière mise à jour : Janvier 2026
</p>
