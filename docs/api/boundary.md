# Spatial Queries


**GET /v1/boundaries/lookup**

Find which boundaries contain a point.

{
lat:,
lon:,
layers:[] optional
}



## Spatial Queries (Synchronous)

**POST /v1/queries/contains**
Check which features contain a geometry.

**POST /v1/queries/intersects**
Find features that intersect a geometry.

**GET /v1/boundaries/lookup**

Find which boundaries contain a point.

{
lat:,
lon:,
layers:[] optional
}
