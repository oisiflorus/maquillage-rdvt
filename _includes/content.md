<aside class="blobTools">
    {% if site.github.pages_hostname == "github.io" %}
    <a href={{ site.github.repository_url }}/blob/{{ site.github.source.branch }}/{{ page.path }} title="Voir sur Github" class="blobGhLink tooltip"></a>
    <a href={{ site.github.repository_url }}/edit/{{ site.github.source.branch }}/{{ page.path }} title="Éditer sur Github" class="blobGhEdit tooltip"></a>
    {% elsif site.gitlab.pages_hostname == "gitlab.io" %}
    <a href={{ site.gitlab.repository_url }}/blob/master/{{ page.path }} title="Voir sur Gitlab" class="blobGhLink tooltip"></a>
    <a href={{ site.gitlab.repository_url }}/edit/master/{{ page.path }} title="Éditer sur Gitlab" class="blobGhEdit tooltip"></a>
    {% endif %}

    <a href="#top" class="blobPageTop">Haut de page</a>
</aside>

<article class=blobContent data-title=content>
    <h1>{{ page.nom }}</h1>
    <div class=metas>
        <ul>
            {% if  page.type %}
                <li>Type : {{ page.type }}</li>
            {% endif %}
            {% if  page.par %}
                <li>Par : <a href="https://github.com/{{ page.par }}">{{ page.par }}</a></li> 
            {% endif %}
            {% if page.adresse %}
                <li>Adresse : 
                {% if page.osm %}
                    <a href="https://www.openstreetmap.org/node/{{ page.osm }}">
                {% else %}
                    <a href="https://www.openstreetmap.org/search?query={{ page.adresse }}, Montréal">
                {% endif %}
                    {{ page.adresse }}</a>
                    </li>
            {% endif %}
            {% if  page.metro %}
                <li>Métro : {{ page.metro }}</li> 
            {% endif %}
            {% if  page.site %}
                <li>Site : <a href="{{ page.site }}">{{ page.site }}</a></li> 
            {% endif %}
        </ul>
    </div>

    {{ content }}

    {% if page.tags %}
    <div class=tags>
        <ul>
            {% for tag in page.tags %}
            <li>{{ tag }}</li>
            {% endfor %}
        </ul>
    </div>
    {% endif %}
</article>