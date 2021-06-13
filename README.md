***En cours de construction !!!***

[Cette page](https://vincent.bradier.net/godot/) et [sa source](https://github.com/vcbd/apprendre-godot) sont sous licence [CC by-nc-sa 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). A été rédigée à l’été 2021, version 3.3.2 du Godot Engine — les liens vers la documentation francophone ne référençant que la version *stable* ou *latest* du moteur, ils pourraient dans le futur devenir obsolètes.

Elle a été créée comme point d’entrée, support et guide ultérieur (toutes les sections *Aller + loin*) à un premier atelier création de jeux vidéo au GEM Queer de Lille mais peut sans doute servir à d’autres. Si vous êtes seul·e, comptez bien jusqu’au triple des temps indiqués pour étudier chaque concept.

# Créer des jeux vidéo avec Godot !!!
Le matin ça va vraiment être un cours banal (enfin brutal) mais après jspr réussir à faire plus dans l’interaction et l’échange. Le but l’après-midi de toute façon ce sera vraiment de s’amuser en couvrant le maxxx de sujets pour savoir où se renseigner ensuite

## Concepts essentiels (10-12h)

### Introduction à la programmation (10-11h30)

#### Terminologie (45mn)
Pas encore de code, on reste dans l’abstrait.
* Variable
  * Stocker une valeur en mémoire
  * Y accéder
  * Types : https://fr.wikipedia.org/wiki/Type_(informatique) (*Types prédéfinis*, il en manque beaucoup, quelques exemples de ce qu’on va rencontrer : Quat, Vec, Vec3, Rect… (Oui ok ce sera surtout de la géométrie))
* Fonction : suite d’instructions
  * Une fonction peut faire des choses (bouger un personnage…)
  * Mais aussi retourner une valeur (position d’un personnage…) (-> variable ?)
  * Peut faire les 2 à la fois
  * Arguments (valeur et référence)
* Objet : collection de membres, soit variables (propriétés) et fonctions (méthodes)
  * Segmenter le code
  * Classes et instances, en gros https://fr.wikipedia.org/wiki/Classe_(informatique) (intro)
  * Héritage
  * Singletons
* Contrôle du flux
  * Conditions : évalutation d’une expression.
    * Expression booléenne (if), introduction aux opérateurs de comparaison
    * Opérateurs logiques : ET, OU et NON
    * Souvent un raccourci pour multiples branches sur égalité/identité (switch)
  * Boucles

#### Visual Scripting (20mn)
https://docs.godotengine.org/fr/stable/getting_started/scripting/visual_script/what_is_visual_scripting.html (penser à cliquer "next" en bas après avoir lu, ça continue)

#### GDScript
Très semblable à (basé sur) Python. https://docs.godotengine.org/fr/stable/getting_started/scripting/gdscript/gdscript_advanced.html (marqué "advanced" mais plus simple que l’introduction… vraiment cette doc)

#### Aller + loin
Autres langages utilisables dans Godot. Voir aussi *Utilisation de Godot > Scripts > Aller + loin > GDNative*

##### ECMAScript
https://github.com/GodotExplorer/ECMAScript

##### Rust
https://github.com/godot-rust/godot-rust

### Introduction aux maths qui nous intéressent
(pas + de 30mn et pas besoin de comprendre, c’est juste pour savoir quoi chercher quand ça bug, le moteur fait le plus gros du boulot)  
Tout ce qu’on voit ici c’est vraiment histoire de dire qu’on l’a déjà vu, pour effleurer tout ce qu’on risque d’utiliser plus tard. Si un jour on veut vraiment comprendre (ou pour quand il y aura des bugs…) je mets les liens adéquats. Le wikipedia matheux fait peur (à raison) mais j’essaie de sélectionner les articles permettant une entrée en douceur (comprendre : pas trop infernale) dans ces concepts !  
Vraiment j’insiste mais je vous mets en une demi-heure des trucs qui prennent des années à vraiment comprendre donc vraiment pas de panique encore une fois le moteur fait quasi tout pour nous

#### Dimensions mathématiques (2mn) (c’est rudement précis)
≠ dimensions physiques ! Point, ligne, plan, espace et hyperespace  
Aller + loin (après les vecteurs) : http://www.jybaudot.fr/Vecteursmatrices/dimension.html (surtout la partie *Dimension*)

#### Nombres complexes (3mn)
* Le carré d’un nombre réel est toujours positif
* On *imagine* un nombre tel que i² = -1
* i n’est pas un nombre réel. Il n’appartient pas à l’ensemble mathématique des réels tout comme ce n’est pas un nombre qu’on retrouve dans la nature, à l’état sauvage
* Donc un complexe s’écrit sous la forme a + bi, a étant la partie réelle et b la partie imaginaire
* On remarque que c’est donc un nombre à deux dimensions
* Aller + loin : Coordonnées polaires (et globalement toute représentation de coordonnées n-dimensionnelles dans un espace à n-1 dimensions, utile pour appréhender l’hypersphère des quaternions) (ne prenez pas peur c’est pas indispensable du tout) (vraiment venez quand même) (svp)

#### Vecteurs (10mn)
J’ai menti les vecteurs faut un peu comprendre
* Coordonnées dans un plan : (x, y)
* Normalisation
* Normales https://fr.wikipedia.org/wiki/Normale_(g%C3%A9om%C3%A9trie) (utile en 3D)
* https://fr.wikipedia.org/wiki/Calcul_vectoriel_en_g%C3%A9om%C3%A9trie_euclidienne
  * Produit vectoriel (cross product) https://fr.wikipedia.org/wiki/Produit_vectoriel (notation, définition, propriétés algébriques jusqu’à la première démonstration (exclue))
  * Produit scalaire (dot product) https://fr.wikipedia.org/wiki/Produit_scalaire (ne nous intéressent que les paragraphes *Propriétés géométriques > Projeté* mais la page est intéressante bien que franchement ardue (ça va quoi c’est des vecteurs et les rédacteurs en font des tonnes pour que ce soit plus compliqué) (encore des mascus sûrement))
  * https://kidscancode.org/godot_recipes/math/dot_cross_product/ est en anglais mais guettez les schémas : le cross product permet de savoir si un objet est à gauche ou à droite d’un autre objet orienté et le dot product s’il est devant/derrière.

#### Matrices (5mn)
Honnêtement jsp faire de calcul matriciel, on va juste voir à quoi ressemblent les transformations géométriques en interne. https://fr.wikipedia.org/wiki/Matrice_(math%C3%A9matiques) donne mal à la tête mais j’ai appris plein de trucs ! Et https://fr.wikipedia.org/wiki/Matrice_de_rotation pour les objets Transform (encore une fois si on veut savoir hacker le moteur hein) (mais c’est relativement facile en fait)

#### Quaternions (10mn)
Encore une fois ça me dépasse, on va juste comparer par rapport à des 3-uple d’angles (angles d’Euler).
* https://fr.wikipedia.org/wiki/Quaternion (intro, histoire, représentation matricielle 4×4, applications)
* Interpolation : transitionner d’une rotation spécifique vers une autre
* Aller + loin : https://fr.wikipedia.org/wiki/Quaternions_et_rotation_dans_l%27espace (*Les quaternions en bref* explique bien le concept de quat.)

---

## Utilisation de Godot (13h30-18h30)

### Télécharger Godot (5mn)
https://godotengine.org Avec ou sans mises à jour automatiques ? Version Steam ?

### Interface de Godot (10mn)
https://docs.godotengine.org/fr/stable/getting_started/step_by_step/intro_to_the_editor_interface.html

#### Gestionnaire de projets (5mn)
```
Godot/
-----/v3.2.1/
-----/------/Godot.3.2.1.x86_64 (Binaire Linux)
-----/------/Projet1/
-----/------/-------/src/       (Sources du jeu)
-----/------/-------/build/     (Distribuables)
-----/v3.3.2/
-----/------/Godot.3.3.2.x86_64 (Binaire Linux)
-----/------/Projet2/
-----/------/-------/src/
-----/------/-------/build/
```
* Versions de Godot : perso je range mes projets avec le binaire de Godot par lequel j’ai commencé à les créer (voir ci-dessus). Godot stocke des informations sur les projets hors des sources donc tous les projets sont visibles dans le gestionnaire de projets de chaque version alors pourquoi faire ça ?
	* Ça permet de "mettre à jour" Godot (comprendre télécharger une nouvelle version à côté des précédentes) sans risquer de casser nos projets existants
	* en fonction des notes de mise à jour, on peut continuer un projet sur une version plus récente du moteur (s’il y a de nouvelles fonctionnalités intéressantes bien sûr ! Le mieux est l’ennemi du bien) (!!!!!! Bien vérifier le changelog pour tout *breaking change* !!!!!!) (Les changements de version majeure (comme la future v4), faites-vous une faveur et considérez ça comme impossible de base) :
	  1. Tester le projet sur la nouvelle version, toujours.
	  2. Si tout va bien : fermer le projet puis le **copier** vers la nouvelle version (si vous utilisez un cvs, vous pouvez déplacer mais taguez le changement de version du moteur, avant de le faire) (le but est de pouvoir revenir en arrière si on découvre plus tard un bug bloquant lié au changement de version) (oui ça implique de s’asseoir sur ce qu’on a fait depuis, mais c’est mieux que de s’asseoir sur tout son projet) (pour éviter ce genre de scénario je vous conseille de tester, tester, tester comme préconisé au point précédent)
	  3. Scanner le projet dans son chemin correspondant à la nouvelle version
	  4. ???
	  5. Profit!!
	* On peut vérifier sur quelle version de Godot tourne un projet en un coup d’œil au chemin dans le gestionnaire de projets, et le comparer avec la version lancée en haut à droite
	* Ne jamais modifier un projet avec un éditeur de version antérieure à celui-ci (par exemple : modifier `Godot/v3.3.2/Projet2` avec `Godot.3.2.1.x86_64` c’est caca faut pas faire)
* Rangement des fichiers. https://docs.godotengine.org/fr/stable/getting_started/step_by_step/filesystem.html Paquet des ressources en lecture seule lors de l’exécution.
* Aller + loin : https://docs.godotengine.org/fr/stable/getting_started/workflow/project_setup/project_organization.html

#### Éditeur (5mn)
C’est un peu effrayant au premier abord, on va prendre cinq bonnes minutes pour identifier le plus gros de l’interface.
* Main viewport
  * 2D/3D/Script : choix de la visualisation. Souvent automatique.
  * Menus
  * Aperçu
* Panneau bas
* Docks
  * Repositionnables.
* Menus

### Nœuds et Scènes
https://docs.godotengine.org/fr/stable/getting_started/step_by_step/scenes_and_nodes.html (heu perso je trouve l’intro plus confusionnante qu’autre chose)

#### Nœuds (5mn)
Briques de base de tout logiciel Godot.
* Enfants (pluriel) et parent (singulier)
* Ça fait un arbre avec des branches
* Racine (tout premier nœud)

##### Inspecteur
Propriétés du nœud sélectionné.

##### Signaux & Groupes
Attention ça va être technique :
* Les signaux permettent de… signaler quelque chose
* Les groupes de… grouper des nœuds

Voilà c’était compliqué mais on va y revenir !!

#### Scènes (10mn)
Sauvegarde d’un nœud-racine et ses enfants.
* Une scène = un arbre/branche
* Découper, encore une fois, découper tout ce qu’on fait car :
* Instanciation et héritage
https://docs.godotengine.org/fr/stable/getting_started/step_by_step/instancing.html

### Scripts (1h)
Très important, c’est ce qui définit toute la logique du jeu. On a introduit ce matin des langages certes relativement lents (car interprétés) mais étroitement couplés au moteur et son API, qui permettent de concevoir très rapidement des prototypes.

#### Intégration avec nœuds et scènes

#### Signaux & groupes

#### Sigletons & autoload

#### Aller + loin (en ligne, ou un autre jour ?)

##### Scripts d’éditeur
https://docs.godotengine.org/fr/stable/tutorials/misc/running_code_in_the_editor.html

##### Paralléliser les scripts
https://docs.godotengine.org/fr/stable/tutorials/threads/using_multiple_threads.html

##### GDNative
Permet d’optimiser son code en le compilant mais ⚠ l’optimisation précoce est à éviter. Ça veut dire écrire deux fois sa logique, une fois en interprété pour le prototype et une fois en compilé pour la sortie (bon pas toute sa logique du coup, seulement ce qui ralentit tout)  
https://docs.godotengine.org/fr/stable/tutorials/optimization/cpu_optimization.html#languages  
https://docs.godotengine.org/fr/stable/tutorials/plugins/gdnative/index.html# (je vous conseille C++ mais C est également disponible si besoin)  
Les langages C et C++, installer un compilateur, les pointeurs… sont hors du cadre de ce document. GDNative est typiquement un truc pour lequel je pense qu’on pourrait se revoir.

### Entrées (souris, clavier, manettes…) (1h ?)

#### Mappage des boutons

##### Boutons vs. actions

##### InputMap

#### Les actions dans les scripts

##### La fonction `_input`

##### Le singleton `Input`

---
Jusque là c’était assez abstrait, mais on arrive enfin à la partie où on affiche des trucs ! Et avec tout ce qu’on a vu avant on va pouvoir itérer très rapidement sur un prototype de jeu simple.

### Graphiques !! (1h)
Beaucoup de concepts se recoupent de la 2D à la 3D. Je les ai classés assez arbitrairement.

#### Ressources
* https://opengameart.org

#### GUI
Un genre de 2D en fait.

#### 2D
* Tout est mesuré en pixels

##### Sprites

##### Animation

#### 3D
* Tout est mesuré en mètres

##### Meshes
* Un mesh est une collection de sommets (vertices) reliés entre eux par des bords (edges), reliés entre eux par des faces. Par exemple, un cube peut être décomposé en 8 sommets, 12 bords et 6 faces.
* Une primitive est un mesh "simple", "standard" (cube, sphère, pyramide, cylindre…)
* Un modèle est une collection de meshes.

##### Caméra

##### Shaders (introduction hein)
Encore un autre langage de prog (un GLSL-like). Pas le plus simple en plus. Mais extrêmement puissant. (ALERTE je viens d’apprendre qu’on peut coder visuellement les shaders aussi https://docs.godotengine.org/fr/stable/tutorials/shading/visual_shaders.html ce qui devrait être très très intéressant car pour diverses raisons on doit maintenir une certaine simplicité du flux dans les shaders du coup ça doit rendre assez bien en VS, bref plutôt coolos)
* Code exécuté sur le (en fait les) processeur(s) graphique(s)
* Parallélisation
* On ne peut pas récupérer les résultats de calculs arbitraires depuis les shaders
* Permettent de (re)définir certaines variables spécifiques pour modifier le rendu

Exemple pour du flat shading, aka low-poly "papier" :

```
shader_type spatial;                                       // On travaille en 3D

render_mode blend_mix,cull_disabled,diffuse_burley;        // Modes de rendu, presets de confs courantes

uniform vec4 albedo : hint_color;                          // Propose de choisir la couleur du matériel dans l’inspecteur
	                                                       // (le vec4 est utilisé pour les couleurs et définit rouge, vert, bleu
	                                                       // (couleurs primaires de la lumière) mais aussi alpha (transparence))

void fragment() {                                          // Fonction exécutée pour chaque pixel affichant un fragment
	                                                       // du mesh sur lequel est appliqué ce matériel (on remarque que
	                                                       // le bloc est défini par {} et non plus par l’indentation du code)
	
	vec3 material_color = albedo.rgb;                      // On récupère la couleur depuis la propriété albedo
	                                                       // du matériel (notez le vec3)
	
	ALBEDO = material_color;                               // On attribue au pixel la couleur récupérée ci-dessus
	
	NORMAL = normalize(cross(dFdx(VERTEX), dFdy(VERTEX))); // On redéfinit la normale du pixel de façon à ne
	                                                       // pas adoucir les bords au rendu

}                                                          // On remarque également qu’on s’est permis beaucoup
	                                                       // de calculs qui vont être évalués à CHAQUE pixel
	                                                       // et ce à 60 images par seconde : les GPU sont monstrueux.
```

Pour mieux comprendre cet exemple (mais en anglais désolé) : http://www.aclockworkberry.com/shader-derivative-functions/ (introduit aussi au coût des branches sur le GPU)  
Important. Les shaders font (ou défont) toute l’ambiance d’un jeu. Quasiment. Visuellement quoi.

##### Aller + loin
https://docs.godotengine.org/fr/stable/tutorials/3d/index.html

#### Mixer tout ça

##### Viewports
https://docs.godotengine.org/fr/stable/tutorials/viewports/viewports.html

### Physique (1h)

### Audio (30mn)

#### Ressources
* https://freesound.org

## Et ensuite ? (bonus 10mn)

### Aller + loin (en ligne)
On ne verra pas tout ça sur place (ou pas tout de suite)

#### La doc (RTFM)
Vous l’avez déjà mais : https://docs.godotengine.org/fr/stable/index.html
* Elle est malheureusement loin de la perfection
* Les *tutoriels* approfondissent bien les concepts qu’on a déjà vus
* *Godot API* (tout en bas du menu) n’est pas traduite, fait très peur, est incomplète mais deviendra vite votre référence une fois que vous saurez vous orienter seul·e

#### CVS avec git
* https://github.com/godotengine/godot-git-plugin devrait permettre de commit directement depuis Godot.
* https://github.com/FredrikNoren/ungit (tout OS) permet d’utiliser Git sans trop toucher à la ligne de commande (car je sais, ça fait peur. Mais c’est rudement pratique)
* Voir aussi https://docs.godotengine.org/fr/stable/getting_started/workflow/project_setup/version_control_systems.html
* En vrai encore un truc à voir ensemble plus tard

#### Debug
https://docs.godotengine.org/fr/stable/tutorials/debug/overview_of_debugging_tools.html
* Les jeux lancés depuis l’éditeur sont 4-5× plus lents que des releases

#### Localisation
https://docs.godotengine.org/fr/stable/tutorials/i18n/internationalizing_games.html

#### Exporter son projet
(Vous allez rire mais j’étais tellement dans la conception de jeux vidéo que j’ai failli oublier de caser une rubrique pour obtenir un binaire distribuable. Oupsi !!)
* https://docs.godotengine.org/fr/stable/getting_started/workflow/export/exporting_projects.html
* *Projet > Exporter…*

#### Sauvegardes
* https://docs.godotengine.org/fr/stable/tutorials/io/saving_games.html
* Numérotez des versions de sauvegarde !!!!

#### Clicketiclick
On n’a fait qu’effleurer tous ces bons liens que j’ai rassemblés. Il est temps de les visiter !

#### Considérations légales

##### Licences
https://docs.godotengine.org/fr/stable/tutorials/legal/complying_with_licenses.html

###### En gros

###### CC0, WTFPL, etc.
Licences "domaine public", mais c’est toujours sympa de créditer quand même. Dans le doute, lire la licence (oui…) permet de connaître précisément les conditions de redistribution ou modification.

### On garde contact ?
* Pas très motivant de bosser tout·e seul·e dans son coin.
* svp svp svp

### Maintenant, apprenez !
C’était dense mais c’était que le début. Tous les points *Aller + loin* sont des portes d’entrée vers certains concepts importants ou leur approfondissement. Même une fois que toute cette page sera maîtrisée ce sera que le début. Quand vous distribuerez votre premier jeu, alors là on pourra dire que c’est que le début. Quand vous contribuerez à Godot ce sera que le début. Quand vous créerez vos propres moteurs ce sera encore que le début.

### Maintenant, enseignez !
Oui je vous y autorise. Plus sérieusement on a vu quasi tout ce que moi je sais, ne doutez pas que vous pouvez transmettre ça à votre tour (ayez la confiance d’un mec blanc médiocre) (oui je parle de moi). Y a pas à apprendre un tout petit peu plus avant de le faire, de toute façon ici on croit à l’apprentissage permanent (si ce n’est pas votre cas merci de relire le point précédent). Et puis ça fait réviser ce qu’on sait déjà et des nouveaux trucs c’est vraiment tout bénéf !
