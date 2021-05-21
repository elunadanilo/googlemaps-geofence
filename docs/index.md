## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/elunadanilo/googlemaps-geofence/edit/main/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/elunadanilo/googlemaps-geofence/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

<div id="map">
    </div>
    <script type="text/javascript">
        function initMap() {
            var objetos = [new google.maps.LatLng(14.149908, -90.843072), new google.maps.LatLng(14.149908, -90.843072), new google.maps.LatLng(14.149908, -90.843072), new google.maps.LatLng(14.150032, -90.843109), new google.maps.LatLng(14.150032, -90.843109), new google.maps.LatLng(14.150032, -90.843109), new google.maps.LatLng(14.149679, -90.843225), new google.maps.LatLng(14.149679, -90.843225), new google.maps.LatLng(14.149679, -90.843225), new google.maps.LatLng(14.149667, -90.843105), new google.maps.LatLng(14.149667, -90.843105), new google.maps.LatLng(14.149667, -90.843105), new google.maps.LatLng(14.149574, -90.843235), new google.maps.LatLng(14.149574, -90.843235), new google.maps.LatLng(14.149574, -90.843235), new google.maps.LatLng(14.149624, -90.843098), new google.maps.LatLng(14.149624, -90.843098), new google.maps.LatLng(14.149624, -90.843098), new google.maps.LatLng(14.149802, -90.843405), new google.maps.LatLng(14.149802, -90.843405), new google.maps.LatLng(14.149802, -90.843405), new google.maps.LatLng(14.149855, -90.84333), new google.maps.LatLng(14.149855, -90.84333), new google.maps.LatLng(14.149855, -90.84333), new google.maps.LatLng(14.149737, -90.843395), new google.maps.LatLng(14.149737, -90.843395), new google.maps.LatLng(14.149737, -90.843395), new google.maps.LatLng(14.149825, -90.8433), new google.maps.LatLng(14.149825, -90.8433), new google.maps.LatLng(14.149825, -90.8433), new google.maps.LatLng(14.149809, -90.843417), new google.maps.LatLng(14.149809, -90.843417), new google.maps.LatLng(14.149809, -90.843417), new google.maps.LatLng(14.14948, -90.843632), new google.maps.LatLng(14.14948, -90.843632), new google.maps.LatLng(14.14948, -90.843632), new google.maps.LatLng(14.149778, -90.843172), new google.maps.LatLng(14.149778, -90.843172), new google.maps.LatLng(14.149778, -90.843172), new google.maps.LatLng(14.149857, -90.843368), new google.maps.LatLng(14.149857, -90.843368), new google.maps.LatLng(14.149857, -90.843368), new google.maps.LatLng(14.149662, -90.843005), new google.maps.LatLng(14.149662, -90.843005), new google.maps.LatLng(14.149662, -90.843005), new google.maps.LatLng(14.149815, -90.843402), new google.maps.LatLng(14.149815, -90.843402), new google.maps.LatLng(14.149815, -90.843402), new google.maps.LatLng(14.150073, -90.843112), new google.maps.LatLng(14.150073, -90.843112), new google.maps.LatLng(14.150073, -90.843112), new google.maps.LatLng(14.150029, -90.84313), new google.maps.LatLng(14.150029, -90.84313), new google.maps.LatLng(14.150029, -90.84313)];
            console.log(objetos);

            var myLatLng = new google.maps.LatLng(14.151171, -90.841083);
            var myLatLng2 = new google.maps.LatLng(14.15009000, -90.84334708);

            var radio = 280;

            var map = new google.maps.Map(document.getElementById('map'), {
                zoom: 4,
                center: myLatLng,
                mapTypeId: 'terrain',
                zoom: 18
            });

            var alerta = new google.maps.Circle({
                strokeColor: '#FF0000',
                strokeOpacity: 0.8,
                strokeWeight: 2,
                fillColor: '#FF0000',
                fillOpacity: 0.35,
                map: map,
                center: myLatLng,
                radius: radio
            });

            function mostrarOcultarMarcador(geocerca, radioGeocerca, ubicacionValidar) {

                var distance = google.maps.geometry.spherical.computeDistanceBetween(geocerca, ubicacionValidar);
                //console.log(distance);

                if (distance <= radioGeocerca) {
                    var marker = new google.maps.Marker({
                        position: ubicacionValidar,
                        map: map,
                        title: 'Yes Show Into Radio'
                    });
                } else {
                    var marker = new google.maps.Marker({
                        position: ubicacionValidar,
                        map: map,
                        title: 'Not Show Into Radio',
                        icon: { url: "http://maps.google.com/mapfiles/ms/icons/blue-dot.png" }
                    });

                }
            }

            for (var i = 0; i <= objetos.length; i++) {
                console.log(objetos[i]);
                mostrarOcultarMarcador(myLatLng, radio, objetos[i]);
            }
        }
    </script>
    <script
        src="https://maps.googleapis.com/maps/api/js?key=AIzaSyDWtRdfntzJ_HmSEAOCeli8nhBG9x8q7iA&libraries=geometry&callback=initMap"
        async defer></script>