# google.maps.Polygon.moveTo()

Move a Polygon on Google Maps V3 to a new LatLng()
Built by Bramus! - [http://www.bram.us/](http://www.bram.us/)


## About

`google.maps.Polygon.moveTo()` is a Google Maps extension allowing one to programmatically move a `google.maps.Polygon` on the map without any user/mouse interaction. Works with both geodesic _(polygons that follow the curvature of the earth)_ and non-geodesic _(straight)_ polygons.


## Installation

* Include the scripts `js/google.maps.Polygon.getBounds.js` and `js/google.maps.Polygon.moveTo.js` in your HTML page
* Include the Google Maps script with the [Google Maps Geometry Library](https://developers.google.com/maps/documentation/javascript/geometry) included. You can do this by referencing `http://maps.googleapis.com/maps/api/js?v=3.exp&sensor=false&libraries=geometry`


## How to use

See the example. Basically just call `myPolygon.moveTo(new google.maps.LatLng(lat, lng))` to move the Polygon to the new Latitude/Longitude.


## Notes / Bugs

* Alas it's not perfect: Rounding errors occur _(You can see this best when moving a polygon with `geodesic` enabled to one location and then moving it back: you'll see that the shape seems to have tilted a bit)_
* It doesn't play nice (yet) with Polygons consisting of multiple paths
* When using non-geodesic polygons it's recommened to wrap `google.maps.Polygon#moveTo()` in a `setTimeout()` with a timing of `200` in order to have `google.maps.Map#getProjection()` available _(it's only available after the map has started rendering)_