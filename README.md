![Zoom previews](https://github.com/nvkelso/golden-ratio/raw/master/images/zoom_start_east_coast.png)

_Legend: Grays = zooms 10 + 11, green = 12, light green = 13, orange = 14, yellow = 15, dark orange = 16, pink = 17, dark red = 18+_

**When pre-rendering the whole world is too much, render less. But which less?**

Land versus ocean is a basic proxy. But population and internet usage should also factor in.

We proxy which tiles are important by looking at:

* Twitter Geocoded tweets
* Flickr photo sharing
* GeoIP addresses
* General population density

This first version is just for Twitter proxy.

The data you want is in:

* data/twitter_bbox.tsv

Initial version uses Twitter geotagged tweet density "binary world" bounding boxes curtsey of Eric Fischer.

http://www.flickr.com/photos/walkingsf/6159680639/in/photostream/

Later versions will include more proxies and refine the regions and country tagging. Also the ability to reference past tile view history (popularity) logs in addition to the existing forecasting ability.

For more image previews, see: http://www.flickr.com/photos/ke6cat/sets/72157629625222031/

You should see savings of 80% to 99% in which tiles get rendered from zoom 11 in.

***Example coverage:***

* Zoom 18 - Within 10 km of 70 global metros (DC but not Baltimore, SF but not San Jose, NYC but not Jersey)
* Zoom 17 - Within 20 km of 250 metros (DC and Baltimore, SF and San Jose, NYC and Jersey)
* Zoom 16 - Within 20 km of 2500 metro and micropolitan areas (picks up regional population centers like Santa Rosa CA, Harrisburg PA, Albany NY)
* Zoom 15 - Most core metro areas and their inner suburbs, bounding box area threshold
* Zoom 14 - Most core metro areas and their exurbs, bounding box area threshold
* Zoom 13 - Metro and micorpolitan areas in 12. Now less than 1% of land area.
* Zoom 12 - Most of NA, western Europe, elsewhere that are on the net. About 5% of land area and less than 2% of globe. 
* Zoom 11 - Not ocean, not unpopulated, is on the net. Ocean is about 71% of the surface: of the 29% of land, we're looking at just half of that.
* Zoom 0 through 10 - global