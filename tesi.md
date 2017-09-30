---
layout: page
title: Tesi
---

{% for tesi in site.data.tesi %}

---

{% if tesi.link %}

## [{{ tesi.title }}]({{ tesi.link }})

{% else %}

## {{tesi.title}}

{% endif %}

**{{ tesi.author }}**

*{{ tesi.period }}*

    {% for sup in tesi.supervisors %}
Supervisor: [{{ sup.name }}]({{ sup.url }})
    {% endfor %}

{% if tesi.host %}
Hosted by {{ tesi.host }}
{% endif %}

{% if tesi.pubblications %}
### Publications
    {% for pub in tesi.pubblications %}

    {% if pub.link %}
0. [{{ pub.title }}]({{ pub.link }})
    {% else %}
0. {{ pub.title }}
    {% endif %}

    {% endfor %}

{% endif %}

{% endfor %}