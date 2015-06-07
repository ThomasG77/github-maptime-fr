# Workshop D3

par <a href="https://twitter.com/ThomasG77">@ThomasG77</a>, WebGeoDataVore

!SLIDE shout

# Workshop D3

## par <a href="https://twitter.com/ThomasG77">@ThomasG77</a>

!SLIDE

* D3: possibilités de représentations et écosystème

* Contextualisation: pourquoi D3? La visualisation de données

* Quel(s) intérêt(s) pour la cartographie ?

* Rappels pratiques

* Travaux pratiques avec mise en ligne de votre démo

!SLIDE

# De nombreux exemples

* [Exemples officiels](https://github.com/mbostock/d3/wiki/Gallery)
* [Gallerie de Christophe Viau](http://christopheviau.com/d3list/gallery.html)

!SLIDE

# Une parenté: [Protovis](https://mbostock.github.io/protovis/)

<img alt="" align="center" src="images/website-protovis.png">

!SLIDE

# Un écosystème effervescent

* Natif
* Surcouches
* Surcouches cartographiques
* Services et autres programmes autour

!SLIDE quieter
<br>
# Surcouches pour des besoins classiques (sans cartographie)

!SLIDE

* http://nvd3.org

<img alt="" align="center" src="images/website-nvd3.png">

!SLIDE

* http://dimplejs.org

<img alt="" align="center" src="images/website-dimple.png">

!SLIDE

* http://c3js.org

<img alt="" align="center" src="images/website-c3js.png">

!SLIDE

* https://tenxer.github.io/xcharts/

<img alt="" align="center" src="images/website-xcharts.png">

!SLIDE quieter
<br>
# Surcouches cartographiques

!SLIDE

# Choroplèthes et points proportionnels, https://datamaps.github.io

<img alt="" align="center" src="images/website-datamaps.png">

!SLIDE

# Visualisation avec fond de plan et plus, https://github.com/emeeks/d3-carto-map

<img alt="" align="center" src="images/website-d3cartomap.png">

!SLIDE

# Globe 3D, http://planetaryjs.com

<img alt="" align="center" src="images/website-planetaryjs.png">

!SLIDE

# Services et autres applications utilisant D3

Pour faire une première visualisation en ligne

* http://datamatic.io
* http://app.raw.densitydesign.org

En passant depuis un autre language de programmation

* https://github.com/areski/python-nvd3

!SLIDE
<br>
# Contexte de D3: OpenData et Visualisation de données

Deux phénomènes liés à un changement de vision du rapport au citoyen

Quelques raccourcis explicatifs sur ces sujets

!SLIDE
<br>
# Principes de l'OpenData:

* Données déjà payées dans le cadre du service public donc doivent être disponibles
* Attente de transparence de la part des citoyens
* Création de richesse potentielle mais comment valoriser?
* OpenData et DataDéluge: trop de données = perte de sens ou impossible à extraire
* Visualisation de données vue comme un moyen de permettre la valorisation

!SLIDE
<br>
# Plusieurs aspects de la visualisation de données:

* Acquérir
* Analyser/Nettoyer
* Valoriser

!SLIDE
<br>
# D3 intervient en phase 2 et 3:

* pour analyser la donnée (distribution, anomalies,...)
* pour valoriser la donnée: "bon" diagramme pour répondre à une question ou s'interroger sur une donnée

!SLIDE

# Quelques exemples de classification

* http://www.datavizcatalogue.com
* http://img.labnol.org/di/data-chart-type.png
* http://www.visual-literacy.org/periodic_table/periodic_table.html
* http://www.los-list.com/blog/wp-content/uploads/2010/03/VisualMiscellaneumTypesofInformationL.gif

!SLIDE

# Intérêts dans un contexte cartographique

Plusieurs visions possibles:

* remplacer des outils comme Leaflet, OpenLayers
* un seul outil "pour les gouverner tous"
* complément cartographique ou non cartographique

!SLIDE
<br>
# Commentaires

* Pour le point 1, c'est un question de besoin: s'il est simple, D3 peut être suffisant
* Pour le point 2, plutôt pour ceux qui partent de D3
* Pour le point 3: soit parce que D3 permet des visualisations cartographiques originales soit parce qu'il y a besoin d'autres choses que des cartes pour la problématique.

!SLIDE

# Qui l'utilise?

* Journalistes de données (Le monde, Le Temps, Rue 89, Ouest Media Lab,...)
* Humanités numériques (chercheurs comme Martin Grandjean)
* Sociétés spécialisées en visualisation de données: Stamen Design, DataVeyes, We Do Data,...
* Pratiquants de la "data science" et du "big data"
* Sociétés ayant besoin de tableaux de bord

# Qui en a besoin potentiellement?

!SLIDE
<br>
# Plan

* Pourquoi D3?
* Prérequis technique
* Selections
* Data
* Scales & Axes
* Shapes
* Layouts 

!SLIDE

# Les "layouts"?

Pour pouvoir générer des graphes, ils permettent de spécifier les relations graphiques entre les élements d'un graphe.
Généralement, il faut une structure de données précises en entrée. Un layout est un algorithme qui génère une structure de données.

!SLIDE

# D3 permet de visualiser des données :

## en utilisant les standards du web: HTML, CSS, JS et SVG

## en transformant la donnée en élément HTML ou SVG

<a href="demos/data-to-element-001.html" target="_blank"><img src="images/data-to-element.png" alt="Données vers éléments"></a>

!SLIDE quieter
<br>
# Data-Driven Documents

## Le nom “D3” fait référence aux 3 initiales et au [Document Object Model (DOM) du W3C](http://www.w3.org/TR/dom/).

!SLIDE quieter
<br>
# Ressources HTML

## [Spécifications HTML 5](http://www.w3.org/TR/html5/), [HTML 5 for developers](https://developers.whatwg.org), [Mozilla Developer Network](https://developer.mozilla.org)

!SLIDE

# Base HTML 5

```
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>Titre de la page</title>
  <style></style>
  <script></script>
</head>
<body>
  <!-- Le reste du contenu -->
</body>
</html>
```

<a href="demos/html-basic-002.html" target="_blank">Démo</a>

!SLIDE quieter
<br>
# Ressources SVG

## [Spécifications SVG](http://www.w3.org/TR/SVG/), [MDN, partie SVG](https://developer.mozilla.org/en/SVG), [Référence de l'API D3](https://github.com/mbostock/d3/wiki/SVG-Shapes)

!SLIDE

# Démo SVG

```
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>Exemple SVG</title>
  <style></style>
  <script></script>
</head>
<body>
  <svg height="100" width="100">
    <circle cx="50" cy="50" r="40" stroke="black" stroke-width="0.5" fill="#F89C43" />
    Navigateur sans support SVG "inline".
  </svg> 
</body>
</html>
```

<a href="demos/svg-basic-003.html" target="_blank">Démo</a>

!SLIDE quieter
<br>
# Ressources CSS

## [Spécifications HTML 5](http://www.w3.org/TR/html5/), [HTML 5 for developers](https://developers.whatwg.org), [Mozilla Developer Network](https://developer.mozilla.org)

!SLIDE

# Démo CSS

```
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>Exemple CSS</title>
  <style>
  body {
    background-color: #F89C43;
  }
  </style>
  <script src="script.js"></script>
</head>
<body>
  <!-- Le reste du contenu -->
</body>
</html>
```

<a href="demos/css-basic-004.html" target="_blank">Démo</a>

!SLIDE quieter
<br>
# Ressources JavaScript

## [Spécifications SVG](http://www.w3.org/TR/SVG/), [MDN, partie SVG](https://developer.mozilla.org/en/SVG), [Référence de l'API D3](https://github.com/mbostock/d3/wiki/SVG-Shapes), [liste de livres JavaScript de Revolunet](http://jsbooks.revolunet.com) dont [Eloquent JavaScript](http://fr.eloquentjavascript.net/) en français

!SLIDE

# Démo JavaScript

```
<!doctype html>
<html lang="fr">
<head>
  <meta charset="utf-8">
  <title>Exemple JavaScript</title>
  <style></style>
  <script>
    console.log([5, 10, 15, 20, 25]);
  </script>
</head>
<body>
  <!-- Le reste du contenu -->
</body>
</html>
```

<a href="demos/css-basic-004.html" target="_blank">Démo</a>

!SLIDE
<br>
# JavaScript, l'incontournable

<quote><i>Le JavaScript peut être considéré comme la glue dans D3:<br>rien ne marche sans lui.</i></quote>

Il faut donc le maîtriser correctement pour pouvoir produire des visualisations personnalisées ou personnaliser les outils utilisant D3.

!SLIDE

# Chrome Developer Tools

<a href="https://developer.chrome.com/devtools" target="_blank"><img src="images/console-chrome.png" /></a>

!SLIDE

# Plugin FireBug (Mozilla Firefox)

<a href="http://getfirebug.com" target="_blank"><img src="images/console-firebug.png" /></a>

!SLIDE

# Debuggueur Mozilla Firefox par défaut

<a href="https://developer.mozilla.org/fr/docs/Outils/D%C3%A9bogueur" target="_blank"><img src="images/console-mozilla-default.png" /></a>

!SLIDE

# "Secrets of the Browser<br>Developer Tools"

<a href="http://devtoolsecrets.com" target="_blank"><img src="images/dev-tool-secrets.png" /></a>

!SLIDE

## Chercher par fonctions
http://bl.ocksplorer.org

# Se retrouver dans l'API
http://devdocs.io/d3/
https://github.com/mbostock/d3/wiki/API-Reference

## Faire vos démos en ligne
http://bl.ocks.org
http://tributary.io
http://jsfiddle.net

!SLIDE

# tag
fixed commit pointers

```
                      A---B---C 
                              ↑
                         release_1.0
```

```
% git commit -m "adding stuff to C"
```

```
                      A---B---C---D 
                              ↑
                         release_1.0
```

!SLIDE
# branch

floating commit pointer

```
                      A---B---C
                              ↑
                            master
```

```
% git commit -m "adding stuff to B"
```

```
                      A---B---C---D
                                  ↑
                                master
```

!SLIDE
# remote branch
a &#8220;remote&#8221; branch is just a commit pointer in your local repo

```
                                 master
                                    ↓
                    A---B---C---D---E
                            ↑       
                      origin/master    
```

it's updated whenever you do a `fetch` or `pull`, otherwise nothing remote about them

!SLIDE
# branch

text files in the `.git` directory

```
% ls -1 .git/refs/heads/**/*
.git/refs/heads/master
.git/refs/heads/my_feature_branch
```

```
% ls -1 .git/refs/remotes/**/* 
.git/refs/remotes/origin/HEAD
.git/refs/remotes/origin/master
.git/refs/remotes/origin/my_feature_branch
```

!SLIDE
# branch

contains is the SHA of the commit it's pointing at

```
% cat .git/refs/heads/master
0981e8c8ffbd3a1277dda1173fb6f5cbf4750d51

# .git/objects/09/81e8c8ffbd3a1277dda1173fb6f5cbf4750d51
```

!SLIDE
# branches point at commits

Contain `tree` (filesystem), `parent` commits and commit metadata
```
% git cat-file -p 0981e8c8ffbd3a1277dda1173fb6f5cbf4750d51
tree 4fd7894316b4659ef3f53426166697858d51a291
parent e324971ecf1e0f626d4ba8b0adfc22465091c100
parent d33700dde6d38b051ba240ee97d685afdaf07515
author Ted Naleid <contact@naleid.com> 1328567163 -0800
committer Ted Naleid <contact@naleid.com> 1328567163 -0800

merge commit of two branches
```

The ID is the SHA of the commit's contents

!SLIDE
<br/>
# branches
commits don't &#8220;belong to&#8221; branches, there's nothing in the commit metadata about branches

!SLIDE
# branches
a branch's commits are implied by the ancestry of the commit the branch points at

```
                                 feature
                                    ↓
                            E---F---G 
                           /
                      A---B---C---D 
                                  ↑ 
                                master
```

<code>master</code> is <code>A-B-C-D</code> and <code>feature</code> is <code>A-B-E-F-G</code>

!SLIDE
# HEAD

<code>HEAD</code> is the current branch/commit

This will be the parent of the next commit

```
% cat .git/HEAD
ref: refs/heads/master
```

most of the time it points to a branch, but can point directly to a SHA when &#8220;detached&#8221;


!SLIDE
# the reflog
a log of recent <code>HEAD</code> movement

```
% git reflog                                       
d72efc4 HEAD@{0}: commit: adding bar.txt
6435f38 HEAD@{1}: commit (initial): adding foo.txt
```

```
% git commit -m "adding baz.txt"
```

```
% git reflog                                       
b5416cb HEAD@{0}: commit: adding baz.txt
d72efc4 HEAD@{1}: commit: adding bar.txt
6435f38 HEAD@{2}: commit (initial): adding foo.txt
```

by default it keeps at least 30 days of history


!SLIDE
<br/>
# the reflog
unique to a repository instance

!SLIDE
# the reflog
can be scoped to a particular branch

```
% git reflog my_branch
347f5fe my_branch@{0}: merge master: Merge made by the recurs…
4e6007e my_branch@{1}: merge origin/my_branch: Fast-forward
32834d8 my_branch@{2}: commit (amend): upgrade redis version
2720e40 my_branch@{3}: commit: upgrade redis version 
```

!SLIDE
<br/>
# dangling commit
if the only thing pointing to a commit is the reflog, it's &#8220;dangling&#8221;

!SLIDE
# dangling commit
```
                    A---B---C---D---E---F
                                        ↑
                                      master
```

```
% git reset --hard SHA_OF_B
```

```
                    A---B---C---D---E---F
                        ↑
                      master
```

<code>C..F</code> are now dangling

!SLIDE
# dangling commit

but they will be safe for ~30 days because of the reflog

```
                                     HEAD@{1}
                                        ↓
                    A---B---C---D---E---F
                        ↑
                     master (also HEAD@{0})

```

<code>HEAD@{1}</code> will become <code>HEAD@{2}</code>..<code>HEAD@{N}</code> as refs are added to the reflog

!SLIDE
<br/>
# garbage collection 
once a dangling commit leaves the reflog, it is &#8220;loose&#8221; and is at risk of garbage collection

!SLIDE
<br/>
# garbage collection 
git does a <code>gc</code> when the number of &#8220;loose&#8221; objects hits a threshold

something like every 1000 commits

!SLIDE
<br/>
# garbage collection 
to prevent garbage collecting a commit, just point something at it

```
% git tag mytag SHA_OF_DANGLING_COMMIT
```

!SLIDE

# the index

a pre-commit staging area

<code>add -A :/</code> puts all changes in the index ready for commit

some bypass the index with <code>git commit -a -m "msg"</code>

!SLIDE
<br/>

# you should have courage to experiment

you have _weeks_ to retrieve prior commits if something doesn't work

!SLIDE shout

# understand where you are

## before you try to go somewhere else


!SLIDE quieter shout

# You need (at least) one repo visualization tool that you grok


!SLIDE small-code

# Here's Mine:

```
~/.gitconfig:
[alias]
l = log --graph --pretty='%Cred%h%Creset -%C(yellow)%d%Creset %s %Cblue[%an]%Creset %Cgreen(%cr)%Creset' --abbrev-commit --date=relative
la = !git l --all
```
```
git la
```

<img src="images/terminal.png" alt="" height="400px">

!SLIDE

# There are others - Git Tower

<img src="images/tower.png" alt="" height="500px">

!SLIDE

# There are others - SourceTree

<img src="images/sourcetree.png" alt="" height="500px">

!SLIDE shout
# Learn<br/>&#8220;the good parts&#8221; and make them your own

!SLIDE
# checkout -

just like `cd -`, takes you to your previous branch
```
                        E---F  ← feature & HEAD
                       /
                  A---B---C---D 
                              ↑ 
                           master
```
```
% git checkout -
```
```
                        E---F  ← feature 
                       /
                  A---B---C---D 
                              ↑ 
                       master & HEAD
```


!SLIDE
# commit --amend

redo the last commit
```
                        A---B---C
                                ↑    
                          master & HEAD
```

```
<... change some files ... > 
% git commit -a --amend --no-edit
```
```
                              C' ← master & HEAD
                             /
                        A---B---C
                                ↑    
                  (dangling but still in reflog)
```


!SLIDE 
<br/>
# rebasing 

reapplies a series of commits to a new parent commit

then moves the current branch pointer

!SLIDE 
# rebasing 

```
                        E---F  ← feature & HEAD
                       /
                  A---B---C---D 
                              ↑ 
                           master
```

```
% git rebase master
```

```
                  (dangling but still in reflog)
                            ↓
                        E---F
                       /
                  A---B---C---D---E'--F'
                              ↑       ↑ 
                           master  feature & HEAD
```

!SLIDE 
# rebasing 

```
% git rebase --abort
```

If you get in trouble `--abort` and try again.  

If you _really_ get in trouble, you can `reset --hard` back to your last commit.

!SLIDE 
<br/>
# rebasing - a private activity
should never be done with commits that have been pushed

!SLIDE
<br/>
# rebasing - a private activity
public rebasing is bad as others could have the same commits with different SHAs


!SLIDE 
# cherry picking 

apply a subset of changes from another branch

```
                            E---F---G 
                           /
                      A---B---C---D 
                                  ↑ 
                             master & HEAD
```

```
% git cherry-pick SHA_OF_F
```

```
                            E---F---G 
                           /
                      A---B---C---D---F' 
                                      ↑ 
                                 master & HEAD
```


!SLIDE quieter shout

# `reset` is for moving branch pointers


!SLIDE 
# reset --soft 

```
                    A---B---C---D---E
                                    ↑
                                  master
```

```
% git reset --soft SHA_OF_C
```

```
                    working dir & index still look like
                                    ↓
                    A---B---C---D---E
                            ↑
                          master
```
1. moves <code>HEAD</code> & the current branch to the specified <code>&lt;SHA&gt;</code>
2. index - unchanged 
3. working directory - unchanged 


!SLIDE 
# reset --soft 

useful for squashing the last few messy commits into one pristine commit
```
                    working dir & index still look like
                                    ↓
                    A---B---C---D---E
                            ↑
                          master
```

```
% git commit -m "perfect code on the 'first' try"
```

```
                    A---B---C---E'
                                ↑
                              master
```

!SLIDE 
# reset --soft 

What if you've got a more complicated situation:

```
                              master
                                ↓
                A---B---C---D---E 
                 \       \
                  F---G---H---I ← feature & HEAD
```

Can't `reset` our way out of this, right?

!SLIDE 
# reset --soft 

Just do one last merge

```
% git merge master
```

```
                              master
                                ↓
                A---B---C---D---E 
                 \       \       \
                  F---G---H---I---J ← feature & HEAD
```

!SLIDE 
# reset --soft 

and then we can `reset` into a single commit 

```
% git reset --soft master
```

```
                A---B---C---D---E ← feature & HEAD & master
                                 \
                                  J ← working dir & index 
```

```
% git commit -m "pristine J"
```

```
                              master
                                ↓
                A---B---C---D---E---J' ← feature & HEAD 
```

!SLIDE 
# reset --hard
```
% git reset --hard <SHA>
```

<br/>
1. moves <code>HEAD</code> & the current branch to the specified <code>&lt;SHA&gt;</code> 
2. clean the index, make it look like <code>&lt;SHA&gt;</code> 
3. clean the working copy, make it look like <code>&lt;SHA&gt;</code> 

<span class="danger">dangerous</span> if you have <span class="danger">uncommitted work</span>, useful for undoing bad commits

!SLIDE 
# reset --hard HEAD 
```
% git reset --hard HEAD
```

just means clean out the working directory and any staged information, don't move the branch pointer

for more info on <code>reset</code>, see: <a href="http://progit.org/2011/07/11/reset.html">http://progit.org/2011/07/11/reset.html</a>


!SLIDE 
<br/>
# fetch 

download new commits and update the remote branch pointer

does not move any local branches

!SLIDE 
# fetch 

```
                   origin/master
(local)                  ↓
                     A---B---C---D ← master & HEAD 
```
```
                     A---B---E---F   
(origin)                         ↑ 
                              master (in remote repo)  
```


```
% git fetch
```


```
                         origin/master
                               ↓
                           E---F
(local)                   /
                     A---B---C---D ← master & HEAD
```


!SLIDE 
<br/>
# pull 

<code>pull</code> is <code>fetch</code> plus <code>merge</code>

!SLIDE 
# pull 

```

                   origin/master
(local)                  ↓
                     A---B---C---D ← master & HEAD
```
```
                     A---B---E---F   
(origin)                         ↑ 
                              master (local ref in remote repo)  
```

```
% git pull
```


```
                         origin/master
                               ↓
                           E---F----
                          /         \
(local)              A---B---C---D---G ← master & HEAD
```

!SLIDE 
# the &#8220;right&#8221; way to pull down changes from the server

1. <code>stash</code> any uncommitted changes (if any)
2. <code>fetch</code> the latest refs and commits from origin
3. <code>rebase -p</code> your changes (if any) onto origin's head<br/> else, just fast-forward your head to match origin's
4. un-<code>stash</code> any previously stashed changes

<code>fetch</code> + <code>rebase</code> avoids unnecessary commits

!SLIDE

# rebasing pull
<br/>
As of git 1.8.5, git has finally added a rebase switch to `pull`:

```
% git pull --rebase
```

This will do the `fetch` + `rebase` for you (you still stash on your own).

!SLIDE shout myth
# git is dangerous 
## myth #1

!SLIDE shout
# git is the _safest_ version control 
## reality

!SLIDE shout myth
# git lets you<br/>rewrite history
## myth #2

!SLIDE shout
# rewriting <br/>history is a _lie_
## reality

!SLIDE shout myth
# git syntax is terrible
## myth #3

!SLIDE shout 
#  git syntax is<br/>_really terrible_
## reality

!SLIDE shout
# git mislabels things

## ex: git branches aren't what you think they are

!SLIDE shout
# throw away your preconceptions from other version control systems

!SLIDE shout
# Questions? 


!SLIDE shout
# Bonus Section!

!SLIDE 
# reset (default)

```
% git reset [--mixed] <SHA>
```

<br/>

1. moves <code>HEAD</code> & the current branch to the specified <code>&lt;SHA&gt;</code> 
2. clean the index, make it look like <code>&lt;SHA&gt;</code> 
3. working directory - unchanged

<code>git reset HEAD</code> will unstage everything in the index


!SLIDE 
<br/>
# squashing 

compresses N commits into one commit that's appended to a destination branch

!SLIDE 
# squashing 

```
                              E---F---G ← feature
                             /
                A---B---C---D 
                            ↑ 
                     master & HEAD
```

```
% git merge --squash feature
```

```
                              E---F---G ← feature
                             /
                A---B---C---D---G' 
                                ↑ 
                         master & HEAD
```

cleans up history, when the thinking behind <code>E..F</code> is unimportant

!SLIDE

# recovering commits

Oops, I really wanted <code>C</code>!

```
                              C' ← master & HEAD
                             /
                        A---B---C ← (dangling)
```
```
% git reflog master  # find SHA_OF_C 
% git reset --hard SHA_OF_C
```
```
                              C' ← (dangling)
                             /
                        A---B---C
                                ↑    
                            master & HEAD
```