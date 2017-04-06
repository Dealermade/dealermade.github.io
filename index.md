# Media Layer API

```html
<script src="//dealermade.com/assets/media-layer/v2/dm.js" 
data-dm-dealership-id="DEALERMADE DEALERSHIP ID" 
data-dm-vehicle-vin="VEHICLE VIN"></script>
```

The above script will insert the media layer next to the script tag.

Required attributes of script tag:
* **src**: currently _must_ point to: //dealermade.com/assets/media-layer/v2/dm.js   
* **data-dm-dealership-id**: Unique Dealership ID.
* **data-dm-vehicle-vin**: Full vin number of vehicle to display pictures for.

By default, the media layer will be placed in the same element as the script tag. However, the media layer can be displayed in a different area, with the folliwing placement attributes:
* **data-dm-replace-element-id**: One element id to replace with the media layer
* **data-dm-insert-before-element-id**: One element id where the media layer will insert before
* **data-dm-insert-after-element-id**: One element id where the media layer will insert after
* **data-dm-insert-before-element-attribute**: One element attribute to find and insert the media layer before, for example: data-widget-id  **[optional]**.
* **data-dm-insert-before-element-attribute-value**: One element attribute value that matches data-dm-insert-before-element-attribute and _must be used with_ data-dm-insert-before-element-attribute.  For example the following value of: inventory-detail1 used with the above example of "data-widget-id" would find all html tags with data-widget-id="inventory-detail1" and insert the media layer above it.      **[optional]**.
* **data-dm-insert-after-element-attribute**: One element attribute to find and insert the media layer after, for example: data-widget-id  **[optional]**.
* **data-dm-insert-after-element-attribute-value**: One element attribute value that matches data-dm-insert-after-element-attribute and _must be used with_ data-dm-insert-after-element-attribute.  For example the following value of: inventory-detail1 used with the above example of "data-widget-id" would find all html tags with data-widget-id="inventory-detail1" and insert the media layer after it. **[optional]**.

Other optional attributes:
* **data-dm-element-ids-to-hide**: One or many element ids separated by a " " space character that will be hidden when the media layer and the corresponding vehicle pictures are loaded
* **data-dm-force-hd**: In this mode, the standard media layer will not be displayed at all, and the HD media layer will automatically load. _Note: the user will be unable to exit the HD media layer other than by closing the page. Only use this attribute on pages in which you intend to show the media layer exclusively_
* **data-dm-manual-hd**: In this mode, if this attribute is set to "yes", the standard media layer will not be displayed at all. The HD media layer can be manually triggered by calling the function `triggerHdMediaLayer()`. So, for instance, you may add a button to the page with an onclick event that triggers the HD media layer, like so: `<button onclick="triggerHdMediaLayer()">Click Me</button>`. Unlike with data-dm-force-hd, the user will be able to exit the HD media layer. Alternately, if this attribute is set to "button", a pre-styled "Launch HD Media Layer" button will appear in place of the media layer.

### The media layer will remain invisible until pictures have been taken for the vehicle using the dealermade photo studio, also the element ids listed in data-dm-element-ids-to-hide will not be hidden unless the media layer has loaded with pictures.

### Example Media Layer Implementation:

```html
<script src="//dealermade.com/assets/media-layer/v2/dm.js" 
data-dm-dealership-id="team-of-navasota" 
data-dm-vehicle-vin="1FTEW1EF4FFA24461"
data-dm-replace-element-id="vpActualContent"
data-dm-element-ids-to-hide="dtlExpand dtlExpand2"></script>
```


# Thumbnail API

We currently have two alternatives for a thumbnail API:

1. Thumbnail Image URL API
2. Thumbnail JavaScript API

Please choose the API that is most convenient for you.

## 1. Thumbnail Image URL API
```html
http://dealermade.com/api/1/dealerships/DEALERMADE DEALERSHIP ID/vehicles/VEHICLE VIN/images/PICTURE SIZE.jpg?default_image_url=[your image url for the vehicle goes here]
```

Required parameters in the image url:
* **DEALERMADE DEALERSHIP ID**: Unique Dealership ID .
* **VEHICLE VIN**: Full vin number of vehicle to display pictures for.
* **PICTURE SIZE**: One of the following standard Dealermade picture size names(medium, preview, large, etc.) Ex: preview.jpg.
  * **large** 1500w x 1000h
  * **medium** 800w x 533h
  * **main** 640w x 427h
  * **preview** 200w x 133h
* **[your image url for the vehicle goes here]**: Url Encoded default image thumbnail for that vehicle.  This will be used if pictures have not yet been taken using the Dealermade Photo Studio (also without brackets).

### Example Thumbnail Image API Implementation:

```html
<img src="//dealermade.com/api/1/dealerships/team-of-navasota/vehicles/1FTFW1ET3DKD06282/images/preview.jpg?default_image_url=http%3A%2F%2Ftagoreimg.d2fs.net%2Fimg%2Fused%2Fford%2Ff-150%2F1ftfw1et3dkd06282%2F3777d222-6258-4cf3-b694-6d6acd014c01.jpeg%3Fw%3D160%26h%3D120"/>
```

## 2. Thumbnail JavaScript API

To add our thumbnail javascript API, just add our javascript tag to any page that have thumbnails:

```html
<script data-dealership-id="DEALERMADE DEALERSHIP ID" src="//dealermade.com/assets/thumbnails/v1/api.js">
</script>
```
* **[DEALERMADE DEALERSHIP ID]**: Unique Dealership ID.

And add the data-thumbnail-vin html attribute populated with the vehicle vin to any image tags for vehicles.

```html
<img src="Your image url here" data-thumbnail-vin="VEHICLE VIN HERE">
```




### Support - Having trouble with our media layer? 
Please contact us at (888) 403-9143.
