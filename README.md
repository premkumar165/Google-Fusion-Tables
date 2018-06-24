# Google-Fusion-Tables

# HTML Code
<!DOCTYPE html>
<html>
<head>
<meta name="viewport"/>
<title>Participant distribution - Ontario community pharmacists' knowledge, attitudes and behavior towards influenza vaccine hesitancy</title>
<style type="text/css">
html, body, #googft-mapCanvas {
  height: 1024px;
  margin: 0;
  padding: 0;
  width: 768px;
}
</style>

<script type="text/javascript" src="https://maps.google.com/maps/api/js?v=3"></script>

<script type="text/javascript">
  function initialize() {
    var isMobile = (navigator.userAgent.toLowerCase().indexOf('android') > -1) ||
      (navigator.userAgent.match(/(iPod|iPhone|iPad|BlackBerry|Windows Phone|iemobile)/));
    if (isMobile) {
      var viewport = document.querySelector("meta[name=viewport]");
      viewport.setAttribute('content', 'initial-scale=1.0, user-scalable=no');
    }
    var mapDiv = document.getElementById('googft-mapCanvas');
    mapDiv.style.width = isMobile ? '100%' : '1366px';
    mapDiv.style.height = isMobile ? '100%' : '768px';
    var map = new google.maps.Map(mapDiv, {
      center: new google.maps.LatLng(44.38051838325974, -81.25493871875),
      zoom: 7,
      mapTypeId: google.maps.MapTypeId.ROADMAP
    });
    map.controls[google.maps.ControlPosition.RIGHT_BOTTOM].push(document.getElementById('googft-legend-open'));
    map.controls[google.maps.ControlPosition.RIGHT_BOTTOM].push(document.getElementById('googft-legend'));
    layer = new google.maps.FusionTablesLayer({
      map: map,
      heatmap: { enabled: false },
      query: {
        select: "col1",
        from: "13CiaOOewQzXNPDt-y4beX0a3LQqMU-hYD38bVn-d",
        where: ""
      },
      options: {
        styleId: 2,
        templateId: 2
      }
    });
    if (isMobile) {
      var legend = document.getElementById('googft-legend');
      var legendOpenButton = document.getElementById('googft-legend-open');
      var legendCloseButton = document.getElementById('googft-legend-close');
      legend.style.display = 'none';
      legendOpenButton.style.display = 'block';
      legendCloseButton.style.display = 'block';
      legendOpenButton.onclick = function() {
        legend.style.display = 'block';
        legendOpenButton.style.display = 'none';
      }
      legendCloseButton.onclick = function() {
        legend.style.display = 'none';
        legendOpenButton.style.display = 'block';
      }
    }
  }
  google.maps.event.addDomListener(window, 'load', initialize);
</script>
</head>

<body>
  <div id="googft-mapCanvas"></div>
</body>
</html>


# Distribution
![Distribution](Distribution.png)

# HeatMap
![Heat-Map-Large](HeatMap1.png)

