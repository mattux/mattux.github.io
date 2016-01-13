---
layout: post
published: true
title: Jekyll e i sistemi di commenti
tags:
- jekyll
- blog
---

In un blog i commenti costituiscono una componente che ha un peso non trascurabile. I CMS tipicamente offrono *out of the box* un sistema di commenti, mentre i generatori di siti **statici** come *Jekyll* solitamente ne sono sprovvisti, essendo una funzionalità per sua natura **dinamica** (anche se con un po' di inventiva si possono generare in maniera statica). Integrarne uno diventa quindi un problema perché è necessario l'utilizzo di codice dedicato e bisogna memorizzare i dati relativi ai commenti stessi.
Non scordiamoci poi la gestione dello *spam*.
Anche se qui non ho per il momento intenzione di usarne uno, spinto dalla curiosità ho considerato alcune opzioni.

### [Disqus](http://disqus.com/)
È la soluzione più adottata da chi ha un blog Jekyll. Tutti i dati sono memorizzati sui server Disqus. Purtroppo non è software libero, ma è la maniera più comoda.

### [HashOver](http://tildehash.com/?page=hashover)
Interessante, con un buon numero di [funzionalità](https://github.com/jacobwb/hashover-next#notable-features), ma usa PHP. Github Pages non supporta l'esecuzione di PHP.

### [Isso](https://posativ.org/isso/)
Supporta Markdown, usa SQLite e Python. Non male e adatto a siti con piccole quantità di commenti, ma non va nella direzione che interessa a me. E inoltre, se Pages non supporta PHP, figuriamoci se supporta qualche tipo di database o Python.

### [StaticComments plugin](http://theshed.hezmatt.org/jekyll-static-comments/)
Ingegnosa soluzione per avere un sistema di commenti statico. Usa PHP e Ruby. Se ho capito come funziona, bisogna aggiungere una directory `_comment` atta a contenere dei file con le descrizioni [YAML](http://yaml.org/ "YAML") dei commenti; quando un utente lascia un commento, uno script PHP mi manda una email e, se non è spam, in base al suo contenuto devo generare il file con lo YAML e lanciare uno script Ruby che genera i commenti. Applicabile solo se non sei pigro e hai un bassissimo volume di commenti.

### [Sfruttare l'issue tracker di GitHub](http://ivanzuzak.info/2011/02/18/github-hosted-comments-for-github-hosted-blogs.html)
A dir poco geniale. Richiede di avere un account di Github per commentare, ma poco male. [Qualcuno](https://github.com/izuzak/izuzak.github.com/issues/12#issuecomment-71345363) ha aperto un [repo apposito](https://github.com/wireddown/ghpages-ghcomments). Finora la migliore soluzione che ho visto.

Se mai dovessi dotare il blog di un sistema di commenti, potrebbe essere quest'ultimo oppure, non proprio entusiasticamente, Disqus.
