# Rapport Clair

Rapport Clair transforme un export CSV d’interventions en rapport client prêt à imprimer ou à enregistrer en PDF.

Le traitement s’effectue dans le navigateur : les données importées ne sont pas envoyées à un serveur.

## Fonctionnalités

- import CSV avec séparateur virgule ou point-virgule ;
- contrôle des dates, durées, statuts et colonnes obligatoires ;
- filtrage par client et période ;
- ajout du nom et du logo de l’entreprise ;
- calcul du nombre d’interventions, du temps total et des interventions résolues ;
- mise en page A4 et export PDF par la fonction d’impression du navigateur ;
- exemple fictif et fichier CSV modèle inclus.

## Utilisation locale

Le projet est un site statique, sans installation ni compilation.

1. Ouvrir `dist/index.html` dans un navigateur moderne.
2. Cliquer sur **Charger l’exemple**, ou importer un fichier CSV.
3. Personnaliser le rapport.
4. Cliquer sur **Imprimer / enregistrer en PDF**.

Pour utiliser un petit serveur local :

```bash
python -m http.server 8080 --directory dist
```

Puis ouvrir <http://localhost:8080>.

## Format CSV

Encodage UTF-8, 2 Mo et 2 000 lignes maximum. Les colonnes obligatoires sont :

```text
date;client;intervention;duree_minutes;statut
2026-09-02;Cabinet Horizon;Mise à jour des postes;90;Résolu
```

- `date` : `AAAA-MM-JJ` ou `JJ/MM/AAAA` ;
- `duree_minutes` : nombre positif ou nul ;
- `statut` : `Résolu`, `En cours` ou `À planifier`.

## Structure

```text
dist/
├── index.html
├── style.css
├── core.js
├── app.js
├── exemple-interventions.csv
└── kit-commercial.txt
```

## Limites de cette première version

- pas d’import XLSX natif : exporter le fichier Excel en CSV UTF-8 ;
- pas de paiement, d’abonnement ou de compte utilisateur ;
- pas de stockage durable ni d’envoi automatique ;
- export PDF via l’impression du navigateur.

## Confidentialité

Le CSV et le logo restent dans la session du navigateur. Recharger la page efface les données chargées.

## Licence

Tous droits réservés. Ce dépôt ne donne aucune autorisation de copie, modification ou redistribution sans accord écrit du propriétaire.
