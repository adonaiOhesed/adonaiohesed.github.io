---
layout: about
author: Hyo-Eun Choi
title: About
key: page-about
---
{% assign author = site.data.authors[page.author] %}

<section class="cv-author-profile" itemprop="author" itemscope itemtype="http://schema.org/Person">
	<div class="author-info">
	<img src="{{author.picture}}" style="width:330px; border-radius: 20%;">
		<h1 class="author-title" itemprop="name" style="border-bottom-width:0; margin:0;">{{author.name}}</h1>
		{% if author.bio %} <h2 class="author-bio" itemprop="description" style="border-bottom-width:0; margin:0;">{{author.bio}}</h2> {% endif %}
		<div class="author-meta">
			{%  if author.email %}<a href="mailto:{{ author.email }}" itemprop="email" class="icon-mail">Mail</a>{% endif %}
			{%  if author.twitter %}<a href="https://twitter.com/{{ author.twitter }}" itemprop="sameAs" class="icon-twitter">Twitter</a> {% endif %}
			{%  if author.linkedin %}<a href="https://www.linkedin.com/in/{{ author.linkedin }}" itemprop="sameAs" class="icon-linkedin">LinkedIn</a> {% endif %}
			{%  if author.xing %}<a href="https://www.xing.com/profile/{{ author.xing }}" itemprop="sameAs" class="icon-xing">Xing</a> {% endif %}

			{%  if author.github %}<a href="https://github.com/{{ author.github }}" itemprop="sameAs" class="icon-github">GitHub</a> {% endif %}
			{%  if author.stackoverflow %}<a href="http://stackoverflow.com/users/{{ author.stackoverflow }}" itemprop="sameAs" class="icon-stackoverflow">StackOverflow</a> {% endif %}

			{%  if author.facebook %}<a href="https://www.facebook.com/{{ author.facebook }}" itemprop="sameAs" class="icon-facebook">Facebook</a> {% endif %}
			{%  if author.gplus %}<a href="https://plus.google.com/+{{ author.gplus }}" itemprop="sameAs" class="icon-google-plus">Google+</a> {% endif %}

			{%  if author.soundcloud %}<a href="https://soundcloud.com/{{ author.soundcloud }}" itemprop="sameAs" class="icon-soundcloud">Soundcloud</a> {% endif %}
			{%  if author.youtube %}<a href="https://www.youtube.com/user/{{ author.youtube }}" itemprop="sameAs" class="icon-youtube">YouTube</a> {% endif %}
			{%  if author.spotify %}<a href="https://open.spotify.com/user/{{ author.spotify }}" itemprop="sameAs" class="icon-spotify">Spotify</a> {% endif %}
			{%  if author.twitch %}<a href="https://www.twitch.tv/{{ author.twitch }}" itemprop="sameAs" class="icon-twitch">Twitch</a> {% endif %}

			{%  if author.pinterest %}<a href="https://www.pinterest.com/{{ author.pinterest }}" itemprop="sameAs" class="icon-pinterest">Pinterest</a> {% endif %}
			{%  if author.dribble %}<a href="https://dribbble.com/{{ author.dribble }}" itemprop="sameAs" class="icon-dribbble">Dribble</a> {% endif %}
			{%  if author.behance %}<a href="https://www.behance.net/{{ author.behance }}" itemprop="sameAs" class="icon-behance">Behance</a> {% endif %}  
			{%  if author.s500px %}<a href="https://500px.com/{{ author.s500px }}" itemprop="sameAs" class="icon-500px">500px</a> {% endif %}
			{%  if author.reddit %}<a href="https://de.reddit.com/user/{{ author.reddit }}" itemprop="sameAs" class="icon-reddit">Reddit</a> {% endif %}
		</div>                                   
	</div>                                       
</section>    

{% assign cv = site.data.cv[page.author] %}
<div class="cv-body">
  <div class="md-card no-border">
		<p>{{cv.profile}} <a href="https://adonaiohesed.github.io/2018/01/01/mission.html"> More detail </a> </p>
  </div>

  <div class="md-card shadow">
		<div class="title icon-stats-bars">
			<h2>Skills</h2>
		</div>
		<div class="content">
			<ul>
				{% for skill in cv.skills %}
				<li>{{ skill }}</li>
				{% endfor %}
			</ul>
		</div>
  </div>

	<div class="md-card shadow education">
		<div class="title icon-book">
			<h2>Publication</h2>
		</div>
		<div class="content">
			<ul>
			{% for publication in cv.publications %}
				<li> 
					 J. Kim, <div class="publication-name"> H. Choi</div>, S. Bae
					 "{{publication.title}}"
					 <div class="publication-place"> {{publication.place}}, </div>
					 {{publication.time}}
				</li>
			{% endfor %}
			</ul>	
		</div>
  </div>

  <div class="md-card shadow education">
		<div class="title icon-library">
			<h2>Education</h2>
		</div>
		{% for entry in cv.education %}   
		<dl>
			<dt class="time">{{entry.time}}</dt>
			<dd>
				<h3>{{entry.location}}</h3>
				<p style="margin-left:130px">{{entry.description}}</p>
			</dd>
		</dl>
		{% endfor %}
  </div>

  <h2 class="employment-heading">Employment History</h2>

  <div class="timeline-container">
		{% for employment in cv.employment %}
		<div class="timeline-block">
			<div class="marker"></div>
			<div class="time">{{employment.time}}</div>
			<div class="timeline-content">
				<div class="time">{{employment.time}}</div>
				<h3>{{employment.position}}</h3>
				<span>{{employment.company}} ({{employment.location}})</span>
				<ul>
					{% for responsibility in employment.responsibilities %}
					<li>{{responsibility}}</li>
					{% endfor %}
				</ul>
			</div>
		</div>
		{% endfor %}
  </div>


  <h2 class="project-heading">Project History</h2>

  {% for project in cv.projects %}
  <div class="md-card shadow project">
		<div class="meta">
			<div class="team">{{project.team}}</div>
			<div class="time">{{project.time}}</div>
		</div>
		<div class="content">
			<h2>{{project.title}}</h2>
			<ul>
				{% for responsibility in project.responsibilities %}
				<li>{{responsibility}}</li>
				{% endfor %}
			</ul>
		</div>
		<div class="cv-footer">
			<ul>
				{% assign technologies = project.technologies | split: ',' %}
				{% for technology in technologies %}
				<li> {{ technology }}</li>
				{% endfor %}
			</ul>
			<span class="icon-briefcase"></span>
		</div>
  </div>
  {% endfor %}

</div>