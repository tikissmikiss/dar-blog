---
layout: post
title: "Blog elaborado mediante la herramienta Jekyll"
categories: misc
img: "media/jekyll.svg"
author: José Herce
excerpt_separator: "<!--more-->"
---


<p class="post-paragraph">
    <a href="https://jekyllrb.com/"><img class="excerpt-image" src="{{ page.img | relative_url }}" width="30%" alt="logo Jekyll" /></a>
</p>

<p class="post-paragraph">
    Para la elaboración de este blog se ha elegido usar la herramienta <a href="https://jekyllrb.com/"> <em>Jekyll</em></a>.
</p>

<p class="post-paragraph">
    <em>Jekyll</em> es una herramienta que permite generar sitios estáticos. Toma texto escrito en un lenguaje de marcado
    como puede ser <em>html</em> o <em>markdown</em> y utiliza layouts para crear un sitio web estático. Permite ajustar la
    apariencia del sitio, las direcciones URL, los datos mostrados en la página y mucho más.
</p>

<p class="post-paragraph">
    <em>Jekyll</em> está escrito en <em>Ruby</em>. Por lo que lo primero que se necesita es tener <em>Ruby</em> instalado. Después de tener
    <em>Ruby</em> instalado podemos instalar <em>Jekyll</em> mediante su administrador de paquetes llamado <em>RubyGems</em>.
</p>

<!--more-->

<p class="post-paragraph">
    <ol class="post-paragraph">Para ello:
        <li>
            Instalar los <a href="https://jekyllrb.com/docs/ruby-101/#gems">gems</a> de <em>Jekyll</em> y <em>Bundler</em>.
        </li>
        <div class="post-code-cmd">gem install jekyll bundler</div>
        <li>
            Crear un nuevo sitio de <em>Jekyll</em> en ./myblog.
        </li>
        <div class="post-code-cmd">jekyll new myblog</div>
        <li>
            Cambiar al nuevo directorio.
        </li>
        <div class="post-code-cmd">cd myblog</div>
        <li>
            Construir el sitio y ponerlo a disposición en un servidor local.
        </li>
        <div class="post-code-cmd">bundle exec jekyll serve</div>
        <li>
            Abrir el navegador en <a href="http://localhost:4000">http://localhost:4000</a>
        </li>
    </ol>
</p>
