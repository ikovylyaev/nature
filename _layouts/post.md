---
layout: default
---
<div class="is-navbar-container">
    <div class="is-brand" style='padding-right: 50px;'>
		<b class="is-logo" style='position: relative; z-index: 1000000;'>
			<div class='img-logo'>
				<img src='{{ site.url }}/img/small.svg' alt='logo'>
			</div>
			<b style='display: inline-block'>натуральный поход</b>
		</b>
    <!-- nav toggle element -->
        <a href="#" id='nav-toggle' class="nav-toggle is-push-right-mobile is-shown-mobile icon-kube-menu"></a>
    </div>
	<!-- main navigation -->
    <div id="navbar-desctop" class="is-navbar is-hidden-mobile">
        <!-- primary navigation -->
        <nav>
            <ul>
                <li><a href="{{ site.url }}/places"><b>места</b></a></li>
                <li><a href="{{ site.url }}/map">карта</a></li>
                <li><a href="{{ site.url }}/about">о нас</a></li>
            </ul>
        </nav>
        <!-- secondary navigation -->
        <nav class="is-push-right navbar-right-content">
            <ul>
                <li><a href="https://vk.com/natureexpedition">vk</a></li>
                <li><a href="https://vk.com/ikovylyaev">instagram</a></li>
                <li><a href="https://www.youtube.com/channel/UCf9GOVc0qKKPB-Ee3LfH_uw">youtube</a></li>
            </ul>
        </nav>
    </div>
    <!-- collapsable navigation -->
    <div id="navbar-mobile" class="is-navbar">
        <!-- primary navigation -->
        <nav>
            <ul>
                <li><a href="{{ site.url }}/places"><b>места</b></a></li>
                <li><a href="{{ site.url }}/map">карта</a></li>
                <li><a href="{{ site.url }}/about">о нас</a></li>
            </ul>
        </nav>
        <!-- secondary navigation -->
        <nav class="is-push-right navbar-right-content">
            <ul>
                <li><a href="https://vk.com/natureexpedition">vk</a></li>
                <li><a href="https://vk.com/ikovylyaev">instagram</a></li>
                <li><a href="https://www.youtube.com/channel/UCf9GOVc0qKKPB-Ee3LfH_uw">youtube</a></li>
            </ul>
        </nav>
    </div>
</div>
<div class='content'>
	<div style="width: 100%; height: 75vh; background: url('{{ site.url }}/photos/{{page.number}}/title.jpg'); background-position: center;background-size: cover; background-position: top center; margin-bottom: 10px; position: relative;">
        <h1 style='background: #ff7400; color: #fff; padding: 20px 50px 20px 80px; position: absolute; left: 0px; bottom: 10vh;'>
            <div style='position: absolute; background: #ff7400; position: absolute; left: -130px; top: 0px; width: 130px; content: ""; height: 100%'></div>
            {{ page.title }}
        </h1>
    </div>
    <div class='row' style='margin-bottom: 100px;'>
        <div class='col'>
            <small>регион</small><h3>{{page.region}}</h3>
        </div>
        <div class='col'>
            <small>дата публикации</small><h3>{{page.date| date: "%d.%m.%Y"}}</h3>
        </div>
        <div class='col'>
            <small>автор</small>
            <a href='{{site.url}}/about/#{{page.author}}' style='color: #000; text-decoration: none;'><h3>@{{page.author}}</h3></a>
        </div>
    </div>
    <div>
        <h2>видео</h2>
        <iframe width="100%" height="600" src="https://www.youtube.com/embed/{{page.youtube}}" frameborder="0" allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>
    <div style='margin-top: 100px;'>
        <h2>фото</h2>
        <link  href="https://cdnjs.cloudflare.com/ajax/libs/fotorama/4.6.4/fotorama.css" rel="stylesheet">
        <script src="https://cdnjs.cloudflare.com/ajax/libs/fotorama/4.6.4/fotorama.js"></script>
        <div class="fotorama" 
                data-height='600'
                data-arrows="true"
                data-click="true"
                data-swipe="true"
                data-trackpad="true"
                data-autoplay="true"
                data-nav="thumbs"
                style='background: #fff;'
        >
            {% for photo in page.photos %}
                <img src='{{site.url}}/photos/{{page.number}}/big/{{ photo.link }}' data-thumb="{{site.url}}/photos/{{page.number}}/small/{{ photo.link }}" alt='{{page.title}}'>
            {% endfor %}
        </div>
    </div>
    <div style='margin-top: 100px;'>
        <h2 class='mb-3'>статьи</h2>
        {% for post in page.textes %}
        <div class='row mb-4'>
            <div class='card'>
                <a  href='{{ post.link }}'>
                    <p>{{ post.author }}</p>
                    <h3>{{ post.title }}</h3>
                </a>
            </div>
        </div>
        {% endfor %}
    </div>
    {{content}}

</div>

<div class='footer is-row'>
    <div class='is-col' style='width: 80px!important;min-width: 80px!important;max-width: 80px!important; margin-left: 0px!important;'>
        <img class='logo' src='{{ site.url }}/img/small.svg' alt='logo'>
    </div>
    <div class='is-col'>
        <nav>
            <ul>
                <li><a class='link-white' href="{{ site.url }}/places"><b>места</b></a></li>
                <li><a class='link-white' href="{{ site.url }}/map">карта</a></li>
                <li><a class='link-white' href="{{ site.url }}/about">о нас</a></li>
            </ul>
        </nav>
        <!-- secondary navigation -->
        <nav>
            <ul>
                <li><a class='link-white' href="https://vk.com/natureexpedition">vk</a></li>
                <li><a class='link-white' href="https://vk.com/ikovylyaev">instagram</a></li>
                <li><a class='link-white' href="https://www.youtube.com/channel/UCf9GOVc0qKKPB-Ee3LfH_uw">youtube</a></li>
            </ul>
        </nav>
    </div>
    <div class='copy'>
        <img src='{{site.url}}/img/ikovylyaev.svg' style='height: 40px!important'>
        <p>made by <a href='http://ikovylyaev.com' class='link-white'>ikovylyaev</a></p>
    </div>
</div>