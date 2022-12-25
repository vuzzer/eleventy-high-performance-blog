---
title: Créer son premier smart contract.
description: Les éditeurs en ligne sont suffisants pour apprendre Solidity ou l'utiliser pour vos bugs.
date: 2022-12-25
scheduled: 2022-12-25
tags: development
layout: layouts/post.njk
---

Pour construire des smarts contracts, nous avons besoin d'un environnement de développement dans lequel travailler. Ici, vous avez deux options. Vous pouvez soit configurer votre environnement de développement dans le navigateur, soit sur votre machine. Dans le premier cas, nous avons Remix IDE et EthFiddle. Et dans le second cas, nous avons Hardhat et Truffle. Cet article se concentrera sur l'environnement Remix pour développer et tester vos smart contracts.

**Prerequis**
* Un esprit curieux

#### Qu'est-ce qu'un smart contract ?
Nous allons définir le smart contract de manière technique.

* Un smart contract est une **collection de code (fonctions)** et **données (état)** qui reside à une adresse spécifique sur la blockchain Ethereum. 
* Les contracts peuvent hériter d'autre contracts
* Un contrat et ses fonctions doivent être appelés pour que quelque chose se passe.
* Les contracts en Solidity sont similaires aux **classes dans les languages de programmation orienté-objet**

#### Introduction à Solidity

[Solidity](https://docs.soliditylang.org/en/v0.8.17/) est language de programmation orienté-objet compilé crée par l'équipe Ethereum qui as une syntaxe similaire au Javascript. Contrairement à JavaScript, Solidity est fortement typé et fait un usage intensif de l'héritage.

Le compilateur Solidity compile le smart contract en **Bytecode** et en **ABI (Application Binary Interface)**.
Le bytecode est le language de bas niveau interpreté par la machine virtuelle Ethereum (EVM) pour executer des fonctions. De l'autre côté, l'ABI est un fichier JSON utilisé par les applications web ou mobile pour appeler les functions des smarts contracts.

#### Remix
Remix est un environnement de développement intégré (IDE) open-source, pour le web et le bureau, destiné au développement Ethereum. C'est l'outil de développement le plus facile à utiliser pour commencer à construire sur Ethereum, et il dispose d'une énorme collection de plugins pour étendre son expérience. 

Remix vous aide à écrire du code Solidity directement dans le navigateur, et dispose d'outils pour tester, déboguer et déployer votre smart contract sur la blockchain.

Vous pouvez visiter Remix sur [https://remix.ethereum.org/](https://remix.ethereum.org/).

**Navigeur dans Remix**

Lorsque vous ouvrez Remix pour la première fois, vous êtes accueilli par un écran comme celui-ci.

![image](https://i.imgur.com/4RqBi40.png)

Dans la barre latérale de gauche, vous pouvez basculer entre <mark>l'explorateur de fichiers</mark>, <mark>le compilateur Solidity</mark>, le <mark>Deployer</mark> et un <mark>panneau d'extensions</mark>.

En bas, il y a un panneau de sortie, qui affiche la sortie de votre compilation, vos déploiements, et vos appels de fonction.

Au milieu se trouve l'endroit où vous allez éditer le code. Actuellement, il affiche l'écran d'accueil de l'IDE, mais dès que nous ouvrirons un fichier, il deviendra l'éditeur de code.

**Workflow de Remix**

Dans la barre latérale, si vous regardez sous le dossier des <mark>contracts</mark> - Remix crée 3 smarts contracts de base pour aider les gens à apprendre Solidity. Jetons un coup d'oeil à <mark>1_Storage.sol</mark>.

![image](https://i.imgur.com/OdGQABf.png)

Nous pouvons voir l'éditeur de code maintenant.

Dans l'explorateur de fichiers, nous pouvons également voir des options pour créer un nouveau fichier ou répertoire, télécharger des fichiers locaux ou importer des fichiers de Github.

Pour compiler nos contrats, nous passons à l'onglet <mark>Compilateur Solidity</mark>, et nous verrons quelque chose comme ceci dans la barre latérale.

<img alt="image" src="https://i.imgur.com/kr0a26J.png" width="200" height="400">

Ici, nous pouvons choisir la <mark>version du compilateur</mark> que nous voulons, le langage de programmation du smart contract que nous utilisons (la plupart du temps, vous n'utiliserez que Solidity), et quelques autres options de configuration.

En cliquant sur <mark>Compile 1_Storage.sol</mark>, vous compilerez le contrat et le rendrez prêt pour le déploiement.

<img alt="image" src="https://i.imgur.com/KieTxyw.png" width="200" height="400">

En passant à l'onglet <mark>Déploiement</mark>, nous verrons quelque chose comme ceci dans la barre latérale.

<img alt="image" src="https://i.imgur.com/svMiVS3.png" width="200" height="400">


Maintenant que tout est prêt, nous allons écrire notre premier contrat intelligent à l'étape suivante.

#### Ecrire votre premier smart contract

Comme tout autre langage de programmation, la première étape consiste à créer un fichier de projet pour le langage. Ici, vous allez créer un fichier intitulé "legend.sol". L'extension de fichier "sol" correspond à Solidity, tout comme "js" correspond à Javascript.

1. Crée le fichier MyContract.sol sous le dossier <mark>contracts</mark>

![image](https://blog.logrocket.com/wp-content/uploads/2021/11/contracts-directory.png)

2. Ecrire le code

```js
    // SPDX-License-Identifier: GPL-3.0
    pragma solidity ^0.8.1;
    contract MyFirstContract {
        string public myString = “I am a legend !”;
    }
```

Lorsque notre code Solidity est enregistré, Remix compile automatiquement notre code, créant un bytecode qui est envoyé au réseau, ainsi qu'une ABI pour interagir avec le contrat déployé.

Nous pouvons inspecter à la fois le bytecode et l'ABI dans l'onglet Compilateur Solidity :

![image](https://blog.logrocket.com/wp-content/uploads/2021/11/ABI.png)

Si notre code se compile avec succès, nous pouvons commencer à le déployer et à nous interfacer avec lui sous l'onglet <mark>déploiement</mark>.

Dans cet onglet, nous pouvons choisir notre environnement, le contrat à déployer et le compte avec lequel le déployer. <mark>JavaScript VM</mark> signifie que Remix maintiendra un réseau blockchain à l'intérieur de notre navigateur pour que les tests soient aussi rapides que possible.

![image](https://blog.logrocket.com/wp-content/uploads/2021/11/deployed-contracts.png)

Au bas de l'onglet, nous voyons <mark>Contrats déployés</mark>, ce qui indique que nous pouvons déployer plusieurs instances d'un ou plusieurs contrats.


**Félicitation 🎉🎉**
Voilà, félicitations, vous venez d'écrire votre premier contrat intelligent.

**Recommendé**
Pour apprendre davantage:
* Visitez la [documentation de solidity](https://docs.soliditylang.org/en/v0.8.17/)
* Jouez avec les smarts contracts par défaut fournis avec Remix pour vous familiariser avec l'environnement.