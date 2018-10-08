---
layout   : course
permalink: generators/jekyll/opmaak/sass/
published: false
#
abbreviations:
  - computer
  - education
hyperlinks:
  - csse
  - technology
title: Sass
---
{%- include includes.md %}

> Zie ook
> ---
> - [Sass][]
> - [Sass Reference](http://sass-lang.com/documentation/file.SASS_REFERENCE.html)
> - [MarkSheet Sass Tutorial](http://marksheet.io/sass.html)
> - [Sass Guidelines](https://sass-guidelin.es)
> - [Jorie Clark's Intro to SASS](https://codepen.io/sasstantrum/post/intro-to-sass)
> - [Learn X in Y minutes: Sass](https://learnxinyminutes.com/docs/sass/)
{:.card.card-link}

Importeren
----------

> Zie ook
> ---
> - [Sass / Sass Basics / Import](http://sass-lang.com/guide#topic-5)
{:.card.card-link}

 - `@import`{:.k} `«naam-van-het-bestand»`{:.v} `;`
 - `@import`{:.k} `«naam-van-het-bestand»`{:.v} `,`  `«naam-van-het-ander-bestand»`{:.v} `;`

> Mappen & Bestanden
> ---
> - 1718-nmd2-code-jekyll/     **# Projectmap**{:.comment}
>   - _sass/                    *# Jekyll zoekt in deze map naar SCSS-bestanden*{:.comment}
>     - _main.scss              *# "main"*{:.comment}
>     - _style-guide.scss       *# "style-guide"*{:.comment}
>   - assets/
>     - css/
>       - app.scss              *# Dit bestand wordt ./assets/css/app.css*{:.comment}
{:.card.card-tree}

{% highlight scss linenos %}
---
---
@import
  "main",
  "style-guide";
{% endhighlight %}{:data-file="./assets/css/app.scss"}

In bovenstaand voorbeeld:

 - verwijst `"main"` naar het bestand `./_sass/_main.scss`;
 - verwijst `"style-guide"` naar het bestand `./_sass/_style-guide.scss`.

Geneste Regels *(Eng.: nested rules)*
-------------------------------------

> Zie ook
> ---
> - [Sass / Sass Basics / Nesting](http://sass-lang.com/guide#topic-3)
> - [Sass Reference / Nesting](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Nested_Rules)
{:.card.card-link}

Net zoals je HTML-element kan nesten[^nesting], zo kan je ook de CSS-regels nesten in SCSS.

[^nesting]: Nesten wil zeggen dat een HTML-element door een ander HTML-element omvat is.

> Tip
> ---
> Beperkt het nesten **tot maximaal 3 niveaus diep**. Meer niveaus maakt de code moeilijk leesbaar en de CSS-selectors trager.
{:.card.card-tip}

{% highlight scss linenos %}
{% include_relative _code/sass/nesten.00.scss %}
{% endhighlight %}{:data-file="nesten.scss"}

Resultaat:

{% highlight css linenos %}
{% include_relative _code/sass/nesten.00.css %}
{% endhighlight %}{:data-file="nesten.css"}

Sass Script
-----------

### Variabelen *(Eng.: variables)*

> Zie ook
> ---
> - [Sass / Sass Basics / Variables](http://sass-lang.com/guide#topic-2)
> - [Sass Documentation / Variables](http://sass-lang.com/documentation/#Variables)
> - [Sass Reference / Variables](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Variables_____variables_)
{:.card.card-link}

Variabelen beginnen met een `$` (dollarteken).

{% highlight scss linenos %}
{% include_relative _code/sass/variabelen.00.scss %}
{% endhighlight %}{:data-file="variabelen.scss"}

Resultaat:

{% highlight css linenos %}
{% include_relative _code/sass/variabelen.00.css %}
{% endhighlight %}{:data-file="variabelen.css"}

### Functies *(Eng.: functions)*

> Zie ook
> ---
> - [Sass Reference / Functions](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Variables_____variables_)
> - [Sass Documentation / Script / Functions](http://sass-lang.com/documentation/Sass/Script/Functions.html)
{:.card.card-link}

Mixins
------

> Zie ook
> ---
> - [Sass Reference / Mixin Directives](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Mixin_Directives__mixins)
{:.card.card-link}

Een mixin groepeert CSS-code, en heeft bovendien de mogelijkheid om een of meer variabelen mee te geven.

{% highlight scss linenos %}
{% include_relative _code/sass/mixins.00.scss %}
{% endhighlight %}{:data-file="mixins.scss"}

Resultaat:

{% highlight css linenos %}
{% include_relative _code/sass/mixins.00.css %}
{% endhighlight %}{:data-file="mixins.css"}

Control Directives & Expressions
--------------------------------

> Zie ook
> ---
> - [Sass Reference / Control Directives](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#Control_Directives___Expressions)
{:.card.card-link}

### Conditioneel

 - `if(` … `)`
 - `@if` … `{` … `}`
 - `@if` … `{` … `} else {` … `}`
 - `@if` … `{` … `} else if` … `{` … `}`
 - `@if` … `{` … `} else if` … `{` … `} else {` … `}`

### Lussen *(Eng.: loops)* 

 - `@for` … `from` … `trough` … `{` … `}`
 - `@each` … `in` … `{` … `}`
 - `@while` … `in` … `{` … `}`

{% highlight scss linenos %}
{% include_relative _code/sass/lussen.00.scss %}
{% endhighlight %}{:data-file="lussen.scss"}

Resultaat:

{% highlight css linenos %}
{% include_relative _code/sass/lussen.00.css %}
{% endhighlight %}{:data-file="lussen.css"}

Overerving *(Eng.: inheritance)*
--------------------------------

{% highlight scss linenos %}
{% include_relative _code/sass/overerving.00.scss %}
{% endhighlight %}{:data-file="overerving.scss"}

Resultaat:

{% highlight css linenos %}
{% include_relative _code/sass/overerving.00.css %}
{% endhighlight %}{:data-file="overerving.css"}