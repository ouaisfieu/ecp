# 🎨 SIGNAL_273 — Thème itch.io

## Paramètres du thème (à entrer dans Edit Theme)

### Couleurs principales

| Paramètre | Valeur | Aperçu |
|-----------|--------|--------|
| **Background** | `#000000` | ⬛ Noir pur |
| **Background 2** | `#0a0a0a` | ⬛ Noir profond |
| **Text color** | `#00ff88` | 🟩 Vert néon |
| **Link color** | `#ff2d2d` | 🟥 Rouge signal |
| **Button color** | `#00ff88` | 🟩 Vert néon |

### Font

**Font family:** `JetBrains Mono` ou `Anonymous Pro` (comme PéTAL)

### Background image (optionnel)

Tu peux utiliser une texture de scanlines ou de matrix code.
Upload une image de 200x200 pixels avec :
- Fond noir
- Lignes vertes très fines (opacity 5-10%)
- Repeat: `repeat`

---

## CSS personnalisé (à coller dans Custom CSS)

```css
/* SIGNAL_273 — Terminal aesthetic */

/* Scanlines overlay */
.wrapper::before {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(0, 255, 136, 0.03) 2px,
    rgba(0, 255, 136, 0.03) 4px
  );
  pointer-events: none;
  z-index: 9999;
}

/* Glowing title */
.game_title {
  text-shadow: 
    0 0 10px rgba(0, 255, 136, 0.5),
    0 0 20px rgba(0, 255, 136, 0.3),
    0 0 30px rgba(0, 255, 136, 0.2) !important;
  letter-spacing: 2px !important;
}

/* Red accent on numbers */
.formatted_description strong {
  color: #ff2d2d !important;
}

/* Terminal-style code blocks */
.formatted_description pre,
.formatted_description code {
  background: #0d1117 !important;
  border: 1px solid #00ff88 !important;
  color: #00ff88 !important;
  font-family: 'JetBrains Mono', 'Anonymous Pro', monospace !important;
}

/* Blockquotes as "transmissions" */
.formatted_description blockquote {
  border-left: 3px solid #ff2d2d !important;
  background: rgba(255, 45, 45, 0.1) !important;
  padding: 15px !important;
  font-style: italic;
}

/* Tables */
.formatted_description table {
  border-color: #00ff88 !important;
}

.formatted_description th {
  background: rgba(0, 255, 136, 0.1) !important;
  color: #00ff88 !important;
}

/* Download button pulse */
.download_btn {
  animation: pulse 2s infinite !important;
}

@keyframes pulse {
  0%, 100% { box-shadow: 0 0 5px rgba(0, 255, 136, 0.5); }
  50% { box-shadow: 0 0 20px rgba(0, 255, 136, 0.8); }
}

/* Links hover effect */
.inner_column a:hover {
  text-shadow: 0 0 10px currentColor;
}

/* Header bar dark */
.game_header_widget {
  background: #000 !important;
}
```

---

## Images à uploader

### 1. Cover image (630×500)
Utilise le prompt AI ou le HTML cover que je t'ai fait.

### 2. Banner image (960×120 ou similaire)
```
Fond noir, texte "SIGNAL_273" en vert néon centré,
scanlines subtiles, style terminal
```

### 3. Screenshot (au moins 1)
Screenshot du jeu avec :
- L'écran de boot
- Le menu principal avec countdown
- Un puzzle en cours

---

## Paramètres itch.io recommandés

| Setting | Value |
|---------|-------|
| **Classification** | Games |
| **Kind of project** | HTML |
| **Release status** | Released |
| **Pricing** | $0 or Name Your Own Price |
| **Genre** | Puzzle, Interactive Fiction |
| **Tags** | `arg`, `alternate-reality-game`, `puzzle`, `investigation`, `political`, `free`, `browser`, `hacker`, `mystery` |
| **Viewport** | 960 × 600 ou Fullscreen |

---

## Fichier à uploader

1. Renomme `SIGNAL_273_ARG.html` → `index.html`
2. Zippe le fichier
3. Upload le .zip
4. Coche "This file will be played in the browser"

---

## Résultat attendu

```
┌─────────────────────────────────────────┐
│ ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ │
│                                         │
│            SIGNAL_273                   │
│     (titre en vert néon qui glow)       │
│                                         │
│  ┌─────────────────────────────────┐   │
│  │     [JOUER DANS LE BROWSER]     │   │
│  └─────────────────────────────────┘   │
│                                         │
│  📡 SIGNAL_273 📡                       │
│                                         │
│  SIGNAL_273 is not a regular game...    │
│  (description en vert sur noir)         │
│                                         │
│  > 273 organizations                    │
│  > €50M+/year                           │
│  > The raid is real                     │
│                                         │
│ ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░ │
└─────────────────────────────────────────┘
```

Le même vibe que PéTAL, mais version **hacker/ARG/conspiracy**. 🔐
