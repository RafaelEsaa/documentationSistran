---
layout: page
title: Inicio
permalink: docs/arquitectura/index
---

# Arquitectura

Welcome to the {{ site.title }} Documentation pages! Here you can quickly jump to a 
particular page.

<div class="section-index">
    <hr class="panel-line">
    {% for docs in site.data.arquitectura %}
        <div class="entry">
            <h5>
                <a href="{{docs.url}}">{{docs.title}}</a>
            </h5>
        </div>
    {% endfor %}
</div>
