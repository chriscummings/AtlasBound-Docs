# Welcome to AtlasBound Developer Docs

GeoScope is a lightweight REST API for performing geospatial containment
queries against a library of stored geometries. It is designed for applications
that need to quickly determine whether a given point or geographic feature
falls within a named region, zone, or boundary — without the overhead of a
full GIS platform.

## Core Concept

GeoScope works by maintaining a collection of named geometry objects
(polygons, multipolygons, or complex boundary shapes) stored server-side.
Clients can then submit coordinates or GeoJSON features and query whether
they intersect with, fall within, or touch any stored geometries.

## Primary Use Cases

- Checking whether a GPS coordinate falls within a delivery zone, service area,
or administrative boundary
- Validating whether a submitted feature overlaps with restricted or protected
regions
- Powering location-aware features like geo-fencing, regional content rules, or
coverage maps

## Key Endpoints

| Endpoint | Description |
|---|---|
| [`GET /geometries`](ss) | List all stored geometry objects |
| `POST /geometries` | Store a new named geometry |
| `GET /geometries/{id}` | Retrieve a single geometry by ID |
| `POST /query/contains` | Check if a point falls within one or more geometries |
| `POST /query/intersects` | Check if a GeoJSON feature intersects stored geometries |

## Design Philosophy

GeoScope prioritizes simplicity and readability.
All geometries are stored and returned as standard GeoJSON, requests and
responses use consistent JSON structures, and errors follow a predictable
schema. It's built for developers who need spatial logic without learning
a full GIS stack.








.