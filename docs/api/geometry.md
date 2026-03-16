# Geometry Management

https://developers.arcgis.com/rest/services-reference/enterprise/geometry-objects/



**POST /v1/geometries**
Create and validate a geometry.

{
"layerId":
"geojson":
{
   "type": "FeatureCollection",
   "features": [
	{
	   "type": "Feature",
	   "geometry": {
		   "type": "Polygon",
		   "coordinates": [
			   [
				   [100.0, 0.0],
				   [101.0, 0.0],
				   [101.0, 1.0],
				   [100.0, 1.0],
				   [100.0, 0.0]
			   ]
		   ]
	   },
	   "properties": {
		   "address": "11TH ST and HARRISON ST",
		   "district": "6"
	   }
	 }
   ]
}
}


{
"time": unix timestamp, int
"success": < true | false >, bool
"objectId": 6029301558047114990, int
}

{
"time":
"success": false,
"error": { //only if success is false
	"code": -2147217395,
	"ref id":,
	"description": "Setting of Value for depth failed."
	}
}

**GET /v1/geometries/{geometry_id}**
Retrieve a stored geometry.

6029301558047114990
geojson



### Geometries

----

Describe a Geometry

## Create a Geometry Resource


```urlencoded
POST v1/geometries
```


=== "Schema"

	| Attribute   | Type    | Description                         |
	| ----------- | -       |-----------------------------------  |
	| `layer`     | String  |Target layer ID.                     |
	| `geojson`   | GeoJSON |Geometries to append to target layer.|

=== "Example JSON"

    ```json hl_lines="2 3"
	{
		"layer": "adadadadadad",
		"geojson": {
			"type": "FeatureCollection",
			"features": [
				{
					"type": "Feature",
					"geometry": {
						"type": "Polygon",
						"coordinates": [
							[
								[100.0, 0.0],
								[101.0, 0.0],
								[101.0, 1.0],
								[100.0, 1.0],
								[100.0, 0.0]
							]
						]
					},
					"properties": {
						"address": "11TH ST and HARRISON ST",
						"district": "6"
					}
				}
			]
		}
	}
	```

### Responses

#### Success

```json
{
	"time": 1768885260,
	"success": true,
	"objectId": 6029301558047114990 // Only if success is true
}
```


#### Error

```json
{
	"time": 1768885260,
	"success": false,
	"error": { // Only if success is false
		"code": 777,
		"refId": 15580471558047,
		"description": "Invalid coordinates for geometry type Polygon."
	}
}
```

## Fetch a Geometry Resource

```urlencoded
GET /v1/geometries/{objectId}
```


=== "Schema"

	| Attribute   | Type    | Description                         |
	| ----------- | -       |-----------------------------------  |
	| `objectId`  | Integer  | ObjectId for target geometry.      |

=== "Example JSON"

    ```json hl_lines="2"
	{
		"objectId": 6029301558047114990,
	}
	```


### Responses

#### Success

```json
{
	"time": 1768885260,
	"objectId": 6029301558047114990,
	"layerId": 558055804443,
	"geojson": {
		"type": "FeatureCollection",
		"features": [
			{
				"type": "Feature",
				"geometry": {
					"type": "Polygon",
					"coordinates": [
						[
							[100.0, 0.0],
							[101.0, 0.0],
							[101.0, 1.0],
							[100.0, 1.0],
							[100.0, 0.0]
						]
					]
				},
				"properties": {
					"address": "11TH ST and HARRISON ST",
					"district": "6"
				}
			}
		]
	}
}
```



#### Error

```json
{
	"time": 1768885260,
	"success": false,
	"error": { // Only if success is false
		"code": 877,
		"refId": 15580471558047,
		"description": "Geometry not found by objectId 6029301558047114990"
	}
}
```
