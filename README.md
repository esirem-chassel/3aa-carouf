# Projet Carouf

L'objectif de ce projet est de réaliser une application console de gestion d'inventaire.
Vous pouvez travailler en équipe sur le projet, mais l'essentiel est de s'exercer en C++.

> [!NOTE]
> Dans le cadre de l'exercice, on créera les données "en dur" dans le code dans un premier temps.

# Gestion de l’inventaire des produits

Nous aurons besoin de gérer l'inventaire des produits ainsi que des stocks.
Pour cela, à minima une classe Produit est nécessaire, avec le nom de chaque produit, l'identifiant interne (sous forme de chaîne), la catégorie du produit, son poids, son prix de vente, son mode de conservation (ambiant, froid ou gel) ainsi que sa valeur fournisseur.
Les catégories doivent également être définies, avec un nom.
On doit connaître la quantité de produits en stock et en rayon.

# Gestion des clients (compte fidélité)

Les clients peuvent disposer de compte fidélité. En ce cas, nous retenons leur nom, prénom, adresse, et leur solde fidélité. Chaque palier de 10 euros d'achats rapporte 5 points fidélité.

# Gestion des fournisseurs et livraisons

Chaque fournisseur, défini par un nom, effectue des livraisons d'un nombre de produits, à une date donnée.
On retient les livraisons à venir, ainsi que celles passées.
Lorsqu'une livraison est effectuée, on vérifie pour chaque produit, la quantité délivrée contre la quantité attendue.
Une livraison avec des produits manquants doit forcément aboutir sur la programmation d'une livraison ultérieure des produits manquants.

# Gestion des ventes

On gère la facturation automatisée de chaque transaction de vente. Une vente peut être associée ou non à un compte client.
Il est nécessaire de retenir tous les détails de la facturation, y compris la date et l'heure, et la valeur individuelle de chaque produit.

# Droits applicatifs

La gestion des droits applicatifs se fait via paramètre au démarrage.
Vous devez prendre en considération dans votre application un paramètre console au lancement "profile".

| profile | Produits | Clients | Fournisseurs / Livraisons | Ventes | Logs |
| ------- | -------- | ------- | ------------------------- | ------ | ---- |
| admin   | RW       | RW      | RW                        | RW     | R    |
| manager | RW       | RW      | RW                        | RW     | -    |
| sales   | R        | RW      | -                         | RW     | -    |

Si aucun profil n'est fourni au démarrage, on assumera un profil "sales"

# Gestion des journaux (logs)

Chaque opération effectuée de création/modification/suppression de produits, fournisseurs, clients, livraisons ou ventes doit donner lieu à une ligne de journalisation, un "log". Par exemple `2025-03-15 15:21:15 : suppression du fournisseur #35`.

# Interactions attendues

Est attendu en console une interface complète via questions.
A vous de "mapper" l'ensemble de l'application.
Par exemple, au démarrage de l'application, celle-ci peut demander à l'utilisateur s'il souhaite gérer les produits, les clients... selon son profil.

# Extension

Si vous avez suffisemment avancé, vous pouvez réaliser la persistence applicative.
Pour cela, sauvegardez vos différentes données dans des fichiers adaptés, à un format lisible, et chargez vos données à l'ouverture de votre application.

> [!CAUTION]
> Il est déconseillé de se lancer dans des bases de données trop rapidement. Mais si vous le faites, sachez que SQLite est aisé à utiliser dans ce cadre.
