---

layout: page
title: Projects
feature_image: "/Giacomo-Balla-Forze-di-paesaggio-+-cocomero-1917-1918-tempera-su-carta-intelata-1030x615.jpg"

---

- [MATREND](http://matrend.unicam.it) 
- [Lignani](https://progettolignani.netlify.com)
- [Da.Re.](http://dare-project.eu)


{% include video.html id="kcZ2k14EPvM" %}

- [T.R.E.E.](https://opencoesione.gov.it/it/progetti/5ma10458/)


  assign year_from = site.posts[-1].date | date: '%Y' 
    {% assign year_to   = site.time | date: '%Y' %}
    {% if year_from == nil or year_from == year_to %}
      {% assign year_string = year_from %}
    {% else %}
      {% assign from_to_seperator = site.data.strings.from_to_seperator | default: '-' %}
      {% assign year_string = year_from | append: '&nbsp;' | append: from_to_seperator | append: '&nbsp;' | append: year_to %}
    {% endif %}
    <p><small class="copyright">{{ site.copyright | markdownify | replace:'<!--copyyears-->',year_string | replace:'<p>','' | replace:'</p>','' }}</small></p>
