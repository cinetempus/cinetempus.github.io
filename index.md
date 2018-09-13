---
layout: main

---

<main class="home" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog" style="padding-top: 65px;">
    {% include flexslider-posts.html %}

<div cold-md="12">

<div align="center">

<h2 style="font-family: latin-100,arabic-100,sans-serif;color: #FFB03B;"> ÚLTIMAS PELICULAS AGREGADAS </h2>

</div>



</div>



<div id="grid" class="row">
    {% for post in site.posts %}
        <article class="box-item col-md-4" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">
            <div class="box">
            <div class="box-body">
                {% if post.image %}
                    <div class="cover">
                        {% include new-post-tag.html date=post.date %}
                        <a href="{{ post.url | prepend: site.baseurl }}" {%if isnewpost %}class="new-post"{% endif %}>
                            <img src="assets/img/placeholder.png" data-url="{{ post.image }}" class="preload">
                        </a>
                    </div>
                {% endif %}
                <div class="box-info">
                    <meta itemprop="datePublished" content="{{ post.date | date_to_xmlschema }}">
                    <time itemprop="datePublished" datetime="{{ post.date | date_to_xmlschema }}" class="date">
                        {% include date.html date=post.date %}
                    </time>
                    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
                        <h2 class="post-title" itemprop="name">
                            {{ post.title }}
                        </h2>
                    </a>
                </div>
            </div>
            </div>
        </article>
    {% endfor %}
</div>


</main>
