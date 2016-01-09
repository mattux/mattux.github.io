---
layout: post
published: true
title: Jekyll e i sistemi di commenti
tags:
- jekyll
- blog
---

Uno dei problemi comuni quando si crea un blog con un *generatore di siti statici* è integrare un sistema di commenti, che è una funzionalità intrinsecamente *dinamica*.
In ogni caso non ho per il momento intenzione di dotare questo blog di commenti, ma spinto dalla curiosità ho considerato alcune opzioni.

### [Disqus](http://disqus.com/)
È la soluzione più adottata da chi ha un blog Jekyll, ma tutti i dati sono memorizzati sui server Disqus. Purtroppo non è software libero, ma bisogna apprezzarne la comodità.

### [HashOver](http://tildehash.com/?page=hashover)
Interessante, con un buon numero di [funzionalità](https://github.com/jacobwb/hashover-next#notable-features), ma usa PHP. Github Pages non supporta l'esecuzione di PHP.

### [Isso](https://posativ.org/isso/)
Supporta Markdown, usa SQLite e Python. Non male e adatto a siti con piccole quantità di commenti, ma non va nella direzione che interessa a me.

### [StaticComments plugin](http://theshed.hezmatt.org/jekyll-static-comments/)
Ingegnoso. Usa PHP e Ruby. Se ho capito come funziona, bisogna aggiungere una directory `_comment` atta a contenere dei file con le descrizioni [YAML](http://yaml.org/ "YAML") dei commenti; quando un utente lascia un commento, uno script PHP mi manda una email e, se non è spam, in base al suo contenuto devo generare il file con lo YAML e lanciare uno script Ruby che genera i commenti. È faticoso solo a scriverlo.

### [Sfruttare l'issue tracker di GitHub](http://ivanzuzak.info/2011/02/18/github-hosted-comments-for-github-hosted-blogs.html)
A dir poco geniale. Richiede di avere un account di Github per commentare, ma poco male. [Qualcuno](https://github.com/izuzak/izuzak.github.com/issues/12#issuecomment-71345363) ha aperto un [repo apposito](https://github.com/wireddown/ghpages-ghcomments). Finora la migliore soluzione che ho visto.

Se mai dovessi inserire un sistema di commenti, potrebbe essere quest'ultimo.
