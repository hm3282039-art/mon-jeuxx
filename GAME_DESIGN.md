# 🎮 Légendes de la Tour Infinie — Game Design Document (accord de principe)

**Projet :** Idle RPG en 2D / 2.5D, style *Mobile Legends: Adventure* / *Epic Seven* (combat automatique, héros à collectionner, ultimes cinématiques, progression hors-ligne).
**Statut :** Accord de principe — aucun code de mécanique n'est encore écrit.
**Branche :** `arena/1347e60d-mon-jeuxx`
**Date :** 2026-10-23

---

## 1. Ce qu'on a convenu (accord)

| Point | Décision |
|-------|----------|
| **Genre** | Idle RPG : équipe de héros qui se battent automatiquement ; le joueur choisit ses héros, leur équipement et le moment de lancer les ultimes. |
| **Références** | *Mobile Legends: Adventure*, *Epic Seven* (style visuel, cinématiques d'ultime, goutte de collection de héros). |
| **Pas de code pour l'instant** | On fige le Game Design Document (ce fichier) avant d'écrire la moindre mécanique. |
| **Graphismes** | Pas "juste une image". Vrais personnages : illustrations complètes + squelette 2D d'animation (os : bassin, buste, tête, bras, arme, jambes, cape, cheveux) style Spine. Vraies cinématiques (cutscenes) pour les ultimes et les intros de boss — on travaillera ça après le GDD. |
| **Pages de test** | Avant d'intégrer un personnage ou une mécanique dans le jeu principal, on crée une **page de test isolée** (ex. : `test-perso.html` ou dossier `/tests/`) avec :<br>• l'attaque du perso (3 temps : élan, frappe, retour)<br>• son ultime (cinématique + effet)<br>• ses statistiques et son comportement de combat<br>On valide la page de test, puis on intègre au jeu principal. |
| **Stack technique** | Déjà en place dans le dépôt : **PixiJS v8 + TypeScript + Vite**. Build mono-fichier possible (`vite-plugin-singlefile`) pour distribuer un `JOUER.html` hors-ligne. |
| **Langue** | Français (interface et documentation). |

---

## 2. Ce qui existe déjà dans le dépôt (base à conserver)

- **Héros (8) :** Kael, Lyra, Morwen, Seren, Frère Aldric, Ashka, Nyx, Thorne. Chacun a déjà : illustration, portrait, squelette 2D, 3 capacités (attaque, compétence auto, ultime).
- **Hub ville 2.5D :** ville de Cendrebourg avec plusieurs profondeurs de défilement, bâtiments cliquables (Portail de Campagne, Taverne, Autel d'Invocation, Forge, Sanctuaire, Tour de l'Infini), PNJ cliquables, ambiance sonore générée par le code.
- **Combat :** automatique à la MLA, arrêt sur image + séquence d'ultime, mode AUTO, vitesse ×1 / ×2, pause, barre de boss, minuteur, 1–3 étoiles, MVP, tableau des dégâts.
- **Campagne :** Chapitre 1, niveau 1-1 "La Route des Pendus" (goules, squelettes archers, boss Gardien d'Os).
- **Systèmes :** Autel d'invocation, sauvegarde auto navigateur, or/gemmes/XP, énergie, écran des héros (Sanctuaire).
- **Assets :** `src/assets/` (webp/ogg déjà optimisés) + `art-sources/` (PNG sources) + `sound-design/`.

---

## 3. Règles de travail (méthode)

1. **Accord d'abord, code ensuite** : toute nouvelle mécanique ou nouveau personnage fait l'objet d'un accord écrit ici ou dans une section dédiée avant d'être codé.
2. **Une page de test par personnage / par mécanique** : pas d'intégration directe dans le jeu principal sans passage par une page de test isolée qui prouve que l'attaque et l'ultime fonctionnent et sont visuellement validés.
3. **Graphismes avant intégration** : on ne code pas un perso avec un rectangle blanc. On prépare d'abord son illustration et son squelette 2D, même simplifiés, pour la page de test.
4. **Cinématiques en phase 2** : les vraies cinématiques d'ultime et d'intro boss sont notées ici comme à faire, mais ne bloquent pas le premier prototype jouable.

---

## 4. Feuille de route immédiate (prochaines étapes)

1. ✅ Valider ce Game Design Document avec toi.
2. Choisir le **premier héros à prototyper** (ou créer un nouveau héros de test).
3. Créer sa **page de test isolée** : attaque (3 temps) + ultime cinématique + affichage des stats.
4. Valider la page de test avec toi.
5. Intégrer le héros dans le jeu principal (hub + combat + autel).
6. Passer au héros suivant / à la mécanique suivante (répéter).

---

## 5. Notes / questions ouvertes (à remplir avec toi)

- [ ] Nom définitif du projet (actuel : Légendes de la Tour Infinie)
- [ ] Premier héros de test : lequel ? (un des 8 existants ou un nouveau)
- [ ] Style des cinématiques d'ultime (arrêt sur image, zoom, écran secoué, cut-in ?)
- [ ] Plateforme cible : navigateur PC en priorité, mobile ensuite ?
- [ ] Modèle économique : gratuit, pub, achats in-app ? (à décider plus tard)

---

*Ce document est le contrat de travail entre nous. Il évolue seulement d'un commun accord.*
