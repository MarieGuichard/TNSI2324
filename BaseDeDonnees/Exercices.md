# Les bases de données: Exercices. 

**Exercice 1**:

Une sandwicherie effectuant des livraisons à domicile dispose d'une base de données dont certains extraits de tables sont reproduits ici. La table `Sandwichs`comporte les informations relatives aux sandwichs proposés à la vente. 

-------------

| Nom_Sandwich  | Prix  |
| :-----------: | :---: |
| Cheeseburger  | 3.90  |
| Double Cheese | 4.90  |
|    Italien    | 4.90  |
|   Foie Gras   | 15.00 |

La table `Clients`comporte les informations relatives aux clients. 

|   Nom   | Prénom |                  Adresse                  | Numéro_Client |
| :-----: | :----: | :---------------------------------------: | :-----------: |
| Bernard | Alain  |  9 rue de Lille, 59650 Villeneuve d'Ascq  |      42       |
| Bernard | Joseph | 34 avenue Calmette 59700 Marcq en Baroeul |      27       |

La table `Commandes`comporte les informations relatives aux commandes passées. 

| Numéro de Client | Nom_Sandwich | Quantité | Numéro_commande | Date       |
| ---------------- | ------------ | -------- | --------------- | ---------- |
| 42               | Italien      | 2        | 12452           | 12-10-2022 |
| 42               | Fois Gras    | 1        | 12452           | 12-10-2022 |
| 27               | Cheesebuger  | 4        | 13587           | 18-11-2022 |

a. Une commande peut-elle comporter plusieurs sandwichs différents? 

b. Quel est le schéma de relation de la table `Sandwichs`? Celui de la table `Clients`? Celui de la table `Commandes`? 

c. La table `Sandwichs`comporte-t-elle un attribut qui soit clé primaire? Un attribut qui est clé étrangère? 

d. Répondre aux mêmes questions pour la table `Clients`et pour la table `Commandes`. 

e. Cette base de données semble-t-elle bien modélisée? Si ce n'est pas le cas, justifier pourquoi et proposer des modifications. 



**Exercice 2**:

Un commerçant utilise plusieurs fichiers pour gérer ses produits. On considère un fichier destiné à gérer des produits frais. Le tableau présenté est un extrait du contenu de ce fichier. 

Les quatre colonnes contiennent respectivement un identifiant numérique, le nom d'un produit, son prix et la marque qui le commercialise. Les mêmes noms de marques peuvent apparaître de nombreuses fois dans la colonne `marque`mais aussi dans les fichiers correspondant à d'autres types de produits. 

| id   | nom       | prix | marque     |
| ---- | --------- | ---- | ---------- |
| 17   | Yaourt6   | 2.52 | Yopnone    |
| 21   | Yaourt12  | 4.93 | Dalait     |
| 25   | Beurre250 | 2.27 | Croisement |
| 28   | Crème50   | 2.74 | Dalait     |
| 31   | Crème70   | 3.79 | Yopnone    |

A partir de ce fichier, construire une relation `Frais`,(pour les produits frais), et une relation `Marques`suivant le modèle relationnel permettant d'éviter la redondance d'informations. Indiquer une clé primaire pour chacune des deux tables et préciser un champ jouant le rôle d'une clé étrangère. 

### Exercice 3:

On souhaite modéliser, de manière nettement simplifiée, une base de données contenant les informations relatives à un forum hébergé sur Internet. 

Une première relation, `Users`, contient les informations relatives aux comptes des utilisateurs du forum: pseudonyme, adresse email, date d'enregistrement, droits (administrateur, modérateur, ...). 

Une seconde relation, `Posts`, contient les informations relatives aux messages postés sur le forum: titre, contenu, date et heure du message, auteur. 

a. Proposer un schéma relationnel permettant de représenter les utilisateurs. Donner un exemple d'enregistrement. 

b. La relation `Users `comporte-t-elle une clé primaire? Si oui, laquelle? 

c. Proposer un schéma relationnel permettant de représenter les messages. Donner un exemple d'enregistrement. 

d. La relation `Posts`comporte-t-elle une clé primaire? Si oui, laquelle? Comporte-t-elle une clé étrangère? Si oui, laquelle ? 

e. On souhaite autoriser les utilisateurs à changer de pseudonyme. Quelles adaptations des schémas relationnels seront nécessaires et pourquoi? 

f. On souhaite ajouter une fonctionnalité supplémentaire sur le forum: la possibilité pour les utilisateurs de créer un ou plusieurs albums reprenant les meilleurs messages du forum, qu'il s'agisse des leurs ou non. Proposer un modèle relationnel pour cette situation. 

### Exercice 4:

1. Donner la modélisation relationnelle d'un bulletin scolaire. Cette dernière doit permettre de mentionner:

   - des élèves, possédant un numéro relationnelle alphanumérique unique,
   - un ensemble de matières fixées, mais qui ne sont pas données. 
   - au plus une note sur 20, par matière et par élève. 

2. Dire si chacun des ensembles est une relation valide pour le schéma de la base de données du bulletin de notes. 

   a.

   - Elève = {}

    - Matière = {}
    - Note = {}

   b. 

   - Elève = {('Emile','Louis','AB112CD')}

    - Matière = {('NSI',1),('Sport',2)}
    - Note = {'AB112CD',1,15}

   c. 

   - Elève = {('Emile','Louis','AB112CD')}

    - Matière = {('NSI',1),('Sport',2)}
    - Note = {'AB112CD',3,15}

   d. 

   - Elève = {('Emile','Louis','AB112CD')}

    - Matière = {('NSI',1),('Sport',2)}
    - Note = {('AB112CD',1,15),('AB112CD',2,4) }

   e. 

   - Elève = {('Emile','Louis','AB112CD')}

    - Matière = {('NSI',1),('Sport',2)}
    - Note = {('AB112CD',1,15),('AB112CD',1,4) }



### Exercice 5:

Un hôtel gère ses chambres avec une base de données. La relation `Chambres`permet d'enregistrer: le numéro de la chambre, la date (le jour réservé), l'heure d'arrivée, le nombre de lits, la présence d'un balcon. 

L'attribut `date`est au format chaîne de caractères et l'attribut `balcon`au format booléen. 

Le tableau ci-dessous précise le contenu d'une ligne. 

| numéro | date       | heure | lits | balcon |
| ------ | ---------- | ----- | ---- | ------ |
| 108    | '18/08/22' | 17    | 3    | True   |

Ecrire en SQL les requêtes permettant d'obtenir:

1. les numéros des chambres réservées à la date du 20/05/22. 
2. Les numéros des chambres réservées à la date du 20/05/22 qui ont un balcon. 
3. Le nombre de chambres sans balcon réservées à la date du 20/05/22. 
4. Le nombre de chambres réservées le 18/05/22 ayant 2 ou 3 lits. 
5. L'heure d'arrivée du premier client le 15/05/22. 



### Exercice 6: 

Une librairie est gérée à l'aide d'une base de données. Le modèle relationnel contient les cinq relations décrites ci-dessous avec leur schéma:

```
Livres (Id, Titre, PrixHT, Année, Id_genre, Id_éditeur)
Auteurs(Id, Nom, Prénom)
Ecrits(Id_auteur,Id_titre)
Genres(Id, Genre)
Editeurs(Id, Nom)
```

Les champs `Id`et le couple `(Id_auteur,Id_titre)`sont des clés primaires. 

Le champ `Id_genre`est une clé étrangère en référence à la clé primaire `Id` de la relation `Genres`. 

Le champ `Id_éditeur`est une clé étrangère en référence à la clé primaire `Id` de la relation `Editeurs`. 

Le champ `Id_auteur`est une clé étrangère en référence à la clé primaire `Id` de la relation `Auteurs`. 

Le champ `Id_titre`est une clé étrangère en référence à la clé primaire `Id` de la relation `Lives`. 

Tous les champs dont le titre est `Id`ou commence par `Id`et le champ `Année`sont de type entier. 

Le champ `PrixHT`est de type flottant. Les autres champs sont du type chaîne de caractères. 

Ecrire en SQL les requêtes permettant d'obtenir:

1. Les titres des livres de la base.
2. Les titres et les années de parution des livres.
3. Les titres des livres qui commencent par la lettre "A". 
4. Le prix HT maximal d'un livre de la base. 
5. Tous les champs de la table `Auteurs`. 
6. Le nombre d'auteurs contenus dans la base. 
7. Le nombre de livres référencés dans la base et le prix moyen. 
8. Les noms et prénoms de tous les auteurs par ordre alphabétique de nom. 
9. Les noms des auteurs dont le prénom est Pierre. 
10. Les titres des livres coûtant plus de 15 euros HT avec leur prix HT. 
11. Les titres des livres avec le nom de leur éditeur. 
12. Les titres des livres du genre "science". 
13. Les années de parution de livre dans le genre "sciences " sans doublon. 
14. Les titres des livres du genre "science" parus en 2019 contenant la chaîne "nsi" dans le titre. 
15. Le titre du livre (ou des livres) dont le prix est maximal. 
16. Les titres des livres avec les noms des auteurs respectifs. 
17. Les genres pour lesquels il n'y a aucun livre. 



### Exercice 7(bac): 

L’énoncé de cet exercice peut utiliser les mots du langage SQL suivants : 

`CREATE TABLE, SELECT, FROM, WHERE, JOIN ON, INSERT INTO, VALUES, UPDATE, SET, DELETE, COUNT, DISTINCT, AND, OR, AS, ORDER BY, ASC, DESC `

Un site web recueille des données de navigation dans une base de données afin d'étudier les profils de ses visiteurs. Chaque requête d'interrogation d'une page de ce site est enregistrée dans une première table dénommée `Visites` sous la forme d'un 5-uplet : `(identifiant, adresse IP, date et heure de visite, nom de la page, navigateur)`. 

Le chargement de la page index.html par 192.168.1.91 le 12 juillet 1998 à 22h48 aura par exemple été enregistré de la façon suivante : 

`(1534, "192.168.1.91", "1998-07-12 22:48:00", "index.html", "Internet  explorer 4.1"`).

La commande SQL ayant permis de créer cette table est la suivante:

```
CREATE TABLE Visites (
	identifiant INTEGER NOT NULL UNIQUE,
	ip VARCHAR(15),
	dateheure DATETIME,
	nompage TEXT,
	navigateur TEXT
);

```

1. a. Donner une commande d'interrogation en langage SQL permettant d'obtenir l'ensemble des 2-uplets (adresse IP, nom de la page) de cette table.

   b. Donner une commande en langage SQL permettant d'obtenir l'ensemble des adresses IP ayant interrogé le site, sans doublon. 

   c. Donner une commande en langage SQL permettant d'obtenir la liste des noms des pages visitées par l'adresse IP 192.168.1.91

Ce site web met en place, sur chacune de ses pages, un programme en javascript qui envoie au serveur, à intervalle régulier de 15 secondes, le temps en secondes de présence sur la page. Ces envois contiennent tous la valeur de identifiant correspondant au chargement initial de la page. Par exemple, si le visiteur du 12 juillet 1998 est resté 65 secondes sur la page, celle-ci a envoyé au serveur les 4 doublets (1534, 15), (1534, 30), (1534, 45) et (1534, 60).

Ces données sont enregistrées dans une table nommée Pings créée avec la commande ci-dessous :

```
CREATE TABLE Pings (
	identifiant INTEGER,
	duree INTEGER
);
```

En plus de l'inscription d'une ligne dans la table `Visites`, chaque chargement d'une nouvelle page provoque l'insertion d'une ligne dans la table `Pings` comprenant l'identifiant de ce chargement et une durée de 0.

Les attributs identifiant des tables `Visites `et `Pings` partagent les mêmes valeurs.

2. a. De quelle table l’attribut `identifiant` est-il la clé primaire ?

   b. De quelle table l’attribut` identifiant` est-il une clé étrangère ? 

   c. Par conséquent, quelles vérifications sont automatiquement effectuées par le système de gestion de base de données ?

3. Le serveur reçoit le doublet `(identifiant, duree)` suivant : (1534, 105). Écrire la commande SQL d'insertion qui permet d'ajouter cet enregistrement à la table `Pings`.

On envisage ensuite d'optimiser la table en se contentant d'une seule ligne par identifiant dans la table `Pings` : les valeurs de l'attribut `duree` devraient alors être mises à jour à chaque réception d'un nouveau doublet` (identifiant, duree)`.

4. a. Écrire la requête de mise à jour permettant de fixer à 120 la valeur de l'attribut `duree `associée à l'identifiant 1534 dans la table Pings. 

   b. Expliquer pourquoi on ne peut pas être certain que les données envoyées par une page web, depuis le navigateur d'un client, via plusieurs requêtes formulées en javascript, arrivent au serveur dans l'ordre dans lequel elles ont été émises. 

   c. En déduire qu'il est préférable d'utiliser une requête d'insertion plutôt qu'une requête de mise à jour pour ajouter des données à la table `Pings`.

5. Écrire une requête SQL utilisant le mot-clef JOIN et une clause WHERE, permettant de trouver les noms de toutes les pages qui ont été consultées plus d'une minute par au moins un utilisateur.


