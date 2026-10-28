# Text Scrambler — Scrambled Text / Texte Brouillé

🌐 **Try it online / Essayer en ligne :** https://botelectro9.github.io/Text-Scrambler/

[English](#english) · [Français](#français)

---

## Download / Télécharger

**Repository / Dépôt :** https://github.com/botelectro9/Text-Scrambler

| File / Fichier | Language / Langue | Direct link / Lien direct |
|---|---|---|
| `text-scrambler-en.html` | English | [Download](https://github.com/botelectro9/Text-Scrambler/raw/origin/text-scrambler-en.html) |
| `texte-brouille-fr.html` | Français | [Télécharger](https://github.com/botelectro9/Text-Scrambler/raw/origin/texte-brouille-fr.html) |

> 🇬🇧 If the link opens the file as text in your browser, right-click it and choose **Save link as…** (make sure the name ends with `.html`).
> 🇫🇷 Si le lien affiche le fichier comme du texte dans votre navigateur, faites un clic droit dessus et choisissez **Enregistrer le lien sous…** (le nom doit se terminer par `.html`).

### 🇬🇧 How to get the files on your computer

**Option 1 – Download everything as a ZIP (easiest)**

1. Open https://github.com/botelectro9/Text-Scrambler
2. Click the green **Code** button, then **Download ZIP**.
3. Unzip the archive.
4. Double-click `text-scrambler-en.html` (or `texte-brouille-fr.html`) to open it in your browser.

**Option 2 – Download a single file**

1. In the repository, click the file name (for example `text-scrambler-en.html`).
2. Click the **Download raw file** button (down-arrow icon, top right of the file view).
3. Check that the saved file ends with **`.html`**. Some browsers add `.txt` (for example `text-scrambler-en.html.txt`) or save it without an extension. If so, rename it so it ends with `.html`. On Windows, turn on **View → File name extensions** in File Explorer to see the real extension; on macOS, use **Get Info → Name & Extension**.
4. Open the file in your browser.

> Don't use "Save page as" on the GitHub file view: it saves GitHub's page, not the tool.

**Option 3 – With Git**

```bash
git clone https://github.com/botelectro9/Text-Scrambler.git
cd Text-Scrambler
```

Then open one of the `.html` files in your browser.

### 🇫🇷 Comment récupérer les fichiers sur votre ordinateur

**Option 1 – Tout télécharger en ZIP (le plus simple)**

1. Ouvrez https://github.com/botelectro9/Text-Scrambler
2. Cliquez sur le bouton vert **Code**, puis sur **Download ZIP**.
3. Décompressez l'archive.
4. Double-cliquez sur `texte-brouille-fr.html` (ou `text-scrambler-en.html`) pour l'ouvrir dans votre navigateur.

**Option 2 – Télécharger un seul fichier**

1. Dans le dépôt, cliquez sur le nom du fichier (par exemple `texte-brouille-fr.html`).
2. Cliquez sur le bouton **Download raw file** (icône flèche vers le bas, en haut à droite de l'aperçu du fichier).
3. Vérifiez que le fichier enregistré se termine bien par **`.html`**. Certains navigateurs ajoutent `.txt` (par exemple `texte-brouille-fr.html.txt`) ou l'enregistrent sans extension. Dans ce cas, renommez-le pour qu'il se termine par `.html`. Sous Windows, activez **Affichage → Extensions de noms de fichiers** dans l'Explorateur pour voir la vraie extension ; sous macOS, utilisez **Lire les informations → Nom et extension**.
4. Ouvrez le fichier dans votre navigateur.

> N'utilisez pas « Enregistrer la page sous » sur l'aperçu GitHub : cela enregistre la page de GitHub, pas l'outil.

**Option 3 – Avec Git**

```bash
git clone https://github.com/botelectro9/Text-Scrambler.git
cd Text-Scrambler
```

Ouvrez ensuite l'un des fichiers `.html` dans votre navigateur.

---

## English

**Scrambled Text** is a single-file HTML/JavaScript page that turns a piece of text into an image. Letters are distorted and the image is covered with noise, decoy characters, strike-through lines and a watermark, so a human can still read it while automatic text recognition (OCR) has a much harder time.

### Features

- Each character gets its own font, size, rotation, skew and color.
- A wave distortion is applied to the whole image.
- Faint decoy letters are scattered in the background.
- Curved lines cross the text, and small arcs are drawn over some letters.
- A repeated diagonal watermark with customizable text.
- Pixel noise and colored speckles.
- **Another variant** button to get a different random layout of the same text.
- Export as PNG (download or copy to clipboard).
- Light and dark theme, works on desktop and mobile.

### Installation

No installation, build step or server needed. Everything runs in the browser.

1. Download `text-scrambler-en.html` (see [Download](#download--télécharger)).
2. Open it in a modern browser (Chrome, Firefox, Safari, Edge).

You can also put the file on any static web host (GitHub Pages, Netlify, your own server).

### Usage

1. Type or paste your text in the **Your text** field. Line breaks are kept; long lines wrap automatically.
2. Adjust the settings:

   | Control | Range | Effect |
   |---|---|---|
   | Distortion | 0–10 | Rotation, skew, size variation, baseline jitter and wave strength |
   | Noise | 0–10 | Number of crossing lines, arcs, pixel noise and speckles |
   | Decoys | 0–10 | Density of decoy letters in the background |
   | Size | 28–72 px | Base font size |
   | Watermark | text | Watermark text; leave empty to disable |

3. Click **Generate image**. Moving a slider regenerates the image immediately.
4. Click **Another variant** for a new random layout.
5. Save the result with **Download PNG** (saved as `scrambled-text.png`) or **Copy image**. If your browser blocks these, right-click or long-press the image and choose "Save image".

### Recommended settings

- **Default (5 / 5 / 4)**: good balance between readability and protection.
- **Stronger (7–8 / 6 / 7)**: harder for OCR. Check that the text is still easy for you to read.
- Shorter texts and larger sizes stay more readable when distortion is high.

### Output

- Width: 1080 px (suited to social networks).
- Height: adapts to the text length (minimum 400 px).
- Format: PNG.

### Limitations

- This makes classic OCR much less reliable, but recent AI vision models can often read fairly distorted text. There is no guarantee the content will go undetected.
- Platforms decide on visibility using many other signals (reports, account behavior, engagement, captions, hashtags). An image alone does not prevent a shadowban.
- Heavily distorted images are harder to read for people with visual impairments and are invisible to screen readers. Consider adding a description when the context allows it.
- Fonts used (Georgia, Courier New, Verdana, etc.) are system fonts; the rendering may vary slightly between operating systems.

### How it works

The page draws on an HTML `<canvas>`:

1. A tinted background with random color gradients.
2. Decoy characters at low opacity.
3. The text, character by character, with random transforms.
4. A sine-wave pixel displacement over the whole image.
5. Crossing Bézier curves and arcs over glyphs.
6. A rotated, repeated watermark.
7. Per-pixel noise and speckles.

The result is converted to a PNG with `canvas.toDataURL()`. A seeded pseudo-random generator (mulberry32) drives all the randomness.

### Customization

Inside the `<script>` block you can edit:

- `FONTS`: the list of fonts picked for each character.
- `DECOYS`: the characters used as background decoys.
- `W`: the output image width (default `1080`).

### License

See the [LICENSE](LICENSE) file.

---

## Français

**Texte Brouillé** est une page HTML/JavaScript en un seul fichier qui transforme un texte en image. Les lettres sont déformées et l'image est couverte de bruit, de lettres leurres, de traits qui barrent le texte et d'un filigrane. Un humain peut la lire, alors que la reconnaissance automatique de texte (OCR) a beaucoup plus de mal.

### Fonctionnalités

- Chaque caractère a sa propre police, taille, rotation, inclinaison et couleur.
- Une ondulation est appliquée à toute l'image.
- Des lettres leurres discrètes sont dispersées en arrière-plan.
- Des courbes traversent le texte et de petits arcs passent sur certaines lettres.
- Un filigrane diagonal répété, au texte personnalisable.
- Du bruit de pixels et des points colorés.
- Bouton « Autre variante » pour obtenir une autre disposition aléatoire du même texte.
- Export en PNG (téléchargement ou copie dans le presse-papiers).
- Thème clair et sombre, fonctionne sur ordinateur et mobile.

### Installation

Aucune installation, compilation ni serveur nécessaire. Tout fonctionne dans le navigateur.

1. Téléchargez `texte-brouille-fr.html` (voir [Télécharger](#download--télécharger)).
2. Ouvrez-le dans un navigateur récent (Chrome, Firefox, Safari, Edge).

Vous pouvez aussi déposer le fichier sur n'importe quel hébergement statique (GitHub Pages, Netlify, votre propre serveur).

### Utilisation

1. Tapez ou collez votre texte dans le champ **Votre texte**. Les retours à la ligne sont conservés ; les lignes longues passent à la ligne automatiquement.
2. Ajustez les réglages :

   | Réglage | Plage | Effet |
   |---|---|---|
   | Déformation | 0–10 | Rotation, inclinaison, variation de taille, décalage vertical et force de l'ondulation |
   | Bruit | 0–10 | Nombre de traits, d'arcs, intensité du bruit de pixels et des points |
   | Leurres | 0–10 | Densité des lettres leurres en arrière-plan |
   | Taille | 28–72 px | Taille de police de base |
   | Filigrane | texte | Texte du filigrane ; laissez vide pour le désactiver |

3. Cliquez sur **Générer l'image**. Déplacer un curseur régénère l'image immédiatement.
4. Cliquez sur **Autre variante** pour une nouvelle disposition aléatoire.
5. Enregistrez le résultat avec **Télécharger PNG** (fichier `texte-brouille.png`) ou **Copier l'image**. Si votre navigateur les bloque, faites un clic droit ou un appui long sur l'image puis « Enregistrer l'image ».

### Réglages conseillés

- **Par défaut (5 / 5 / 4)** : bon équilibre entre lisibilité et protection.
- **Renforcé (7–8 / 6 / 7)** : plus difficile pour un OCR. Vérifiez que le texte reste facile à lire pour vous.
- Les textes courts et les grandes tailles restent plus lisibles quand la déformation est forte.

### Image produite

- Largeur : 1080 px (adaptée aux réseaux sociaux).
- Hauteur : s'adapte à la longueur du texte (minimum 400 px).
- Format : PNG.

### Limites

- L'outil rend les OCR classiques beaucoup moins fiables, mais les modèles d'IA de vision récents lisent souvent du texte assez déformé. Rien ne garantit que le contenu passera inaperçu.
- Les plateformes décident de la visibilité à partir de nombreux autres signaux (signalements, comportement du compte, interactions, légendes, hashtags). Une image seule n'empêche pas un shadowban.
- Les images très déformées sont plus difficiles à lire pour les personnes malvoyantes et invisibles pour les lecteurs d'écran. Pensez à ajouter une description quand le contexte le permet.
- Les polices utilisées (Georgia, Courier New, Verdana, etc.) sont des polices système ; le rendu peut varier légèrement d'un système à l'autre.

### Fonctionnement

La page dessine sur un `<canvas>` HTML :

1. Un fond teinté avec des dégradés de couleur aléatoires.
2. Des caractères leurres à faible opacité.
3. Le texte, caractère par caractère, avec des transformations aléatoires.
4. Un déplacement des pixels en sinusoïde sur toute l'image.
5. Des courbes de Bézier et des arcs sur les lettres.
6. Un filigrane incliné et répété.
7. Du bruit pixel par pixel et des points.

Le résultat est converti en PNG avec `canvas.toDataURL()`. Un générateur pseudo-aléatoire à graine (mulberry32) pilote tout l'aléatoire.

### Personnalisation

Dans le bloc `<script>`, vous pouvez modifier :

- `FONTS` : la liste des polices tirées pour chaque caractère.
- `DECOYS` : les caractères utilisés comme leurres.
- `W` : la largeur de l'image produite (par défaut `1080`).

### Licence

Voir le fichier [LICENSE](LICENSE).
