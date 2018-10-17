### GoogleMapsforRails
---
https://github.com/apneadiving/Google-Maps-for-Rails

```sh
gem 'gmaps4rails'
rails g gmaps4rails:copy_js
rails g gmaps4rails:copy_coffee


```

```js
//= require underscore
//= require gmaps/google


handler = Gmaps.build('Google');
handler.buildMap({ profider: {}, internal: {id: 'map'}}, function(){
  markrers = handler.addMarkers([
    {
      "lat": 0,
      "lng": 0,
      "picture": {
        "url": "http://people.mozilla.com/~faaborg/files/shiretoko/firefoxIcon/firefox-32.png",
        "width": 32,
        "height": 32
      },
      "infowindow": "hello!"
    }
  ]);
  handler.bounds.extendWidth(markers);
  handler.fitMapToBounds();
});

handler = Gmaps.buld('Google');
handler.buildMap({
  provider: {
    disableDefaultUI: true
  },
  internal: {
    id: 'map'
  }
},
function(){
  markers = handler.addMarkers([
    {
      "lat": 0,
      "lng": 0,
      "picture": {
        "url": "http://people.mozilla.com/~faaborg/files/shiretoko/firefoxIcon/firefox-32.png",
        "width": 32,
        "height": 32
      },
      "infowindow": "hello!"
    }
  ]);
  handler.bounds.extendWith(markers);
  handler.fitMapToBounds();
  }
);


```

```ruby
@users = User.all
@hash = Gmaps4rails.build_markers() do |user, marker|
  marker.lat user.latitude
  marker.lng user.longitude
end



```

```html
<div style='width: 800px;'>
  <div id="map" style='width: 800px; height: 400px;'></div>
</div>

<script src="//maps.google.com/maps/api/js?key=[your API key]"></script>
<script src="//cdn.rawgit.com/mahnunchik/markerclustererplus/master/dist/markerclusterer.min.js"></script>
<script src="//cdn.rawgit.com/printercu/google-maps-utility-library-v3-read-only/master/infobox/src/infobox_packed.js" type='text/javascript'></script>

<script>
  markers = handler.addMarkers(<%=raw @hash.to_json %>);
</script>


```
