<h3> Richard Dait
<h3> GEOG 458
<h3> 03/12/2021

</br>
</br>
</br>
<a href="https://imgur.com/nXOsuW9"><img src="https://i.imgur.com/nXOsuW9.png" title="source: imgur.com" /></a>
<h2> <p align="center">  <b> Essay: Analyzing The Spoken World Mapping Project</b> </p> </br>
<h3><b> Overview</b></br>
<h4> <p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The digital geography related project I am analyzing and critiquing is <a href="https://mikus31.github.io/the-spoken-world/">The Spoken World</a> by Michael McNeil. It is an interactive worldwide webmap of location name pronunciations. The cartographer was inspired by his inability to help his nine year old cousin, Asher, say <a href="https://github.com/mikus31/the-spoken-world">Icelandic</a> places for his school assignment. While as a student at the <a href="https://newmapsplus.as.uky.edu/explore-new-maps">University of Kentucky</a>, Michael decided to build an interactive, thematic webpage for the purpose of teaching himself and others an acceptable and non-offensive way of saying location names.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; The major function of the webpage is the click event where it highlights each numbered cluster marker with a polygon after one hovers over them. Each click results in the page zooming inward. Markers simultaneously break into smaller circles or red markers with location names. The zoom feature is an alternative way of accomplishing this. Another function is the switchboard with radio buttons located at the top right. The user has the option of choosing between a light and dark basemap. A simple, yet useful function is the ability to minmize the splash window with either the arrow or list icons. There is also an attribution 'i' button that displays information such as who the map maker is and data sources, when it is clicked.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While the webpage is nice to look at and fun to play with, it is unfortunately missing key map elements. There is no legend to tell the user what the symbols are, what the colors represent and what the numerical values mean. Additionally, it is without a scale bar and north arrow. They are necessary to communicate to the reader what the purpose is and what the content is all about. There is a title, which I have not been able to implement as a beginner level map maker. This is something I appreciate. Additionally, Michael provides an attribution link and citation of sources. These are required components when making a webpage or project as they give proper credit and gives the user tools to produce a map of their own.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The intended audience are beginner level cartographers and those who are curious about saying location names at an accceptable level where locals would not find it offensive. The implementation, functions and code are a bit more sophisticated than what an undergraduate geography major at the University of Washington would be able to do. However, I, as an undergraduate find the code extremely useful and may incorporate them in future projects. Up and coming map makers would also benefit from this webmap as the handling events are challenging, but achievable and fun to implement. Besides those who have a difficult time pronouncing a place name, globetrotters can also use this project to better relate with locals. Michael McNeil talks about the importance of place names on his <a href="https://github.com/mikus31/the-spoken-world">Github page</a> as they speak to a group's culture and identity.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;As mentioned, Michael McNeil is the lone author and map maker. At the time of creation, he was affliated with the University of Kentucky as a student obtaining his master of science in <a href="https://newmapsplus.as.uky.edu/">digital mapping/new maps plus</a>. While the author does not explicitly state, the last update of the <a href="https://github.com/mikus31/the-spoken-world/tree/master/data">data folder</a> on his Github page was in 2019, so that is the assumed data collected date. The data sources are Natural Earth, MapBox Studio and Forvo. This can be found on the popup interactive window of the <a href="https://mikus31.github.io/the-spoken-world/">webmap</a>.
</p>
<h3><b> System Architecture</b></br>
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The webpage was built using leaflet with a third-party map server, OpenStreetMap and client-side Javascript libraries. Design elements such as fonts are from Google Fonts, icons from The Noun Project and Material Design and colors from ColorSupplyyy. Point data was extracted from Natural Earth and place name pronunciations from Forvo. Essentially, tiles are hosted on OpenStreetMap, which is loaded onto Leaflet via code by the mapmaker. Data flows in between the client and server. Javascript libraries such as jQuery loads GeoJSON files. <q> <!doctype html>
<html lang="en">

<head>
    <title>The Spoken World</title>
    <meta charset=utf-8 />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <!-- Leaflet CSS -->
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.4.0/dist/leaflet.css" integrity="sha512-puBpdR0798OZvTTbP4A8Ix/l+A4dHDD0DGqYW6RQ+9jxkRFclaxxQb/SJAWZfWAkuyeQUytO7+7N4QKrDh+drA==" crossorigin="" />
    <!-- Marker Clusters -->
    <link rel="stylesheet" href="libs/Leaflet.markercluster/MarkerCluster.Default.css">
    <link rel="stylesheet" href="libs/Leaflet.markercluster/MarkerCluster.css">
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css?family=Lato|Oswald" rel="stylesheet">
    <!--font-family: 'Oswald', sans-serif;
    font-family: 'Lato', sans-serif;-->
    <!-- Sidebar V-2 -->
    <link rel="stylesheet" href="libs/sidebar-v2/leaflet-sidebar.css" />
    <!-- Google Icons -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
    <style>
        body {
            padding: 0;
            margin: 0;
        }

        h1 {
            font-family: 'Oswald', sans-serif;
            font-size: 4.5em;
            color: white;
            text-align: center;
        }

        h2 {
            font-family: 'Oswald', sans-serif;
            font-size: 1em;
            color: #d74840;
        }

        p {
            font-family: 'Lato', sans-serif;
            font-size: .9em;
        }

        html,
        body,
        #map {
            height: 100%;
            width: 100vw;
        }

        #sound {
            z-index: 1999;
            bottom: 12px;
            left: 61px;
            position: absolute;
        }

        audio {
            z-index: 1999;
            bottom: 13px;
            left: 61px;
            position: absolute;
        }
    </style>
</head>

<body>
    <div id="sidebar" class="sidebar collapsed">
        <!-- Nav tabs -->
        <div class="sidebar-tabs">
            <ul role="tablist">
                <li><a href="#home" role="tab"><i class="material-icons">toc</i></a></li>
                <!--                <li><a href="#search" role="tab"><i class="material-icons">search</i></a></li>-->
                <!--                <li><a href="#audio" role="tab"><i class="material-icons">hearing</i></a></li>-->
                <li><a href="#share" role="tab"><i class="material-icons">share</i></a></li>
                <!--                <li class="disabled"><a href="#messages" role="tab"><i class="material-icons">mail_outline</i></a></li>-->
            </ul>
            <ul role="tablist">
                <li><a href="#info" role="tab"><i class="material-icons">info</i></a></li>
                <!--                <li><a href="#settings" role="tab"><i class="material-icons">settings</i></a></li>-->
                <!--                <li><a href="https://github.com/mikus31/the-spoken-world" role="tab" target="_blank"><i class="material-icons">link</i></a></li>-->
            </ul>
        </div>
        <!-- Tab panes -->
        <div class="sidebar-content">
            <div class="sidebar-pane" id="home">
                <h1 class="sidebar-header">The Spoken World<span class="sidebar-close"><i class="material-icons">chevron_left</i></span>
                </h1>
                <p>An interactive worldwide map of place-name pronunciations.</p>
                <p>To begin using the map, close this popup by clicking on the arrow above. On the map, you can zoom in, zoom out, and pan using your mouse (on desktop) or fingers (on mobile or tablet). Clicking on a numbered cluster marker also will zoom in to the map. </p>
                <p>To access the audio for a particular place, click on the red map markers and then on the play button.</p>
                <p>Some places on the map may not have pronunciations yet. You can contribute to the completion of the map by submitting a missing pronunciation on the website <a href='https://forvo.com/' target="_blank">Forvo.com</a>.</p>
                <p>Read more about the project <a href='https://github.com/mikus31/the-spoken-world' target="_blank">on GitHub</a>.</p>
            </div>
            <!--<div class="sidebar-pane" id="audio">
                <h1 class="sidebar-header">Audio History<span class="sidebar-close"><i class="material-icons">chevron_left</i></span></h1>
                <p>Audio controls?</p>
                <p>Last five?</p>
                <p>Most popular?</p>
            </div>-->
            <!--<div class="sidebar-pane" id="search">
    <h1 class="sidebar-header">Search<span class="sidebar-close"><i class="material-icons">chevron_left</i></span></h1>
    <p>Embed <a href='https://github.com/stefanocudini/leaflet-search' target="_blank">leaflet-search?</a></p>
</div>-->
            <div class="sidebar-pane" id="info">
                <h1 class="sidebar-header">More Information<span class="sidebar-close"><i class="material-icons">chevron_left</i></span></h1>
                <h2>Data Sources</h2>
                <p>Populated places point data from <a href='http://www.naturalearthdata.com/' target="_blank">Natural Earth</a>.</p>
                <p>Custom basemaps created in <a href='https://www.mapbox.com/' target="_blank">Mapbox Studio</a>.</p>
                <p>Place-name pronunciations from <a href='https://forvo.com/' target="_blank">Forvo</a>.</p>
                <h2>Mapping Libraries</h2>
                <p><a href='https://leafletjs.com/' target="_blank">Leaflet JS</a></p>
                <p><a href='https://github.com/Leaflet/Leaflet.markercluster' target="_blank">Leaflet Marker Cluster</a></p>
                <p><a href='https://github.com/Turbo87/sidebar-v2' target="_blank">Leaflet Sidebar-v2</a></p>
                <h2>Design Elements</h2>
                <p>Fonts from <a href='https://fonts.google.com/' target="_blank">Google Fonts</a>.</p>
                <p>Icons from <a href='https://thenounproject.com/' target="_blank">The Noun Project</a> and <a href='https://material.io/' target="_blank">Material Design</a>.</p>
                <p>Colors by <a href='http://stevescott.com.au/' target="_blank">Steven Scott</a> via <a href='https://colorsupplyyy.com/app' target="_blank">ColorSupplyyy</a>, where I spent hours playing with their fun color picking tool!</p>
                <h2>Acknowledgments</h2>
                <p>Special thanks to <a href='https://stpao.org/' target="_blank">Louis Fitzmorris</a>, Rich Donohue, the New Maps Plus Slack channel, my cousin Asher for inspiring <a href='https://github.com/mikus31/the-spoken-world' target="_blank">the project</a>, and my supportive, honest-feedback-providing wife Sarah.</p>
                <h2>About</h2>
                <p>Master's Degree project by <a href='https://www.linkedin.com/in/michael-mcneil-8279ba51/' target="_blank">Michael McNeil</a> for <a href='https://newmapsplus.as.uky.edu/' target="_blank">New Maps Plus</a> at the <a href='http://www.uky.edu/UKHome/' target="_blank">University of Kentucky</a>.</p>
                <p>Publication Date: 2019-06-13</p>
            </div>
            <div class="sidebar-pane" id="share">
                <h1 class="sidebar-header">Share This Map!<span class="sidebar-close"><i class="material-icons">chevron_left</i></span></h1>
                <p><a href="https://twitter.com/home?status=The%20Spoken%20World,%20an%20interactive%20map%20of%20place-name%20pronunciations%20(by%20%40mikusthetiger%20for%20%40newmapsplus%20%40universityofky)%20---%3E%20%20https%3A//mikus31.github.io/the-spoken-world/" target="_blank">Share on Twitter</a></p>
                <p><a href="https://www.facebook.com/sharer/sharer.php?u=https%3A//mikus31.github.io/the-spoken-world/" target="_blank">Share on Facebook</a></p>
                <p><a href="https://www.linkedin.com/shareArticle?mini=true&url=https%3A//mikus31.github.io/the-spoken-world/&title=The%20Spoken%20World&summary=An%20interactive%20map%20of%20place-name%20pronunciations.&source=" target="_blank">Share on LinkedIn</a></p>
            </div>
            <div class="sidebar-pane" id="settings">
                <h1 class="sidebar-header">Settings<span class="sidebar-close"><i class="material-icons">chevron_left</i></span></h1>
                <p>Light Mode / Dark Mode switch?</p>
                <p>Choose language?</p>
            </div>
        </div>
    </div>
    <div id="map" class="sidebar-map">
        <!--        <button id="sound">click for audio</button>-->
    </div>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
    <script src="https://unpkg.com/leaflet@1.4.0/dist/leaflet.js" integrity="sha512-QVftwZFqvtRNi0ZyCtsznlKSWOStnDORoefr1enyq5mVL4tmKB3S/EnC3rRJcxCPavG10IcrVGSmPh6Qw5lwrg==" crossorigin=""></script>
    <script src='https://api.mapbox.com/mapbox.js/v3.2.0/mapbox.js'></script>
    <script src="https://unpkg.com/leaflet.markercluster@1.4.1/dist/leaflet.markercluster.js"></script>
    <script src="https://d3js.org/d3-dsv.v1.min.js"></script>
    <script src="https://d3js.org/d3-fetch.v1.min.js"></script>
    <script src="https://d3js.org/d3.v5.min.js"></script>
    <script src="libs/sidebar-v2/leaflet-sidebar.js"></script>
    <script>
        // create map
        L.mapbox.accessToken = 'pk.eyJ1IjoibWlrdXMzMSIsImEiOiJjazFjNWJibXcwYTJ6M3BxbjExaTAxMDFvIn0.-jtTOhL7aN53DazF5RRvxw';
        // add light mode and dark mode here
        var lightMode = L.mapbox.styleLayer('mapbox://styles/mikus31/cjajul8jxb6212rq7ly2wgenz')
            , darkMode = L.mapbox.styleLayer('mapbox://styles/mikus31/cjuvg0hhxc3011fpo0h58juwq');
        // initialize the map in lightMode
        var map = L.map('map', {
            layers: [lightMode]
        });
        // create text for basemap switcher box
        var baseMaps = {
            "Light Basemap": lightMode
            , "Dark Basemap": darkMode
        };
        // add the basemap switcher box to the map
        L.control.layers(baseMaps).addTo(map);
        // allow map to access user's location?
        /*map.locate({
            setView: true
            , maxZoom: 16
        });*/
        // create custom marker icon
        var audioIcon = L.icon({
            iconUrl: 'images/marker-red.png'
            , iconSize: [40, 40], // size of the icon
            iconAnchor: [20, 20], // point of the icon which will correspond to marker's location
            popupAnchor: [0, 0]
                // point from which the popup should open relative to the iconAnchor
        });
        // load places geojson and call function to add data to map
        $.getJSON("data/places-newtable.geojson", function (data) {
            drawPlaces(data);
        });
        // add sidebar to map
        var sidebar = L.control.sidebar('sidebar').addTo(map);
        sidebar.open('home');
        // add function to close sidebar when user zooms in
        // map.setZoom in drawPlaces is causing this to fire when the page loads ... is there a way to delay this function until the user zooms in?
        /*map.on('zoom', function () { sidebar.close(); });*/
        function drawPlaces(data) {
            var places = L.geoJson(data);
            // set the zoom/center to the extent of the geojson
            map.fitBounds(places.getBounds());
            // and then zoom in a tad
            map.setZoom(map.getZoom() + .5);
            // set the max bounds to prevent user from scrolling beyond bounds?
            map.setMaxBounds(map.getBounds());
            // create new markerClusterGroup
            var markers = L.markerClusterGroup();
            // close the sidebar when cluster is clicked
            markers.on('clusterclick', function () {
                sidebar.close();
            });
            // loop through all the features
            data.features.forEach(function (feature) {
                // create a new Leaflet marker for each
                var coords = feature.geometry.coordinates
                    , marker = L.marker([coords[1], coords[0]], {
                        icon: audioIcon
                    });
                // create a tooltip for the markers ...
                var props = feature.properties;
                // console.log(props.nameascii);
                var placesPopup = props.nameascii;
                // ... and bind it to the markers
                marker.bindTooltip(placesPopup);
                // add the individual markers to the markerClusterGroup
                markers.addLayer(marker);
                marker.feature = {
                    properties: {
                        placeName: props.nameascii
                    }
                }
                marker.on('click', function () {
                    // close the sidebar if still open
                    sidebar.close();
                    let placeName = this.feature.properties.placeName;
                    console.log(placeName)
                    let url = 'https://apifree.forvo.com/key/f08a91897cb826f93096d8ea72e87c4e/format/json/action/standard-pronunciation/word/' + placeName;
                    console.log(url)
                    getPath(url);
                });
            });
            // add the markerClusterGroup to the map
            map.addLayer(markers);
        }

        function getPath(path) {
            $.ajax({
                    url: path
                    , type: 'GET'
                    , dataType: 'jsonp'
                    , cors: true
                    , contentType: 'application/json'
                    , secure: true
                    , headers: {
                        'Access-Control-Allow-Origin': '*'
                    , }
                    , beforeSend: function (xhr) {
                        xhr.setRequestHeader("Authorization", "Basic " + btoa(""));
                    }
                    , success: function (data) {
                            let mp3Path = data.items[0].pathmp3;
                            let oggPath = data.items[0].pathogg;
                            d3.select('audio').remove();
                            d3.select('body').append('audio').attr('controls', '').append('source').attr('type', 'audio/mpeg').attr('src', mp3Path)
                            d3.select('audio').append('source').attr('type', 'audio/ogg').attr('src', oggPath)
                        }
                        // what if forvo does not have a pronunciation yet for a place?
                        // can create a failure function to drive users to the forvo site to submit one?

                    , failure: function (data) {
                        console.log('uh oh, no audio file!')
                    }
                })
                // console.log(url);
        }
    </script>
</body>

</html></q></p>
<h3><b> UI/UX and Web Mapping Design </b></br>
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Spoken World project supports responsive design. It was tested on three devices. The webpage's functions and features work beautifully on my laptop. There is no image distortion or reduction in resolution when I click on markers or toggle between basemaps. The image quality remains crisp throughout and the performance (e.g., transition between zooms) of the page is consistent. In other words, it does not lag. As for my mobile phone, the webpage works seemlessly on mobile and desktop version. Surprisingly, the animated effects after clicking on the markers do not produce a delay. Radio buttons for the basemaps respond to my selection and the zoom feature works efficiently. The webpage automatically resize according to the mobile version on my phone. When I switch to desktop site, the page enlarges without any performance lag or distortion. As for my roommate's ipad, there were no issues. The webpage responds to my behavior accordingly. For example, when I rotate the device landscape mode, it adjust itself to fit the screen size. As with the other devices, images are crisp throughout and transitions age smooth after each event.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;There are two basemaps - light and dark. They were customized on <a href="https://www.mapbox.com/">MapBox Studio</a>. In my opinion, they are well-made and excellent choices as one caters to the playful crowd, while the other accentuates the colorful numbered cluster markers. You cannot go wrong with either one.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Since the purpose of the webpage is to help the user pronounce a particular location, the map layer is not thematic. It does not display a geographic pattern or phenomena. I would say it is more of a reference map as the end marker produces the name of the place. Additionally, the map is one color and symbols are not proportional to any data.
</br>
</br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; There are several interactive features. First is the mouse event that let a user hover over a symbol. If one hover, scroll over or clicks on a red marker, the location name appears. The same behavior can be applied to the colorful circular objects. However, a polygon encircles
the circular symbol. Another interactive feature is the click event. After the click is fired, a numbered cluster circle either breaks into small circles, or turns into multiple red location markers. Another interactive feature is the switchboard with radio buttons where a user can toggle between basemaps. This is a useful tool, especially for those who prefer to look at a webpage in a different light. Besides allowing a user to zoom in and out of a page, it fires the same event as clicking on a circle. The introduction window is also interactive as you are able to expand or contract it and click on numerous links associated with the webpage.</p>
<h3><b>Pros and Cons</b></br>
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; One reason why I chose this project to analyze oppose to others is, it is visually pleasing. At first glance, my eyes could not help but be attracted to the choice of colors and setup of the map. In my opinion, one huge flaw that beginner to mid level cartographers make is selecting the wrong color scheme. I am guilty of this. Michael selected bright and fun colors such as yellow and orange that are not only nice to look at, but they go hand-in-hand with the purpose of the project. Additionally, the map is set at a perfect scale as you are able to clearly see the study/geography area and points of interest to understand the intended use. Another thing that I absolutely love are the numerous handling events. One is the ability to toggle back and forth between two basemaps via radio buttons. The choices are simple and brilliant - light and dark. Another interactive event that makes a world of a difference is the splash window. Not only does it contain a share button with working url links, but there is an option to contract it. Furthermore, Michael provides an attribution or more information icon ('i') that displays a ton of information. A few include data sources, mapping libraries and an about me segment. As an aspiring cartographer, I find this extremely helpful and will incorporate a similar style in the future. The last positive that is worth mentioning is the result from clicking on a numbered cluster marker. As you click on a circle, it quickly breaks apart into smaller circles or red markers with the name of the zoomed in location. This can also be done using the zoom button. I find this useful because as a user, I like to have options.</br></br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While the interactive webpage project has a lot of positive traits, I noticed a few cons. The obvious one is the inoperable audio option. This could be due to a flaw in the code or the cartographer disabling or removing part of it. Regardless, I was looking forward to hearing the right pronounciation of the location names. After all, the project is built around this. The only other negative is, the webpage is missing two necessary map elements - legend and scale. While the splash page window includes a brief summary of the project, I had to click on the associated Github to clarify any misunderstanding. A map legend is essential for the reader to grasp what the symbols, color scheme and numerical values represent.</p><p align="left"></p>
<h3><b>Reflection</b></br>
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While this webpage is playful and informative, it reminds me of three readings from this past quarter. The first is <a href="https://drive.google.com/file/d/1aqMFkewNT9s9nrAecAVYiaBAbtCrf7xj/view">Affective Geovisualisations</a> by Stuart Aitken and James Craine. They are pushing for more emotions in the world of geography and mapmaking via moving images or something similar. While the Spoken World project does not contain moving images, in my opinion, it can be an emotionally charged experience. When a user clicks on a red marker and the pronounciation is mentioned, it can spark an emotional response, especially if the user is unable to say the name correctly. Mapmaking does not have to incorporate moving images to stir emotions and affect change. An interactive map with a unique purpose can do just that. Users will be absorbed by the thought of saying a place's name over and over again, until they master the acceptable pronounciation according to locals. Another reading that this webpage reminded me of is <a href="https://drive.google.com/file/d/1T7ChuOnaKrgjTVhAeV_Niei2pqCWiiqK/view">Introducing Code/Space</a> The idea that code or software creates space aligns perfectly with what the author is trying to achieve - <blockquote> an effort to elevate local, authoritative pronunciations to the global level.</blockquote> His code may in fact, produce space as users who perfect an acceptable way of saying a location's name, will be empowered to travel to distant places without the worry of offending locals or not saying things right. The last reading centers on the concept of intent regarding algorithms. While the purpose of the Spoken World project is to inform and educate, one cannot help but think about other webpages that have similar features with a different intent. Algorithms and code are powerful. They can cause harm and injustice. Luckily, the webpage is nothing more than a learning experience.
<h3><p align="center"><b>References</b></br>
<h4><ol type = "1"><li>McNeil, Michael. 2015. <i>The Spoken World</i>. https://mikus31.github.io/the-spoken-world/ (Accessed on 03/09/2021).</li><li>University of Kentucky, College of Arts and Sciences. 2015. <i>Explore New Maps: Examples of NMP Student Maps</i>. https://newmapsplus.as.uky.edu/explore-new-maps (Accessed on 03/09/2021).</li><li>Michael Mcneil: Digital Mapping Gallery. 2021. <i>Main Page</i>. https://mikus31.github.io/ (Accessed on 03/12/2021).</li><li>Github. 2021. <i>mikus31: the-spoken-world</i>. https://mikus31.github.io/ (Accessed on 03/12/2021).</li><li>Aitken, Stuart and Craine, James. 2006. <i>Affect Geovisualisations</i>. https://drive.google.com/file/d/1aqMFkewNT9s9nrAecAVYiaBAbtCrf7xj/view (Accessed on 03/12/2021).</li><li>Dodge, Rob and Dodge, Martin. 2011. <i>Chapter 1: Introducing Code/Space</i>. https://drive.google.com/file/d/1T7ChuOnaKrgjTVhAeV_Niei2pqCWiiqK/view (Accessed on 03/12/2021).</li><li>Amoore, Louise. 2020. <i>Chapter 3: Cloud Ethics. https://drive.google.com/file/d/1C3925q917K7cD8-NEbw_Yik_X0oCeSfd/view</i> (Accessed on 03/12/2021).</li></ol>
