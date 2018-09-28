---
layout: main

---

<main class="home" id="post" role="main" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog" style="padding-top: 65px;">
    {% include flexslider-posts.html %}

<div cold-md="12">

<div align="center">

<h2 class="top_h2"> ÚLTIMAS PELICULAS AGREGADAS </h2>

</div>



</div>



<!-- banner-bottom -->
<div class="banner-bottom">
		<div class="container">
			<div class="w3_agile_banner_bottom_grid">
				<div id="owl-demo" class="owl-carousel owl-theme">
				     {% for post in site.posts %}
					 	{% if post.nuevo=='new_peliculas' %}
						 <div class="item">
							<div class="w3l-movie-gride-agile w3l-movie-gride-agile1">
								<a id="load" href="{{ post.url | prepend: site.baseurl }}" class="hvr-shutter-out-horizontal"><img src="{{ post.image_carousel }}" title="album-name" class="img-responsive" alt=" " />
									<div class="w3l-action-icon"><i class="fa fa-play-circle" aria-hidden="true"></i></div>
								</a>
								<div class="mid-1 agileits_w3layouts_mid_1_home">
									<div class="w3l-movie-text">
										<h6><a id="load" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h6>							
									</div>
									<div class="mid-2 agile_mid_2_home">
										<p>{{ post.anio }}</p>
										<div class="block-stars">
											<ul class="w3l-ratings">
												<li><a href="#"><i class="fa fa-star" aria-hidden="true"></i></a></li>
												<li><a href="#"><i class="fa fa-star" aria-hidden="true"></i></a></li>
												<li><a href="#"><i class="fa fa-star" aria-hidden="true"></i></a></li>
												<li><a href="#"><i class="fa fa-star" aria-hidden="true"></i></a></li>
												<li><a href="#"><i class="fa fa-star-half-o" aria-hidden="true"></i></a></li>
											</ul>
										</div>
										<div class="clearfix"></div>
									</div>
								</div>
								<div class="ribben">
									<p>NEW</p>
								</div>
							</div>
						</div>
						{%endif%}
					 {% endfor %}
				</div>
			</div>			
		</div>
</div>
<!-- //banner-bottom -->





<div id="grid" class="row">
    {% for post in site.posts %}
        <article class="box-item col-md-3 col-xs-6 col-lg-3" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">
            <div class="box">
            <div class="box-body">
                {% if post.image %}
                    <div class="cover">
                        {% include new-post-tag.html date=post.date %}
                        <a id="load" href="{{ post.url | prepend: site.baseurl }}" {%if isnewpost %}class="new-post"{% endif %}>
                            <img src="https://res.cloudinary.com/imbriitneysam/image/upload/v1537239672/placeholder-min.png" data-url="{{ post.image }}" class="preload">
                        </a>
                    </div>
                {% endif %}
                <div class="box-info">
                    <meta itemprop="datePublished" content="{{ post.date | date_to_xmlschema }}">
                    <time itemprop="datePublished" datetime="{{ post.date | date_to_xmlschema }}" class="date">
                        {% include date.html date=post.date %}
                    </time>
					<div class="w3l-movie-text">
						<h6>
							<a id="load" class="post-link" href="{{ post.url | prepend: site.baseurl }}">
									{{ post.title }}
							</a>
						</h6>
						<span class="category">
						<a href="{{ site.url }}{{ site.baseurl }}/category/{{ post.category }}">
							<span>{{ post.category }}</span>
						</a>
					</span>
					</div>
                </div>
            </div>
            </div>
        </article>
    {% endfor %}

 {% for category in site.categories %}
   <ul>
    {% for posts in category %}
      {% for post in posts %}
	    {% if post.category2 =='Peliculas' %}
		 <li><a name="{{ category | first }}">{{ category | first }}</a></li>
         <li><a href="{{ post.url }}">{{ post.title }}</a></li>
		 {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  
{% endfor %}
</div>


</main>
