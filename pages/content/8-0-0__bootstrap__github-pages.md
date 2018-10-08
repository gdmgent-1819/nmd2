---
layout   : course
permalink: bootstrap/github-pages/
published: false
#
title     : GitHub Pages
title_long: "GitHub Pages, Jekyll & Bootstrap 4"
---

> Mappen & Bestanden
> ---
> - mijn-home-map/           **# De Home-map (PowerShell-opdracht `~`)**{:.comment}
>   - Code/                   *# De Code-map (PowerShell-opdracht `c`)*{:.comment}
>     - code-nmd2-ghpages/    *# De projectmap*{:.comment}
{:.card.card-tree}

{% highlight posh %}
PS> c
PS> mkdir code-nmd2-ghpages
PS> cd mijn-ghpages-project
PS> git init
PS> mkdir _vendor
PS> cd _vendor
PS> git submodule add https://github.com/twbs/bootstrap
PS> cd bootstrap
PS> git checkout v4.0.0-beta
PS> cd ..
PS> cd ..
PS> touch Gemfile
PS> code .
{% endhighlight %}

{% highlight rb linenos %}
source 'http://rubygems.org'
gem 'github-pages'
gem 'wdm', '>= 0.1.1' if Gem.win_platform?
{% endhighlight %}{:data-file="~/Code/code-nmd2-ghpages/Gemfile"}

> Mappen & Bestanden
> ---
> - code-nmd2-ghpages/    *# De projectmap*{:.comment}
>   - _sass/
>     - _main.scss
>   - _vendor/
>     - bootstrap/
>   - assets/
>     - css/
>       - app.scss
>   - _config.yml
>   - index.html
{:.card.card-tree}

{% highlight yml linenos %}

{% endhighlight %}{:data-file="~/Code/code-nmd2-ghpages/_config.yml"}

