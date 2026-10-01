# Ciel des proches — Qui a le ciel le plus clément ?

Application d'astrologie mono-fichier (HTML/CSS/JS, sans backend) qui calcule le thème natal de chaque proche et sa « météo astrale » du jour, à partir de la date, de l'heure et du lieu de naissance. Les positions des planètes sont calculées directement dans le navigateur, sans bibliothèque ni clé API.

Site : https://fef73.github.io/meteo-astro/ — accessible aussi depuis le lanceur [comparateur-meteo.fr](https://comparateur-meteo.fr/).

## Bulletin cosmique

- Signe traversé par le Soleil et par la Lune.
- **Phase lunaire** avec son icône et le pourcentage éclairé.
- **Aspect le plus serré** du jour entre deux planètes (conjonction, sextile, carré, trigone, opposition), avec son orbe.
- **Planètes rétrogrades** du jour.

## Cartes par personne

- **Note globale sur 100** et étoiles pour ❤️ Amour, 💼 Travail et ⚡ Énergie.
- Notes calculées d'après les **transits** : aspects entre les planètes du jour (Soleil → Saturne) et celles du thème natal, pondérés par leur nature (harmonieux ou tendu), leur orbe et la planète en jeu, plus l'accord entre la Lune du jour et la Lune natale.
- **Deux phrases explicatives** tirées des aspects les plus marquants (« ☉ Soleil en trigone avec votre Lune : bon moment pour… »).
- Signes du Soleil, de la Lune et de l'Ascendant de la personne.
- Classement 🥇🥈🥉 quand plusieurs thèmes sont enregistrés.
- 4 périodes : aujourd'hui, demain, après-demain, 7 jours. Sur 7 jours, les notes sont des moyennes, avec le **meilleur jour** et le **plus délicat**.

## 🏆 Palmarès

- Tous les thèmes classés par note, avec une barre à la couleur de chaque carte.
- **Champions par domaine** : meilleure note en amour, travail et énergie.
- Suit la période choisie ; une ligne touchée ouvre le thème natal correspondant.
- Affiché à partir de 2 thèmes.

## 🪐 Thème natal

- **Roue du thème** en SVG : signes colorés par élément (feu, terre, air, eau), 12 maisons, Ascendant (AS), Milieu du Ciel (MC) et aspects entre planètes (vert harmonieux, rouge tendu).
- **Tableau des positions** du Soleil à Neptune : signe, degré, maison et rétrogradation (℞).
- **Interprétation** : Soleil, Lune, Ascendant, planètes personnelles et sociales (Mercure → Saturne) avec leur maison, et élément dominant.
- **Heure inconnue** acceptée : l'Ascendant, le Milieu du Ciel et les maisons sont alors masqués, la Lune est calculée à midi.
- **Info-bulles** au survol (ou au toucher sur mobile) : planètes, signes, maisons, aspects, AS, MC, notes et étoiles.

## Ajout d'un thème

- Formulaire **＋ Ajouter un thème** : prénom, date et heure de naissance, lieu.
- **Saisie au clavier** (pratique sur Android) : `14071985` devient `14/07/1985`, `0830` devient `08:30` ; `8h30`, `14.07.1985` sont aussi acceptés. Dates et heures impossibles refusées avec un message clair.
- Lieu cherché par le [géocodage Open-Meteo](https://open-meteo.com/en/docs/geocoding-api) (gratuit, sans clé), qui fournit aussi le **fuseau horaire IANA**.
- L'heure locale est convertie en heure universelle avec le fuseau du lieu, **heure d'été historique comprise** (`Intl.DateTimeFormat`).
- Suppression d'un thème avec la croix ✕ de sa carte.
- Une carte « Exemple » s'affiche tant qu'aucun thème n'est ajouté.

## Calculs astronomiques

- Positions du Soleil, de la Lune et des planètes jusqu'à Neptune à partir des **éléments orbitaux de Paul Schlyter** (équation de Kepler, perturbations principales de la Lune, de Jupiter, de Saturne et d'Uranus), longitudes écliptiques géocentriques.
- Écart inférieur à **0,05°** avec la bibliothèque de référence `astronomy-engine`, vérifié de 1925 à 2060.
- **Ascendant et Milieu du Ciel** à partir du temps sidéral local et de la latitude.
- **Maisons égales** (12 parts de 30° depuis l'Ascendant).
- Rétrogradation détectée en comparant la position à 24 h d'intervalle.

## 📖 Comprendre un thème

Panneau repliable qui explique le rôle des planètes (*quoi*), des signes (*comment*) et des maisons (*où*), d'où viennent les maisons, les 12 domaines et le choix des maisons égales.

## Confort d'usage

- Interface bilingue **FR/EN** (préférence mémorisée, langue du navigateur au premier passage), y compris les textes d'interprétation et les dates.
- Thèmes enregistrés **uniquement dans le navigateur** (`localStorage`), jamais envoyés à un serveur.
- Bouton 📤 Partager (partage natif sur mobile, sinon copie du lien).
- Le fonctionnement du site est aussi résumé dans un panneau repliable « ✨ Fonctionnalités du site » juste avant le pied de page.
- Design commun aux autres sites de fef73 : fond nuit, polices Fraunces, Space Grotesk et IBM Plex Mono.

## Avertissement

Contenu à visée ludique : l'astrologie n'a pas de valeur prédictive démontrée.

## Fichiers

| Fichier | Rôle |
|---|---|
| `index.html` | Le site complet (HTML, CSS et JavaScript) |
| `README.md` | Ce fichier |

---

Créé par fef73 avec [Claude](https://claude.ai).
