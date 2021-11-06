---
layout: post
title: "Algunas posibilidades que ofrece Liquid"
# date: 2021-10-30 13:06:52 +0200
img: "media/liquid.png"
author: José Herce
txt1: "{{ page.open-keys}} and {{ page.close-keys}}."
open-keys: "{{ "
close-keys: " }}"
open-key: "{"
close-key: "}"
excerpt_separator: "<!--more-->"
---

<div class="liquid article">

<p class="post-paragraph">
    <a href="https://shopify.github.io/liquid/"><img class="excerpt-image" src="{{ page.img | relative_url }}" width="30%" alt="logo Jekyll" /></a>
</p>

<p class="post-paragraph">
    <a href="https://shopify.github.io/liquid/"><em>Liquid</em></a> es un lenguaje de código abierto para creación de
    plantillas. Está escrito en <em>Ruby</em> y fue desarrollado por <a href="https://www.shopify.com/">Shopify</a>. Se
    utiliza para cargar contenido de manera dinámica durante el desarrollo de páginas web.
</p>

<p class="post-paragraph">
    <em>Liquid</em> utiliza una combinación de <a href="#objects"><strong>objetos</strong></a>, <a href="#tags"><strong>etiquetas</strong></a> y <a href="#filters"><strong>filtros</strong></a> para crear una plantilla que permite mostrar
    contenido de manera dinámica.
</p>

<!--more-->

<h2 class="post-paragraph" id="objects">Objetos</h2>

<p class="post-paragraph">
    Los <strong>objetos</strong> contienen el contenido que Liquid muestra en una página. Los objetos y las variables se muestran cuando están encerrados
    entre llaves dobles: <code class="language-plaintext highlighter-rouge">{{ page.open-keys }}</code>and<code class="language-plaintext highlighter-rouge">{{ page.close-keys }}</code>
</p>

<p class="post-paragraph code-label-liquid">Input</p>
<p class="post-code-liquid post-paragraph">
    <code class="highlight">{{ page.open-keys}}<span class="nv">page</span>.<span class="nv">title</span>{{ page.close-keys}}</code>
</p>

<p class="code-label-liquid ">Output</p>
<p class="post-code-liquid ">
    <code>Introduction</code>
</p>

<p class="post-paragraph">
     title del objeto page, que contiene el texto Introduction
    En este caso, Liquid representa el contenido de la propiedad <code class="language-plaintext highlighter-rouge">title</code>
    del objeto <code class="language-plaintext highlighter-rouge">page</code>, que contiene el texto <code
        class="language-plaintext highlighter-rouge">Introduction</code>.</p>

<h2 class="post-paragraph" id="tags">Etiquetas</h2>

<p class="post-paragraph">
Las <strong>Etiquetas</strong> crean la lógica y el flujo de control de las plantillas. Los delimitadores de llaves con porcentaje que rodean texto <code class="language-plaintext highlighter-rouge">{{ page.open-key }}%</code> y <code
        class="language-plaintext highlighter-rouge">%{{ page.close-key }}</code>, no producen ningún resultado visible cuando se renderiza la plantilla. Esto le permite asignar variables y crear condiciones o bucles sin mostrar ninguna lógica líquida en la página.
</p>

<p class="code-label-liquid">Input</p>
<div class="post-code-liquid highlighter-rouge">
    <div class="highlight">
        <pre class="highlight"><code><span class="p">{{ page.open-key }}%</span><span class="w"> </span><span class="kr">if</span><span class="w"> </span><span class="nv">user</span><span class="w"> </span><span class="p">%{{ page.close-key }}</span>
  Hello <span class="p">{{ page.open-keys}}</span><span class="w"> </span><span class="nv">user</span><span class="p">.</span><span class="nv">name</span><span class="w"> </span><span class="p">{{ page.close-keys }}</span>!
<span class="p">{{ page.open-key }}%</span><span class="w"> </span><span class="kr">endif</span><span class="w"> </span><span class="p">%{{ page.close-key }}</span>
</code></pre>
    </div>
</div>

<p class="code-label-liquid">Output</p>
<p class="post-code-liquid post-paragraph">
    <code>Hello Adam!</code>
</p>

<p class="post-paragraph">
Las etiquetas se pueden clasificar en varios tipos:</p>

<ul class="post-paragraph">
    <li><a href="https://shopify.github.io/liquid/tags/control-flow/">Control de flujo</a></li>
    <li><a href="https://shopify.github.io/liquid/tags/iteration/">Iteración</a></li>
    <li><a href="https://shopify.github.io/liquid/tags/template/">Plantilla</a></li>
    <li><a href="https://shopify.github.io/liquid/tags/variable/">Asignación variable</a></li>
</ul>

<p class="post-paragraph">
Puede leer más sobre cada tipo de etiqueta en sus respectivas secciones.</p>

<h2 class="post-paragraph" id="filters">Filtros</h2>

<p class="post-paragraph">
Los <strong>Filtros</strong> cambian la salida de un objeto o variable Liquid. Se utilizan dentro de llaves dobles <code class="language-plaintext highlighter-rouge">{{ page.open-keys }}{{ page.close-keys }}</code> junto a una <a href="https://shopify.github.io/liquid/tags/variable/">asignación de variables</a>, y
están separadas por un carácter de barra vertical <code
        class="language-plaintext highlighter-rouge">|</code>.</p>

<p class="code-label-liquid">Input</p>
<div class="post-code-liquid highlighter-rouge">
    <div class="highlight">
        <pre class="highlight"><code><span class="p">{{ page.open-keys}}</span><span class="w"> </span><span class="s2">"/my/fancy/url"</span><span class="w"> </span><span class="p">|</span><span class="w"> </span><span class="nf">append</span><span class="p">:</span><span class="w"> </span><span class="s2">".html"</span><span class="w"> </span><span class="p">{{ page.close-keys }}</span>
</code></pre>
    </div>
</div>

<p class="code-label-liquid">Output</p>
<p class="post-code-liquid post-paragraph">
    <code>/my/fancy/url.html</code>
</p>

<p class="post-paragraph">
Se pueden usar varios filtros en una salida y se aplican de izquierda a derecha.
</p>

<p class="code-label-liquid">Input</p>
<div class="post-code-liquid highlighter-rouge">
    <div class="highlight">
        <pre class="highlight"><code><span class="p">{{ page.open-keys}}</span><span class="w"> </span><span class="s2">"adam!"</span><span class="w"> </span><span class="p">|</span><span class="w"> </span><span class="nf">capitalize</span><span class="w"> </span><span class="p">|</span><span class="w"> </span><span class="nf">prepend</span><span class="p">:</span><span class="w"> </span><span class="s2">"Hello "</span><span class="w"> </span><span class="p">{{ page.close-keys }}</span>
</code></pre>
    </div>
</div>

<p class="code-label-liquid">Output</p>
<p class="post-code-liquid post-paragraph">
    <code>Hello Adam!</code>
</p>
</div>

