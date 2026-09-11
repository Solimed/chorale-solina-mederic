# Site de la chorale — Mariage de Solina & Médéric

Site web (une seule page) pour que les choristes révisent partitions et enregistrements.
Messe du **17 octobre 2026**, église Saint-Pierre-et-Saint-Paul, Le Neubourg.

Même outil que le site de la chorale de Loïc & Lola, en **bleu marine**.

## Contenu du dossier

```
Site chorale/
├── index.html      ← la page (design + code)
├── Partitions/     ← les partitions PDF (une par chant)
├── Audio/          ← les enregistrements MP3
└── README.md
```

> ⚠️ Les dossiers s'appellent **Partitions** et **Audio** (avec majuscule). GitHub
> Pages est sensible à la casse : garde exactement cette orthographe dans `index.html`.

## Ordre des chants (déduit du livret de messe)

| # | Moment | Chant | Base du nom de fichier |
|---|--------|-------|------------------------|
| 1 | Chant d'entrée | Céleste Jérusalem | `01-celeste-jerusalem` |
| 2 | Gloria | Messe de saint Claude de la Colombière | `02-gloria` |
| 3 | Psaume 138 | Seigneur, tu connais si bien mon âme | `04-psaume` ✅ PDF |
| 4 | Alléluia | Taizé | `05-alleluia` |
| 5 | Invocation de l'Esprit Saint | Viens, Esprit très Saint (Ad Dei Gloriam) | `06-viens-esprit-saint` ✅ PDF |
| 6 | Action de grâce (chanté 2 fois) | Laudate Dominum (Médéric & Solina) | `06-laudate-dominum` |
| 7 | Prière universelle | O Marie, prends nos prières | `07-o-marie` |
| 8 | Offertoire | Hostia Sancta | `08-hostia-sancta` |
| 9 | Sanctus | | `09-sanctus` |
| 10 | Anamnèse | | `10-anamnese` |
| 11 | Notre Père (chanté) | Glorious | `11-notre-pere` |
| 12 | Agnus Dei | Saint Augustin | `12-agnus-dei` |
| 13 | Communion | En Esprit et en Vérité | `13-en-esprit-et-en-verite` |
| 14 | Communion | En toi ma confiance | `14-en-toi-ma-confiance` |
| 15 | Action de grâce | Anima Christi | `15-anima-christi` |
| 16 | Chant d'envoi | Je veux voir Dieu | `16-je-veux-voir-dieu` |

> Les 2 partitions déjà en place gardent leur nom d'origine (`04-psaume.pdf`,
> `06-viens-esprit-saint.pdf`) ; peu importe le numéro, c'est l'ordre dans
> `index.html` qui fait foi.

## Ajouter une partition

1. Dépose le PDF dans `Partitions/` (nom conseillé : la base ci-dessus + `.pdf`,
   ex. `03-gloria.pdf`).
2. Dans `index.html`, sur la ligne du chant, renseigne `sheetMusic` :
   `sheetMusic: "Partitions/03-gloria.pdf",`

## Ajouter les enregistrements

1. Dépose les MP3 dans `Audio/` (ex. `03-gloria-soprano.mp3`, `…-alto`, `…-tenor`,
   `…-basse`, `…-tous`).
2. Dans `index.html`, renseigne le bloc `audio` du chant :
   ```js
   audio: {
     soprano: "Audio/03-gloria-soprano.mp3",
     alto:    "Audio/03-gloria-alto.mp3",
     tenor:   "Audio/03-gloria-tenor.mp3",
     basse:   "Audio/03-gloria-basse.mp3",
     tous:    "Audio/03-gloria-tous.mp3"
   },
   ```
   Laisse `""` pour ce qui manque encore : le bouton reste simplement grisé.

`<voix>` = `soprano`, `alto`, `tenor`, `basse` ou `tous`.

## Mettre à jour le site en ligne

Depuis Git Bash dans ce dossier :

```bash
git add -A && git commit -m "Mise à jour" && git push
```

Le site se met à jour tout seul en ~1 minute.
