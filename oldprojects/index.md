---
layout: slate
---

{% comment %}

    oldprojects/index.md

    Copyright © 2023 Aditya Bhat. All rights reserved.
    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

{% endcomment %}

{% comment %} Create an array of capitalized, unique, and sorted tags {% endcomment %}
{% assign all_tags = "" | split: "" %}
{% for repo in site.data.old.repositories %}
    {% for tag in repo.tags %}
        {% capture cap_tag %}{{tag | capitalize}}{% endcapture %}
        {% assign all_tags = all_tags | push: cap_tag %}
    {% endfor %}
{% endfor %}
{% assign all_uniq_tags = all_tags | uniq | sort %}

{% comment %} Create the string and links for tag/header navigation {% endcomment %}
{% assign tag_nav = "" | split: "" %}
{% for tag in all_uniq_tags %}
    {% capture tag_link %}<a href="#{{tag | slugify}}">{{tag}}</a>{% endcapture %}
    {% assign tag_nav = tag_nav | push: tag_link %}
{% endfor %}

{% assign sorted_repos = site.data.old.repositories | sort: "name" %}

## Old Projects ##
{{tag_nav | join: " &#124; "}}

{% for tag in all_uniq_tags %}
### {{tag}} ### {#{{tag|slugify}}}

{% include repo_list_start.html %}
{% for repo in sorted_repos %}
    {% if repo.tags contains tag %}
        {% assign github_repo = site.github.public_repositories | where: "name", repo.name | first %}
        {% include repo_card.html name=github_repo.name github_link=github_repo.html_url website_link=github_repo.homepage description=github_repo.description %}
    {% endif %}
{% endfor %}
{% include repo_list_end.html %}

{% endfor %}

{% comment %} TODO include Contributions to Other's Projects section {% endcomment %}
{% comment %}   have it link to filtered contributions by me {% endcomment %}
