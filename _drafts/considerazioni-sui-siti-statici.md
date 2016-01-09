---
layout: post
published: true
title: Considerazioni sui siti statici
tags:
- web
- blog
- jekyll
---

Un tempo erano i siti statici: niente database, niente Javascript né PHP, né niente di simile, solo semplici ipertesti.

Arrivarono poi i database, Javascript, PHP e i loro simili. E furono i siti dinamici. E con loro i CMS.

(Ok, ho semplificato parecchio)

Oggi, nello sfavillante 2016, fa quasi figo dire:

> Io mica ho usato un CMS, l'ho fatto statico.

Ok.

I siti statici hanno sostanzialmente due vantaggi:

- meno codice che gira, meno codice exploitabile e quindi sulla carta più sicurezza;
- pagine generate una volta anziché ogni qualvolta un utente la visita, quindi il sito è più veloce.

E grazie al razzo.

Anche i principali svantaggi sono due:

- tipicamente manca una GUI per la gestione del sito;
- se vuoi, dato che il mondo non è "o bianco o nero", un po' di dinamicità (soprattutto lato server) ti pigliano i sensi di colpa, oltre ad eventuali difficoltà tecniche.

Cionondimeno spesso sono la soluzione migliore e siccome *"fare un sito statico scrivendo tutto il codice HTML a mano anche no"*, sono nati i **generatori di siti statici**.

Come ho già scritto qualche post fa, questo blog usa [Jekyll](http://jekyllrb.com/ "Jekyll") ed è hostato sulle [Github Pages](https://pages.github.com/ "Github Pages").
Una cosa che hanno molto spesso i blog, sono i **commenti** e quando questo blog era su *Blogger*, ce li aveva mentre ora no. Questo perché il sito è *statico*, mentre i commenti sono una componente di solito *dinamica* e che richiede inevitabilmente del codice lato server.
