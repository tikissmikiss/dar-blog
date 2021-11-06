---
layout: post
title: "Proceso de renderizado de Jekyll"
categories: misc
img: "media/jekyll.svg"
author: José Herce
excerpt_separator: "<!--more-->"

---

<article class="article">
  <div class="improve right hide-on-mobiles"> <a data-proofer-ignore=""
      href="https://github.com/jekyll/jekyll/edit/master/docs/_docs/rendering-process.md"><i class="fa fa-pencil"></i>
      </a> </div>
  <!-- <h1 class="post-paragraph"> <span> <span>Proceso de renderizado de Jekyll</span> </span> </h1> -->
  <p class="post-paragraph"> <span> <span>Para cualquier sitio de Jekyll, una </span> </span><em> <span> <span>sesión de
          compilación</span> </span> </em> <span> <span> consta de fases discretas en el siguiente orden: </span>
    </span><em> <span> <span>configurar complementos, leer archivos de origen, ejecutar generadores, representar
          plantillas</span> </span> </em> <span> <span> y, finalmente, </span> </span><em> <span> <span>escribir
          archivos en el disco</span> </span> </em> <span> <span> .</span> </span> </p>
  <p class="post-paragraph"> <span> <span>Si bien las fases anteriores se explican por sí mismas, la única fase que
        justifica la disección es </span> </span><em> <span> <span>la fase de interpretación</span> </span> </em> <span>
      <span> .</span> </span> </p>
  <p class="post-paragraph"> <span> <span>La fase de renderizado se puede dividir en tres etapas opcionales. </span>
      <span class="">Cada archivo renderizado pasa por una o más de estas etapas según lo determinado por la cadena de
        contenido, el contenido inicial y la extensión del archivo. </span> <span>Las etapas son similares a una línea
        de montaje, y la </span> </span><em> <span> <span>salida</span> </span> </em> <span> <span> de una etapa es la
      </span> </span><em> <span> <span>entrada</span> </span> </em> <span> <span> para la etapa siguiente:</span>
    </span> </p>
<!--more-->
  <ul>
    <li><strong> <span> <span>Interpretación de expresiones de Liquid en el archivo</span> </span> </strong><br> <span>
        <span> Esta etapa evalúa las expresiones de Liquid en el archivo actual. </span> <span>De forma predeterminada,
          la interpretación es </span> </span><em> <span> <span>superficial</span> </span> </em> <span> <span> , en el
          sentido de que cualquier expresión de Liquid en la salida resultante no se interpreta más.
        </span> <span>Además, cualquier expresión de Liquid en la parte frontal del archivo no se modifica.</span>
      </span> </li>
    <li><strong> <span> <span>Liberar los convertidores</span> </span> </strong><br> <span> <span> Esta etapa invoca el
          convertidor asignado a la extensión del archivo actual y convierte la cadena de entrada.
        </span> <span>Esto es cuando Markdown se convierte en HTML y Sass / Scss en CSS o CoffeeScript en JavaScript,
          etc., etc.
          Dado que esta etapa está determinada por la extensión del archivo, Markdown o Sass dentro de un </span>
      </span><code class="language-plaintext highlighter-rouge">.html</code> <span> <span>archivo permanecerán
          intactos.</span> </span> </li>
    <li><strong> <span> <span>Completar los diseños</span> </span> </strong><br> <span> <span> En esta etapa, </span>
      </span><em> <span> <span>el archivo de origen</span> </span> </em> <span> <span> se considera renderizado y no se
          volverá a visitar. </span> <span>Sin embargo, en función de la extensión del archivo y, en consecuencia, en
          función de la materia </span> <span>inicial </span> <span>, se determina si tomar la </span> <span>cadena de
        </span> </span><em> <span> <span>salida</span> </span> </em> <span> <span> de la etapa anterior y colocarla en
          diseños o no. </span> <span>Mientras que la salida de los archivos Sass o los archivos CoffeeScript </span>
      </span><em> <span> <span>nunca se</span> </span> </em> <span> <span> colocan en un diseño, la salida de texto
          normal puede ir de cualquier manera según si se ha asignado un diseño
          a través de la página principal. </span> </span><br><br> <span> <span class=""> La colocación en diseños
          funciona de manera similar a cómo las muñecas rusas encierran a las más pequeñas
          dentro de sí mismas o cómo una ostra genera una perla: la salida convertida de la etapa anterior forma el
          núcleo y los diseños se </span><em> <span class="">renderizan</span> </em> <span class=""> sucesivamente
        </span> </span><em> <span></span> </em> <span> <span> por separado en el núcleo.</span> </span> </li>
  </ul>
</article>