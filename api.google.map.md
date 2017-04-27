### google map


* html

```bash
<body onload = "loadMap()">
      <div id = "carte" style = "width:570px; height:580px;"></div>
</body>
```

* jquery
```bash
      <script src = "https://maps.googleapis.com/maps/api/js"></script>
      
      <script>
         function loadMap() {

            var latlng = new google.maps.LatLng(46.779231, 6.659431);

            var options = {
               center: latlng,
               zoom: 19,
               mapTypeId: google.maps.MapTypeId.ROADMAP
            };

            var carte = new google.maps.Map(document.getElementById("carte"), options);

             //création du marqueur

            var marqueur = new google.maps.Marker({
               position: new google.maps.LatLng(46.779231, 6.659431),
               map: carte
            });

         }
      </script>
```


* more info

```bash
http://www.tutorialspoint.com/google_maps/
https://openclassrooms.com/courses/google-maps-javascript-api-v3
```