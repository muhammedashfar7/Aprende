---
layout: page
title: Book Reviews
description: "My awesome reading notes. Some are in-depth, some are short, some include quotes. All are for me."
---
<div class="home">
	<div class="call-out"><h1>Book Reviews</h1>
	    Here are notes I've taken on books I've read. Some are in-depth, some are short, some include quotes. I've included ratings and genres for future sorting.
	</div>
  <div class="posts">

  {% assign reviews = site.book_reviews | sort: "date" | reverse %}
  {% for review in reviews %}
  	<div class="post-teaser">
  			  <div class="book_info">
				  {% if review.cover %}<div class="book_cover"><a href="{{ review.url | prepend: site.baseurl }}"><img src="/img/{{ review.cover }}" alt="Book cover for {{ review.title }}" /></a></div>{% endif %}
				  <div class="book_meta">
					  <h3><em><a href="{{ review.url | prepend: site.baseurl }}">{{ review.title }}</a></em></h3>
					  <p>Author: {{ review.author }}</p>
					  <p>Rating:  <span class="stars-container stars-{{ review.stars | times:20 | round: 0 }}" title="{{ review.stars }}/5">★★★★★</span></p>
					  <p>Genre: {{ review.category }}</p>
					  <p>Themes: {% assign first = true %}{% for tag in review.tags %}{% unless first %},{% endunless %} {{ tag }}{% assign first = false %}{% endfor %}</p>
					  <p>Finished: {{ review.date | date: "%B %-d, %Y" }}</p>
					  {% if review.excerpt %}<p>{{ review.excerpt }}</p>{% endif %}
					  <a class="button" href="{{ review.url | prepend: site.baseurl }}">Read full notes</a>
				  </div>
			  </div>

  	</div>
  {% endfor %}

 </div>