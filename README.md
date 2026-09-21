pour créer des vidéos gratuitement avec l'intelligence artificielle de manière illimitée veuillez lire ce tutoriel. tous les logiciels sont dans le répertoire il y a le fichier index.html qui est un exemple qui marche bien et les autres s'appellent deepseek...

mise à jour importante : dans le répertoire le fichier index est un exemple qui marche bien mais certains des fichiers qui s'appellent deepseek ont la clé API qui est écrite directement dans le code source , c'était une clé API de test , ainsi pour que ça marche vous devez modifier dans le code source la clé API.  Pour les autres fichiers deepseek la clé API est configurable directement dans la page et elle fonctionne pour toutes les autres applications. de plus sur iPhone je n'ai pas testé il paraît que le iPhone télécharge le fichier et l'ouvre avec un éditeur de texte soit parce qu'il renomme le fichier en point txt ou soit parce qu'il ne l'ouvre pas avec le navigateur dans l'idéal le navigateur est chrome.

---

# CinéIA Spectrum — Créez vos vidéos IA avec Agnes AI (100 % gratuit)

## 🌐 Qu'est-ce que ce projet ?

CinéIA Spectrum est un générateur de vidéos par intelligence artificielle entièrement gratuit. Vous fournissez une image, vous sélectionnez un ou plusieurs styles visuels, et l'outil crée automatiquement des vidéos de 5 à 10 secondes en animant votre image dans chaque style choisi.

Le tout fonctionne avec une simple clé API gratuite chez Agnes AI, sans installation, sans carte bancaire, sans inscription complexe. Un seul fichier HTML, un navigateur, et c'est parti.

---

## 1. Comment obtenir une clé API gratuite chez Agnes AI

Agnes AI est une plateforme qui met à disposition des modèles d'intelligence artificielle multimodal (texte, image, vidéo) **gratuitement et sans limite de durée** pour les développeurs.

Voici la procédure exacte :

1. **Rendez-vous sur le site officiel** : `https://agnes-ai.com` (ou `https://agnes-ai.cn` pour la version chinoise).
2. **Créez un compte** avec votre adresse email. L'inscription est gratuite et ne demande aucune information bancaire.
3. **Accédez au tableau de bord** : une fois connecté, cherchez la section « API Keys » ou « Clés API ».
4. **Cliquez sur « Create API Key »** (Créer une clé API). Une clé commençant par `sk-...` sera générée. Copiez-la immédiatement et conservez-la en lieu sûr — elle ne sera plus affichée en entier.
5. **C'est tout !** Vous pouvez maintenant utiliser cette clé dans CinéIA Spectrum ou dans n'importe quelle application compatible avec l'API Agnes AI.

💡 **Astuce** : Si vous perdez votre clé, vous pouvez en générer une nouvelle depuis le tableau de bord. Pour des raisons de sécurité, supprimez l'ancienne immédiatement.

---

## 2. Spécificités de l'API gratuite Agnes AI

### Modèles disponibles gratuitement

| Type de modèle | Nom du modèle | Statut |
|---|---|---|
| **Texte** | `agnes-2.0-flash` | ✅ Gratuit |
| **Image** | `agnes-image-2.1-flash` | ✅ Gratuit |
| **Vidéo** | `agnes-video-v2.0` | ✅ Gratuit ($0/seconde) |

### Limites de débit (RPM = Requêtes Par Minute)

Les utilisateurs gratuits sont soumis à des limitations de débit RPM. Si vous atteignez la limite, il suffit d'attendre un court instant avant de refaire une requête.

Voici les valeurs exactes pour le tier gratuit：

| Type de modèle | RPM autorisé | **RPM effectif (réel)** |
|---|---|---|
| **Texte** | 30 | **20 requêtes/minute** |
| **Image (1K)** | 30 | **20 images/minute** |
| **Image (2K)** | 20 | **10 images/minute** |
| **Vidéo** | 2 | **1 vidéo/minute** |

⚠️ **Important** : La vidéo est limitée à **1 génération par minute**. CinéIA Spectrum gère automatiquement cette contrainte en attendant 60 secondes entre chaque clip.

### Endpoints API utilisés

| Action | Méthode | Endpoint |
|---|---|---|
| Créer une tâche vidéo | `POST` | `https://apihub.agnes-ai.com/v1/videos` |
| Récupérer le résultat | `GET` | `https://apihub.agnes-ai.com/agnesapi?video_id=<ID>` |
| Chat texte (optionnel) | `POST` | `https://apihub.agnes-ai.com/v1/chat/completions` |

### Paramètres vidéo

- **`num_frames`** : nombre total d'images. Doit être ≤ 441 et suivre la règle **8n + 1** (ex: 121, 153, 241, 441).
- **`frame_rate`** : de 1 à 60 fps (24 fps par défaut).
- **Durée** = `num_frames / frame_rate`. Exemple : 153 frames ÷ 24 fps = **6,4 secondes**.

### Fonctionnalités du modèle vidéo

Le modèle `agnes-video-v2.0` supporte : le text-to-video, l'image-to-video (une image en entrée → vidéo animée), la keyframe animation (plusieurs images clés → transitions fluides), le motion control (contrôle des mouvements du sujet et de la caméra), et la cohérence visuelle sur plusieurs frames.

---

## 3. Comment utiliser CinéIA Spectrum

### Étape 1 — Téléchargez le fichier

Récupérez le fichier `index.html` depuis ce dépôt GitHub et enregistrez-le sur votre téléphone ou votre ordinateur.

### Étape 2 — Ouvrez le fichier

Double-cliquez sur `index.html` ou ouvrez-le avec n'importe quel navigateur moderne (Chrome, Safari, Firefox, Edge). Aucune installation serveur n'est nécessaire — tout fonctionne directement dans le navigateur.

### Étape 3 — Ajoutez votre clé API

1. Cliquez sur le bouton **⚙️ Paramètres API** en haut de la page.
2. Collez votre clé API Agnes AI (celle qui commence par `sk-...`).
3. Cliquez sur **Sauvegarder**. La clé est stockée localement dans votre navigateur et n'est jamais envoyée ailleurs qu'à l'API Agnes AI.

### Étape 4 — Générez vos vidéos

1. **Uploadez une image** : cliquez sur la zone d'upload et sélectionnez une photo depuis votre téléphone. Cette image servira de première frame pour toutes les vidéos générées.
2. **Cochez les styles** qui vous intéressent parmi les 30 proposés (Anime, Ghibli, Wes Anderson, Van Gogh, Cyberpunk, Pixel Art, Film Noir, etc.).
3. **Choisissez la durée** : 5,0 s, 6,4 s (recommandé), ou 10,0 s.
4. **Choisissez le mouvement** : Excentrique, Hallucinant, Spectaculaire, Kung-fu Shaolin, Hip-hop, Robot, etc.
5. Cliquez sur **🎬 Générer les vidéos**.

Chaque vidéo est générée **une par une**, avec une pause automatique de 60 secondes entre chaque (pour respecter la limite de 1 vidéo/minute). Les vidéos apparaissent au fur et à mesure dans la galerie en bas de la page.

### Estimation du temps

Pour 5 styles sélectionnés avec des vidéos de 6,4 secondes, comptez environ **8 à 12 minutes** au total. Le système affiche un compte à rebours en temps réel pour chaque étape.

---

## 4. Prompt de modification du script

Vous souhaitez personnaliser CinéIA Spectrum ? Copiez ce prompt et collez-le dans n'importe quelle intelligence artificielle conversationnelle (ChatGPT, Claude, DeepSeek, etc.) en lui fournissant votre fichier `index.html`.

---

**PROMPT À COPIER :**

```
Je te fournis le code source complet d'une application web HTML/CSS/JavaScript 
appelée CinéIA Spectrum. Cette application génère des vidéos par intelligence 
artificielle à partir d'une image, en utilisant l'API gratuite Agnes AI 
(https://apihub.agnes-ai.com/v1).

Voici le code actuel :

[COLLEZ ICI LE CONTENU COMPLET DE VOTRE FICHIER index.html]

Je souhaite modifier cette application. Voici ce que je veux changer :

[EXPLIQUEZ ICI VOS MODIFICATIONS, par exemple :]
- Ajouter de nouveaux styles visuels (précisez lesquels et donnez leurs mots-clés anglais)
- Modifier les couleurs de l'interface
- Changer les durées proposées dans le menu déroulant
- Ajouter un système de sauvegarde des vidéos dans l'historique du navigateur
- Ajouter un bouton pour télécharger chaque vidéo
- Modifier les prompts aléatoires (donnez vos propres actions, éclairages, mouvements de caméra)
- Ajouter un champ de texte pour que l'utilisateur décrive lui-même sa vidéo
- Traduire l'interface dans une autre langue
- Créer une file d'attente visible avec le temps restant estimé
- Ajouter un mode "preview" qui génère une seule image fixe pour tester le style avant la vidéo

Contraintes obligatoires :
- Le fichier doit rester un seul fichier HTML autonome (pas de fichiers séparés)
- L'API utilisée reste celle d'Agnes AI avec la clé stockée dans localStorage
- Le modèle vidéo est "agnes-video-v2.0"
- Les appels vidéo doivent respecter la limite de 1 RPM (pause de 60 secondes entre chaque)
- Les num_frames doivent suivre la règle 8n+1 et être ≤ 441
- Le frame_rate est 24 par défaut
- L'audio doit être généré avec uniquement des bruitages et ambiances, pas de musique
- Les vidéos doivent être au format 9:16 vertical

Génère le fichier index.html complet et fonctionnel avec mes modifications.
```

---

## 📌 Notes complémentaires

- **Confidentialité** : Votre clé API reste stockée dans le `localStorage` de votre navigateur. Elle n'est jamais transmise à un serveur tiers autre que l'API Agnes AI.
- **Coût** : Le modèle `agnes-video-v2.0` est facturé **$0/seconde** pour les utilisateurs gratuits. Aucun paiement n'est requis.
- **Support** : En cas de question ou de problème d'intégration, vous pouvez contacter Agnes AI à l'adresse `support@agnes-ai.com`.
- **Documentation officielle** : `https://wiki.agnes-ai.com` pour les guides d'intégration complets.

---

Avec ce README, tes abonnés peuvent obtenir une clé API gratuite, télécharger le fichier, lancer leurs premières vidéos et même modifier le script pour l'adapter à leurs besoins. 🎬
