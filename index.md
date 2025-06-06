---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

{:.logo}
![Optech Logo](/img/logos/optech-notext.png)

Bitcoin Optech helps Bitcoin users and businesses integrate scaling
technologies.

We provide [weekly newsletters][], a [podcast][], [case studies and
announcements][blog], [analyses of Bitcoin software and
services][matrix], [workshops][] and help to facilitate improved relations between
businesses
and the open source community.

[Learn more about us][about].

[workshops]: /en/workshops
[weekly newsletters]: /en/newsletters/
[blog]: /en/blog/
[podcast]: /en/podcast/
[about]: /en/about
[matrix]: /en/matrix/

{% assign posts_en = site.posts | where:"lang","en" %}

<h2>Recent newsletters, blog posts, and podcasts</h2>
<ul class="post-list">
  {%- for post in posts_en limit:5 -%}
  <li>
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    <span class="post-meta">{{ post.date | date: date_format }}</span>
    <h3>
      <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
      </a>
    </h3>
    {%- if site.show_excerpts -%}
      {{ post.excerpt }}
    {%- endif -%}
  </li>
  {%- endfor -%}
</ul>

<p class="rss-subscribe">View more <a href="/en/newsletters/">newsletters</a> or <a href="/en/blog">blog posts</a>. Learn about new content by subscribing via email or <a href="{{ "/feed.xml" | relative_url }}">RSS</a>.</p>

{% include newsletter-signup.html %}

{% include supporters.html %}
