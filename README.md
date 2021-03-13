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
</p> </br>
<h3><b> System Architecture</b></br>
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</p>
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
<h4><p align="left">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;While this webpage was playful and informative, it reminded me of three readings from this past quarter. The first is <a href="https://drive.google.com/file/d/1aqMFkewNT9s9nrAecAVYiaBAbtCrf7xj/view">Affective Geovisualisations</a> by Stuart Aitken and James Craine. They are pushing for more emotions in the world of geography and mapmaking via moving images or something similar. While the Spoken World project does not contain moving images, in my opinion, it can be an emotionally charged experience. When a user clicks on a red marker and the pronounciation is mentioned, it can spark an emotional response, especially if the user is unable to say the name correctly. Mapmaking does not have to incorporate moving images to stir emotions and affect change. An interactive map with a unique purpose can do just that. Users will be absorbed by the thought of saying a place's name over and over again, until they master the acceptable pronounciation according to locals. Another reading that this webpage reminded me of is <a href="https://drive.google.com/file/d/1T7ChuOnaKrgjTVhAeV_Niei2pqCWiiqK/view">Introducing Code/Space</a> The idea that code or software creates space aligns perfectly with what the author is trying to achieve - <blockquote> an effort to elevate local, authoritative pronunciations to the global level</blockquote>. His code may produce space as users who perfect an acceptable way of saying a location's name, will be empowered to travel to distant places without the worry of offending locals or not saying things right.  
<h3><p align="center"><b>References</b></br>
<h4><ol type = "1"><li>McNeil, Michael. 2015. <i>The Spoken World</i>. https://mikus31.github.io/the-spoken-world/ (Accessed on 03/09/2021).</li><li>University of Kentucky, College of Arts and Sciences. 2015. <i>Explore New Maps: Examples of NMP Student Maps</i>. https://newmapsplus.as.uky.edu/explore-new-maps (Accessed on 03/09/2021).</li><li>Michael Mcneil: Digital Mapping Gallery. 2021. <i>Main Page</i>. https://mikus31.github.io/ (Accessed on 03/12/2021).</li><li>Github. 2021. <i>mikus31: the-spoken-world</i>. https://mikus31.github.io/ (Accessed on 03/12/2021).</li><li>Aitken, Stuart and Craine, James. 2006. <i>Affect Geovisualisations</i>. https://drive.google.com/file/d/1aqMFkewNT9s9nrAecAVYiaBAbtCrf7xj/view (Accessed on 03/12/2021).</li></ol>
