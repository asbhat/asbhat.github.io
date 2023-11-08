---
layout: slate
---

{% comment %}

    index.md

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

## About ##

{% include linkedin_profile_badge.html vanity="aditya-bhat-829b4720" name="Aditya Bhat" %}

{% comment %} TODO add a CV link / document {% endcomment %}

<a href="https://www.mobygames.com/developer/sheet/view/developerId,1092386" title="Aditya on MobyGames">
    <img src="/assets/images/mobygames-logo.png" style="height: 50px">
</a>

## iOS Applications ##
{% include repo_list_start.html %}
{% include repo_card.html name="RiceballDb" github_link="" website_link="/riceballdb/index.html" description="<i>Currently in beta.</i><br>Discover, save, and track your consumption of media." %}
{% include repo_list_end.html %}

## Sample Game Slices ##
{% include repo_list_start.html %}
{% for game_slice in site.data.game_slices %}
    {% include repo_card.html name=game_slice.name github_link=game_slice.github_link website_link=game_slice.website_link description=game_slice.description %}
{% endfor %}
{% include repo_list_end.html %}

<br><br>
## [Old Projects](/oldprojects/index.html) ##

{% comment %} TODO include Contributions to Other's Projects section {% endcomment %}
{% comment %}   have it link to filtered contributions by me {% endcomment %}
