# @datafire/gov_bc_ca_geocoder
This gated API computes the physical locations (i.e., latitude and longitude) and correct, standardized forms of civic and non-civic addresses in British Columbia.  CORS is enabled for any domain. To request an apikey, please contact the <a href=https://forms.gov.bc.ca/databc-contact-us/  target="_blank">DataBC Help Desk</a><br>Please read our <a href=https://github.com/bcgov/api-specs/blob/master/COLLECTION_NOTICE.md#collection-notice target="_blank">data collection notice</a>

## Operation: addresses.outputFormat.get
Represents the set of geocoded and standardized sites and intersections whose address best matches a given query address.

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "addressString": {
      "type": "string",
      "description": "Examples: 525 Superior Street, Victoria, BC<br>301-780 Blanshard St, Victoria, BC<br>Johnson St and Government St, Victoria, BC.<br> Civic or intersection address as a single string. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#addressString target=\"_blank\">addressString</a>"
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "interpolation": {
      "type": "string",
      "description": "accessPoint interpolation method. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#interpolation target=\"_blank\">interpolation</a>",
      "enum": [
        "adaptive",
        "linear",
        "none"
      ]
    },
    "echo": {
      "type": "boolean",
      "description": "If true, include unmatched address details such as site name in results."
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "minScore": {
      "type": "integer",
      "description": "The minimum score required for a match to be returned. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#minScore target=\"_blank\">minScore</a>"
    },
    "matchPrecision": {
      "type": "string",
      "description": "Example: street,locality.  A comma separated list of individual match precision levels to include in results. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#matchPrecision target=\"_blank\">matchPrecision</a>"
    },
    "matchPrecisionNot": {
      "type": "string",
      "description": "Example: street,locality.  A comma separated list of individual match precision levels to exclude from results. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#matchPrecisionNot target=\"_blank\">matchPrecisionNot</a>"
    },
    "siteName": {
      "type": "string",
      "description": "A string containing the name of the building, facility, or institution (e.g., Duck Building, Casa Del Mar, Crystal Garden, Bluebird House).See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#siteName target=\"_blank\">siteName</a>"
    },
    "unitDesignator": {
      "type": "string",
      "description": "The type of unit within a house or building. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#unitDesignator target=\"_blank\">unitDesignator</a>",
      "enum": [
        "APT",
        "BLDG",
        "BSMT",
        "FLR",
        "LOBBY",
        "LWR",
        "PAD",
        "PH",
        "REAR",
        "RM",
        "SIDE",
        "SITE",
        "SUITE",
        "TH",
        "UNIT",
        "UPPR"
      ]
    },
    "unitNumber": {
      "type": "string",
      "description": "The number of the unit, suite, or apartment within a house or building."
    },
    "unitNumberSuffix": {
      "type": "string",
      "description": "A letter that follows the unit number as in Unit 1A or Suite 302B."
    },
    "civicNumber": {
      "type": "string",
      "description": "The official number assigned to a site by an address authority. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#civicNumber target=\"_blank\">civicNumber</a>"
    },
    "civicNumberSuffix": {
      "type": "string",
      "description": "A letter or fraction that follows the civic number (e.g., the A in 1039A Bledsoe St). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#civicNumberSuffix target=\"_blank\">civicNumberSuffix</a>"
    },
    "streetName": {
      "type": "string",
      "description": "The official name of the street as assigned by an address authority (e.g., the Douglas in 1175 Douglas Street). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetName target=\"_blank\">streetName</a>"
    },
    "streetType": {
      "type": "string",
      "description": "The type of street as assigned by a municipality (e.g., the ST in 1175 DOUGLAS St). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetType target=\"_blank\">streetType</a>"
    },
    "streetDirection": {
      "type": "string",
      "description": "The abbreviated compass direction as defined by Canada Post and B.C. civic addressing authorities. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetDirection target=\"_blank\">streetDirection</a>",
      "enum": [
        "N",
        "S",
        "E",
        "W",
        "O",
        "NE",
        "NO",
        "NW",
        "SE",
        "SO",
        "SW"
      ]
    },
    "streetQualifier": {
      "type": "string",
      "description": "Example: the Bridge in Johnson St Bridge. The qualifier of a street name. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetQulifier target=\"_blank\">streetQualifier</a>"
    },
    "localityName": {
      "type": "string",
      "description": "The name of the locality assigned to a given site by an address authority. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#localityName target=\"_blank\">localityName</a>"
    },
    "provinceCode": {
      "type": "string",
      "description": "The ISO 3166-2 Sub-Country Code. The code for British Columbia is BC."
    },
    "localities": {
      "type": "string",
      "description": "A comma separated list of locality names that matched addresses must belong to. For example, setting localities to Nanaimo only returns addresses in Nanaimo"
    },
    "notLocalities": {
      "type": "string",
      "description": "A comma-separated list of localities to exclude from the search."
    },
    "bbox": {
      "type": "string",
      "description": "Example: -126.0792,49.7628,-126.0163,49.7907.  A bounding box (xmin,ymin,xmax,ymax) that limits the search area. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#bbox target=\"_blank\">bbox</a>"
    },
    "centre": {
      "type": "string",
      "description": "Example: -124.01659,49.2296.  The coordinates of a centre point (x,y) used to define a bounding circle that will limit the search area. This parameter must be specified together with 'maxDistance'. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#centre target='_blank'>centre</a>"
    },
    "maxDistance": {
      "type": "number",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "extrapolate": {
      "type": "boolean",
      "description": "If true, uses supplied parcelPoint to derive an appropriate accessPoint.           See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#extrapolate target=\"_blank\">extrapolate</a>"
    },
    "parcelPoint": {
      "type": "string",
      "description": "The coordinates of a point (x,y) known to be inside the parcel containing a given address. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#parcelPoint target=\"_blank\">parcelPoint</a>"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: intersections.near.outputFormat.get
Represents intersections near a given point

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  The point (x,y) from which the nearest site will be identified. The coordinates must be specified in the same SRS as given by the 'outputSRS' parameter."
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "minDegree": {
      "type": "integer",
      "description": "The minimum degree an intersection can have to be included in results. A dead-end has a degree of 1."
    },
    "maxDegree": {
      "type": "integer",
      "description": "The maximum degree an interesection can have to be included in results. A four-way stop has a degree of 4."
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point",
    "outputSRS"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: intersections.nearest.outputFormat.get
Represents the closest intersection to a given point

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  The point (x,y) from which the nearest site will be identified. The coordinates must be specified in the same SRS as given by the 'outputSRS' parameter."
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "minDegree": {
      "type": "integer",
      "description": "The minimum degree an intersection can have to be included in results. A dead-end has a degree of 1."
    },
    "maxDegree": {
      "type": "integer",
      "description": "The maximum degree an interesection can have to be included in results. A four-way stop has a degree of 4."
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: intersections.within.outputFormat.get
Represents all intersections within a given area

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormattarget=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "bbox": {
      "type": "string",
      "description": "Example: -119.51,49.48,-119.53,49.50. A bounding box (xmin,ymin,xmax,ymax) used to limit the search area. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#bbox target=\"_blank\">bbox</a>"
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results"
    },
    "minDegree": {
      "type": "integer",
      "description": "The minimum degree an intersection can have to be included in results. A dead-end has a degree of 1."
    },
    "maxDegree": {
      "type": "integer",
      "description": "The maximum degree an interesection can have to be included in results. A four-way stop has a degree of 4."
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "bbox"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: intersections.intersectionID.outputFormat.get
Represents a individual intersection

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "intersectionID": {
      "type": "string",
      "description": "A unique intersection identifier"
    },
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    }
  },
  "additionalProperties": false,
  "required": [
    "intersectionID",
    "outputFormat"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: occupants.addresses.outputFormat.get
Represents the set of occupants whose addresses best match a given query address. Every occupant has an associated site which has a standardized address and a coordinate location on the Earth.

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "addressString": {
      "type": "string",
      "description": "Examples: Redfish Elementary --<br>Redfish Elementary -- Balfour<br>Redfish Elementary School -- 265 Bryan Rd, Balfour, BC<br>Occupant name followed by a frontGate delimiter ('--') followed by an optional address"
    },
    "tags": {
      "type": "string",
      "description": "Example: schools;courts;employment<br>A list of tags separated by semicolons."
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "interpolation": {
      "type": "string",
      "description": "accessPoint interpolation method. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#interpolation target=\"_blank\">interpolation</a>",
      "enum": [
        "adaptive",
        "linear",
        "none"
      ]
    },
    "echo": {
      "type": "boolean",
      "description": "If true, include unmatched address details such as site name in results."
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "minScore": {
      "type": "integer",
      "description": "The minimum score required for a match to be returned. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#minScore target=\"_blank\">minScore</a>"
    },
    "matchPrecision": {
      "type": "string",
      "description": "Example: street,locality.  A comma separated list of individual match precision levels to include in results. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#matchPrecision target=\"_blank\">matchPrecision</a>"
    },
    "matchPrecisionNot": {
      "type": "string",
      "description": "Example: street,locality.  A comma separated list of individual match precision levels to exclude from results. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#matchPrecisionNot target=\"_blank\">matchPrecisionNot</a>"
    },
    "siteName": {
      "type": "string",
      "description": "A string containing the name of the building, facility, or institution (e.g., Duck Building, Casa Del Mar, Crystal Garden, Bluebird House).See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#siteName target=\"_blank\">siteName</a>"
    },
    "unitDesignator": {
      "type": "string",
      "description": "The type of unit within a house or building. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#unitDesignator target=\"_blank\">unitDesignator</a>",
      "enum": [
        "APT",
        "BLDG",
        "BSMT",
        "FLR",
        "LOBBY",
        "LWR",
        "PAD",
        "PH",
        "REAR",
        "RM",
        "SIDE",
        "SITE",
        "SUITE",
        "TH",
        "UNIT",
        "UPPR"
      ]
    },
    "unitNumber": {
      "type": "string",
      "description": "The number of the unit, suite, or apartment within a house or building."
    },
    "unitNumberSuffix": {
      "type": "string",
      "description": "A letter that follows the unit number as in Unit 1A or Suite 302B."
    },
    "civicNumber": {
      "type": "string",
      "description": "The official number assigned to a site by an address authority. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#civicNumber target=\"_blank\">civicNumber</a>"
    },
    "civicNumberSuffix": {
      "type": "string",
      "description": "A letter or fraction that follows the civic number (e.g., the A in 1039A Bledsoe St). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#civicNumberSuffix target=\"_blank\">civicNumberSuffix</a>"
    },
    "streetName": {
      "type": "string",
      "description": "The official name of the street as assigned by an address authority (e.g., the Douglas in 1175 Douglas Street). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetName target=\"_blank\">streetName</a>"
    },
    "streetType": {
      "type": "string",
      "description": "The type of street as assigned by a municipality (e.g., the ST in 1175 DOUGLAS St). See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetType target=\"_blank\">streetType</a>"
    },
    "streetDirection": {
      "type": "string",
      "description": "The abbreviated compass direction as defined by Canada Post and B.C. civic addressing authorities. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetDirection target=\"_blank\">streetDirection</a>",
      "enum": [
        "N",
        "S",
        "E",
        "W",
        "O",
        "NE",
        "NO",
        "NW",
        "SE",
        "SO",
        "SW"
      ]
    },
    "streetQualifier": {
      "type": "string",
      "description": "The qualifier of a street name (e.g., the Bridge in Johnson St Bridge)"
    },
    "localityName": {
      "type": "string",
      "description": "The name of the locality assigned to a given site by an address authority. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#streetDirection target=\"_blank\">streetDirection</a>"
    },
    "provinceCode": {
      "type": "string",
      "description": "The ISO 3166-2 Sub-Country Code. The code for British Columbia is BC."
    },
    "localities": {
      "type": "string",
      "description": "A comma separated list of locality names that matched addresses must belong to. For example, setting localities to Nanaimo only returns addresses in Nanaimo"
    },
    "notLocalities": {
      "type": "string",
      "description": "A comma-separated list of localities to exclude from the search."
    },
    "bbox": {
      "type": "string",
      "description": "Example: -126.07929,49.7628,-126.0163,49.7907.  A bounding box (xmin,ymin,xmax,ymax) that limits the search area. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#bbox target=\"_blank\">bbox</a>"
    },
    "centre": {
      "type": "string",
      "description": "Example: -124.0165,49.2296.  The coordinates of a centre point (x,y) used to define a bounding circle that will limit the search area. This parameter must be specified together with 'maxDistance'. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#centre target='_blank'>centre</a>"
    },
    "maxDistance": {
      "type": "number",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "extrapolate": {
      "type": "boolean",
      "description": "If true, uses supplied parcelPoint to derive an appropriate accessPoint.           See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#extrapolate target=\"_blank\">extrapolate</a>"
    },
    "parcelPoint": {
      "type": "string",
      "description": "The coordinates of a point (x,y) known to be inside the parcel containing a given address. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#parcelPoint target=\"_blank\">parcelPoint</a>"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: occupants.near.outputFormat.get
Represents occupants near a given point in order of closest to farthest

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  The point (x,y) from which the nearest site will be identified. The coordinates must be specified in the same SRS as given by the 'outputSRS' parameter."
    },
    "tags": {
      "type": "string",
      "description": "Example: schools;courts;employment<br>A list of tags separated by semicolons."
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "excludeUnits": {
      "type": "boolean",
      "description": "If true, excludes sites that are units of a parent site"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: occupants.nearest.outputFormat.get
Represents the closest occupant to a given point

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  The point (x,y) from which the nearest site will be identified. The coordinates must be specified in the same SRS as given by the 'outputSRS' parameter."
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "tags": {
      "type": "string",
      "description": "Example: schools;courts;employment<br>A list of tags separated by semicolons."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: occupants.within.outputFormat.get
Represents all occupants within a given area

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "bbox": {
      "type": "string",
      "description": "Example: -119.51,49.48,-119.53,49.50. A bounding box (xmin,ymin,xmax,ymax) used to limit the search area. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#bbox target=\"_blank\">bbox</a>"
    },
    "tags": {
      "type": "string",
      "description": "Example: schools;courts;employment<br>A list of tags separated by semicolons."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "bbox"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: occupants.occupantID.outputFormat.get
Represents an individual occupant

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "occupantID": {
      "type": "string",
      "description": "Occupant identifier"
    },
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    }
  },
  "additionalProperties": false,
  "required": [
    "occupantID",
    "outputFormat"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: sites.near.outputFormat.get
Represents sites near a given point in the order of closest to farthest

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  The point (x,y) from which the nearby sites will be identified. The coordinates must be specified in the same SRS as given by the 'outputSRS' parameter."
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "excludeUnits": {
      "type": "boolean",
      "description": "If true, excludes sites that are units of a parent site"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: sites.nearest.outputFormat.get
Represents the site nearest a given point

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "point": {
      "type": "string",
      "description": "Example: -122.377,50.121  Centre point of search. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#point target=\"_blank\">point</a>"
    },
    "maxDistance": {
      "type": "integer",
      "description": "The maximum distance (in metres) to search from the given point.  If not specified, the search distance is unlimited."
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "excludeUnits": {
      "type": "boolean",
      "description": "If true, excludes sites that are units of a parent site"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "point"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: sites.within.outputFormat.get
Represents sites within a given area

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "bbox": {
      "type": "string",
      "description": "Example: -119.51,49.48,-119.53,49.50. A bounding box (xmin,ymin,xmax,ymax) used to limit the search area. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#bbox target=\"_blank\">bbox</a>"
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "maxResults": {
      "type": "integer",
      "description": "The maximum number of search results to return."
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    },
    "excludeUnits": {
      "type": "boolean",
      "description": "If true, excludes sites that are units of a parent site"
    }
  },
  "additionalProperties": false,
  "required": [
    "outputFormat",
    "bbox"
  ]
}
```
### Output Schema
```json
{}
```
## Operation: sites.siteID.outputFormat.get
Represents an individual site

### Input Schema
```json
{
  "type": "object",
  "properties": {
    "siteID": {
      "type": "string",
      "description": "A unique, but not immutable, site identifier."
    },
    "outputFormat": {
      "type": "string",
      "description": "Results format. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputFormat target=\"_blank\">outputFormat</a>",
      "enum": [
        "json",
        "geojson",
        "xhtml",
        "kml",
        "gml",
        "csv",
        "shpz"
      ]
    },
    "outputSRS": {
      "type": "integer",
      "description": "The EPSG code of the spatial reference system (SRS) to use for output geometries. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#outputSRS target=\"_blank\">outputSRS</a>",
      "enum": [
        4326,
        4269,
        3005,
        26907,
        26908,
        26909,
        26910,
        26911
      ]
    },
    "locationDescriptor": {
      "type": "string",
      "description": "Describes the nature of the address location. See <a href=https://github.com/bcgov/api-specs/blob/master/geocoder/glossary.md#locationDescriptor target=\"_blank\">locationDescriptor</a>",
      "enum": [
        "any",
        "accessPoint",
        "frontDoorPoint",
        "parcelPoint",
        "rooftopPoint",
        "routingPoint"
      ]
    },
    "setBack": {
      "type": "integer",
      "description": "The distance to move the accessPoint away from the curb and towards the inside of the parcel (in metres). Ignored if locationDescriptor not set to accessPoint."
    }
  },
  "additionalProperties": false,
  "required": [
    "siteID",
    "outputFormat"
  ]
}
```
### Output Schema
```json
{}
```