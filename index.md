---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
Courses:

{% for node in site.pages %}
  {% if node.course %} 
    {% if node.module %}
    {% else %}
<a href="{{site.baseurl}}{{node.url}}">{{node.course}}</a>
    {% endif %}
  {% endif %}
{% endfor %}