---
layout: post
comments: true
title:  "Another post"
date:   2015-06-21 20:25:03
categories: jekyll update
---

<html>
  <head>
    <style>
      #map-canvas {
        width: 1000px;
        height: 600px;
      }
    </style>
    <script src="https://maps.googleapis.com/maps/api/js"></script>
    <script>
      function getDate(dateString) {
      	var dateValue = new Date(Date.parse(dateString));
      	return dateValue;
      }
      function getPosition() {
      	var today = new Date();
      	if (today < getDate("2015/07/03 20:00")) { //Madrid
      		return new google.maps.LatLng(40.4271128,-3.6821114);
      	} else if (today < getDate("2015/07/04 14:00")) { //Suances 
      		return new google.maps.LatLng(43.4140297,-4.0563102);
      	} else if (today < getDate("2015/07/04 21:00")) { //Santander
      		return new google.maps.LatLng(43.4613444,-3.8111371);
      	} else if (today < getDate("2015/07/05 04:00")) { //Navegando tarde/noche
      		return new google.maps.LatLng(45.327804, -5.339756);
      	} else if (today < getDate("2015/07/05 12:00")) { //Navegando madrugada
      		return new google.maps.LatLng(47.501230, -6.218662);
      	} else if (today < getDate("2015/07/05 20:00")) { //Navegando mediodia
      		return new google.maps.LatLng(49.808554, -3.494053);
      	/*} else if () { //Portsmouth
      		return new google.maps.LatLng(44.5403, -78.5463);
      	} else if () { //Salisbury
      		return new google.maps.LatLng(44.5403, -78.5463);
      	} else if () { //Santander
      		return new google.maps.LatLng(44.5403, -78.5463);
      	} else if () { //Santander
      		return new google.maps.LatLng(44.5403, -78.5463);
      	} else if () { //Santander
      		return new google.maps.LatLng(44.5403, -78.5463);
      	} else if () { //Santander
      		return new google.maps.LatLng(44.5403, -78.5463);
      	}*/
      	} else { // De vuelta en Madrid
      		return new google.maps.LatLng(40.4271128,-3.6821114);
      	}
      }

	  function initialize() {
	  	var westfalia = './westfalia.png';
	  	function addWestfalia(position) {
		  	var marker = new google.maps.Marker({
		  		position: position,
		  		icon: westfalia,
		  		map: map,
		  		title: "Aqui estamos!"
		  	});
			marker.setAnimation(google.maps.Animation.BOUNCE);
	  	}
	    var mapCanvas = document.getElementById('map-canvas');
	    var mapOptions = {
	      center: new google.maps.LatLng(47.6365, -9.9747026),
	      zoom: 5,
	      mapTypeId: google.maps.MapTypeId.ROADMAP
	    }
	    var map = new google.maps.Map(mapCanvas, mapOptions);

	    /* SET CURRENT POSITION DEPENDING ON TIME */
	    var home = getPosition();	
		addWestfalia(home);
	  }

	  google.maps.event.addDomListener(window, 'load', initialize);

	</script>
  </head>
  <body>
    <div id="map-canvas"></div>
  </body>
</html>
