# featureservice

A little module that extracts every feature from an Esri "geo-service". The real power in this module is it is designed to page over service and extract every single feature no matter what Server version the data are hosted on.

## Installation

```
npm install featureservice
```

## Usage 

```javascript
  var FeatureService = require('featureservice')
  
  // a url to a feature service
  var url = 'http://....../FeatureServer/0'

  var service = new FeatureService(url, options)
```

## Methods

### layerIds(callback)
Get all the ids in a feature service layer

### layerInfo(callback) 
Get the json metadata for a service layer

### statistics(field, stats, callback)
Get statistics for a field and an array of stats. 

```javascript
service.statistics('id', ['min', 'max'], function (err, stats) {
  console.log(stats.features)
})

```

### pages(callback)
Returns an array of page urls that would get every feature in the service

## Browser

A browser ready build of this module is in `dist/featureservice.min.js` and is built via the command `npm run build`

Example
```html
<html>
  <script src="dist/featureservice.min.js"></script>
  <script>
    var service = new FeatureService('http://koop.dc.esri.com/socrata/seattle/2tje-83f6/FeatureServer/0', {})
    service.statistics('id', ['max'], function (err, stats) { 
      console.log(err, stats)
    })
  </script>
</html>

```

## Todo

* Expose a stream of feature instead of page chuncks

## License

[Apache 2.0](LICENSE)

<!-- [](Esri Tags: ArcGIS Web Mapping GeoJson FeatureServices) -->
<!-- [](Esri Language: JavaScript) -->
