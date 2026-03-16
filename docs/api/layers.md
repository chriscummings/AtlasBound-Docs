# Layers

POST /v1/layers
Create a feature layer

{
"name":,
"alias":, // display name
"geometryType":point/line/poly,
"fields": [
{name:,
type:
}
]
}

{
"time": unix timestamp, int
"success": < true | false >, bool
"layerId": 6029301558047114990, int
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
