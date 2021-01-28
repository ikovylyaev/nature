---
layout: default
title: карта
permalink: /map/
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
                <li><a href="{{ site.url }}/places">места</a></li>
                <li><a href="{{ site.url }}/map"><b>карта</b></a></li>
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
                <li><a href="{{ site.url }}/places">места</a></li>
                <li><a href="{{ site.url }}/map"><b>карта</b></a></li>
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
    <div id='map' style="width: 100%; height: calc(100vh - 150px); background: #ff7400; margin-bottom: 50px; position: relative;">
    </div>
</div>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.7.1/dist/leaflet.css"
   integrity="sha512-xodZBNTC5n17Xt2atTPuE1HxjVMSvLVW9ocqUKLsCC5CXdbqCmblAshOMAS6/keqq/sMZMZ19scR4PsZChSR7A=="
   crossorigin=""/>
 <script src="https://unpkg.com/leaflet@1.7.1/dist/leaflet.js"
   integrity="sha512-XQoYMqMTK8LvdxXYG3nZ448hOEQiglfqkJs1NOQV44cWnUrBc8PkAOcXy20w0vlaXaVUearIOBhiXZ5V3ynxwA=="
   crossorigin=""></script>
<script>
    var map = L.map('map', {zoomControl: false}).setView([56.837977, 60.603091], 10);
    var greenIcon = L.icon({
        iconUrl: '{{site.url}}/img/pin.svg',
        iconSize:     [50, 50], // size of the icon
        iconAnchor:   [25, 0], // point of the icon which will correspond to marker's location
        popupAnchor:  [0, 0] // point from which the popup should open relative to the iconAnchor
    });
    L.control.zoom({position: 'bottomright'}).addTo(map);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '&copy; натуральный поход | made by <a href="http://ikovylyaev.com">ikovylyaev</a> | <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> '
    }).addTo(map);
    {% for post in site.posts %}
    L.marker([{{ post.map }}], {icon: greenIcon}).addTo(map)
        .bindPopup('<h4>{{ post.title }}</h4><a class="link-white" href="{{site.url}}{{post.url}}">перейти</a>')
    {% endfor %}
</script>
<style>
    body{
        overflow: hidden;
    }
    .custom-popup, .leaflet-popup-content-wrapper {
        background:#ff7400;
        color:#fff;
        font-size:12px;
        line-height:10px;
        border-radius: 0px;
    }
    .custom-popup, .leaflet-popup-content-wrapper a {
        color:rgba(255,255,255,0.1);
    }
    .custom-popup, .leaflet-popup-tip-container {
        width:30px;
        height:15px;
    }
    .custom-popup, .leaflet-popup-tip {
        background: transparent;
        border: none;
        box-shadow: 0 0px 0px rgba(0,0,0,0)!important;
    }
    .leaflet-container a.leaflet-popup-close-button {
        color: #fff;
    }
</style>