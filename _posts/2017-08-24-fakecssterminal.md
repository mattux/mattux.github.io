---
layout: post
published: true
title: Finto terminale in HTML+CSS
comments: true
tags:
- webdeveloping
---

Stavo guardando la documentazione di [jrnl](http://jrnl.sh/) quando mi sono chiesto "Ma quale sarà un modo pigro di fare un finto terminale in HTML e CSS?".

Partiamo dal risultato. Dopo un mezzo pomeriggio di smanettaggio sono arrivato a questo:

![fake Terminal]({{ site.url }}/assets/fake_terminal.png)

L'HTML è veramente semplice ed essenziale:

{% highlight html linenos  %}
<html>
  <head>
    <link rel="stylesheet" href="shterminal.css" />
  </head>

  <body>

  <div class="shterm">
    <div id="winbuttons">
      <span>○</span>
      <span>○</span>
      <span>◉</span>
    </div>

    <div class="shcode">
      <pre class="caret"><code>echo "Hello World"</code></pre>
      <pre><code>Hello World</code></pre>
      <pre class="caret"><code>echo "tacocat spelled backwards is tacocat"</code></pre>
      <pre><code>tacocat spelled backwards is tacocat</code></pre>
    </div>
  </div>

  </body>
</html>

{% endhighlight %}

La parte divertente è nel CSS. Allo scopo di evitare di fare troppi div, per definire la _decorazione della finestra_ ho usato lo pseudo elemento `::before`.
Prendo la definizione da una fonte autorevolissima, l'[MDN](https://developer.mozilla.org/it/):

> In CSS, **::before** creates a pseudo-element that is the first child of the selected element. It is often used to add cosmetic content to an element with the content property. It is inline by default. ([::before - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/::before))

Uno _pseudo elemento_ è una keyword che ci consente di definire lo stile di una specifica parte di un particolare elemento.

Ecco come ho definito lo stile della decorazione della finta finestra di terminale:

{% highlight css lineos %}
div.shterm::before {
  content: 'Terminal';
  font-size: 16px;
  text-align: center;
  display: block;
  border: 1px solid #ddd;
  border-bottom: 1px solid #222;
  box-shadow: 0px 5px 8px -7px #000;
  border-top-left-radius: 2px;
  border-top-right-radius: 2px;
  background: -moz-linear-gradient(bottom, #eee 0%, #bbb 100%);
  background: -webkit-linear-gradient(bottom, #eee 0%, #bbb 100%);
  background: linear-gradient(to bottom, #eee 0%, #bbb 100%);
}
{% endhighlight %}

Spesso si usa `::before` in tandem con la direttiva `content`. Ad esempio qui simulo il prompt così:

{% highlight css lineos %}
div.shcode pre.caret::before {
  content: '[user@machine ~]$ ';
  font-weight:bold;
}
{% endhighlight %}

A [questo link](https://gist.github.com/mattux/63e50d4378a271107c2a3a19f6bb23a5) il gist completo.

A pigrizia non saprei, ma a semplicità direi che ci siamo, dai.
