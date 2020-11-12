# Audio player custom html structure
jPlayer with implement custom html structure

Help link: https://jplayer.org
## Screenshot 1
![Screenshot 1](screenshot.png)

## Screenshot 2
![Screenshot 2](screenshot2.png)


**Write your won HTML and CSS** 

	<div  id="myplayer"></div> <!-- actual player -->
	
	<!-- custom HTML structure -->
	<div  id="custom-layout-1"  class="jp-player"  role="application"  aria-label="media player"> 
		<div  class="left-controls">
			<div>
				<span  class="play-pause play-button"></span>
				<span  class="play-pause pause-button"  style="display: none"></span>
			</div>
			<span  class="time-duration">
				<span  class="jp-current-time"></span> / <span  class="jp-duration"></span>
			</span>
		</div>

		<div  class="middle-controls">
			<div  class="progress-wrap">
				<div  class="jp-progress">
					<div  id="jp-progress-bar"  class="jp-progress-bar"  style="width: 0%"></div>
				</div>
			</div>
		</div>
		<div  class="right-controls">
			<div  class="jp-sound">
				<div  class="vol-bar">
					<div  class="vol-bar-value"></div>
				</div>
				<span  class="mute-unmute mute-button" style="display: none"></span>
				<span  class="mute-unmute unmute-button"></span>
			</div>
			<div  class="more"><span  class="dots-vertical"></span></div>
		</div>
	</div>

**Import link jquery library and jplayer** 

	<script  type="text/javascript"  src="dist/js/jquery.min.js"></script>
    <script  type="text/javascript"  src="dist/js/jquery.jplayer.min.js"></script>
 ----

		$(document).ready(function(){
			// for the player 1
			$("#myplayer").jPlayer({
				ready: function () {
					$(this).jPlayer("setMedia", {
						title: "Bubble",
						m4a: "http://jplayer.org/audio/m4a/Miaow-07-Bubble.m4a",
						mp4: "https://www.w3schools.com/html/horse.mp3",
						oga: "http://jplayer.org/audio/ogg/Miaow-07-Bubble.ogg"  
					});
				},
				
				supplied: "m4a, oga, mp3",
				wmode: "window",
				volume: 0.5,
				useStateClassSkin: true,
				autoBlur: false,
				smoothPlayBar: true,
				keyEnabled: true,
				remainingDuration: true,
				toggleDuration: true,
				
				cssSelectorAncestor: "#custom-layout-1",
				cssSelector: {
				videoPlay: '.jp-video-play',
				play: '.play-button',
				pause: '.pause-button',
				stop: '.jp-stop',
				seekBar: '.jp-progress',
				playBar: '.jp-progress-bar',
				mute: '.mute-button',
				unmute: '.unmute-button',
				volumeBar: '.vol-bar',
				volumeBarValue: '.vol-bar-value',
				currentTime: '.jp-current-time',
				duration: '.jp-duration',
				}
			});
		});