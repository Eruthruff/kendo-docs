---
title: kendo.dataviz.ui.Map
meta_title: Configuration, methods and events of Kendo UI DataViz Map
meta_description: Learn how to configure Kendo UI Javascript chart widget in a few easy steps, use and change methods and events.
slug: api-dataviz-map
relatedDocs: gs-dataviz-map-overview
tags: api,dataviz,map,maps,spatial,geoviz
publish: true
---

# kendo.dataviz.ui.Map

## Configuration

### center `Array|kendo.dataviz.map.Location`

The map center. Coordinates are listed as `[Latitude, Longitude]`.

#### Example - setting the map center
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            center: [30.268107, -97.744821],
            zoom: 3,
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls `Object`

The configuration of built-in map controls.

#### Example - hide all controls
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                attribution: false,
                navigator: false
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls.attribution `Boolean` *(default: true)*

Enables or disables the built-in attribution control.

#### Example - hide the attribution control
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                attribution: false
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls.navigator `Boolean|Object` *(default: true)*

Enables or disables the built-in navigator control (directional pad).

#### Example - hide the navigator control
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                navigator: false
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls.navigator.position `String` *(default: "topLeft")*

The position of the navigator control. Possible values include:

* "topLeft"
* "topRight"
* "bottomRight"
* "bottomLeft"

#### Example - position the navigator control
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                navigator: {
                    position: "topRight"
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls.zoom `Boolean|Object` *(default: true)*

Enables or disables the built-in zoom control (+/- button).

#### Example - hide the zoom control
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                zoom: false
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### controls.zoom.position `String` *(default: "topLeft")*

The position of the zoom control. Possible values include:

* "topLeft"
* "topRight"
* "bottomRight"
* "bottomLeft"

#### Example - position the zoom control
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                zoom: {
                    position: "topRight"
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layerDefaults `Object`

The default configuration for map layers by type.

#### Example - set tile layer defaults
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    opacity: 0.5
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layerDefaults.shape `Object`

The default configuration for shape layers.

#### Example
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            controls: {
                navigator: {
                    position: "topRight"
                }
            },
            layerDefaults: {
                shape: {
                    attribution: "&copy; Company Inc."
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.attribution `String`

The attribution for all shape layers.

#### Example - set default attribution for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    attribution: "&copy; Company Inc."
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style `Object`

The default style for shapes.

#### Example - Set default style for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        fill: {
                            color: "red",
                            opacity: 1
                        },
                        stroke: {
                            color: "green",
                            width: 4,
                            dashType: "longDashDot",
                            opacity: 0.5
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.fill `Object`

The default fill for layer shapes.
Accepts a valid CSS color string or object with detailed configuration.

#### Example - Set default fill for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        fill: {
                            color: "red",
                            opacity: 1
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.fill.color `String`

The default fill color for layer shapes.
Accepts a valid CSS color string, including hex and rgb.

#### Example - Set default fill color for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        fill: {
                            color: "red"
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.fill.opacity `Number`

The default fill opacity (0 to 1) for layer shapes.

#### Example - Set default fill with opacity for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        fill: {
                            color: "red",
                            opacity: 1
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.stroke `Object`

The default stroke for layer shapes.
Accepts a valid CSS color string or object with detailed configuration.

#### Example - Set default stroke for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        stroke: {
                            color: "green",
                            width: 4,
                            dashType: "longDashDot",
                            opacity: 0.5
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.stroke.color `String`

The default stroke color for layer shapes.
Accepts a valid CSS color string, including hex and rgb.

#### Example - Set default stroke color for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        stroke: {
                            color: "green"
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.stroke.dashType `String` *(default: "solid")*

The default dash type for layer shapes.
The following dash types are supported:

* "dash" - a line consisting of dashes
* "dashDot" - a line consisting of a repeating pattern of dash-dot
* "dot" - a line consisting of dots
* "longDash" - a line consisting of a repeating pattern of long-dash
* "longDashDot" - a line consisting of a repeating pattern of long-dash-dot
* "longDashDotDot" - a line consisting of a repeating pattern of long-dash-dot-dot
* "solid" - a solid line

#### Example - Set default dashed stroke for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        stroke: {
                            width: 4,
                            dashType: "longDashDot"
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.stroke.opacity `Number`

The default stroke opacity (0 to 1) for layer shapes.

#### Example - Set default stroke with opacity for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        stroke: {
                            width: 4,
                            opacity: 0.5
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.shape.style.stroke.width `Number` *(default: 1)*

The default stroke width for layer shapes.

#### Example - Set default stroke width for all shape layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                shape: {
                    style: {
                        stroke: {
                            width: 4
                        }
                    }
                }
            },
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layerDefaults.tile `Object`

The default configuration for tile layers.

#### Example - set default options for all tile layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    opacity: 0.8,
                    attribution: "&copy; OpenStreetMap"
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png"
            }]
        });
    </script>

### layerDefaults.tile.urlTemplate `String`

The URL template for tile layers. Template variables:

* x - X coordinate of the tile
* y - Y coordinate of the tile
* zoom - zoom level
* subdomain - Subdomain for this tile. See [subdomains](#configuration-layers-tile-subdomains)

#### Example - set default URL template for all tile layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                    attribution: "&copy; OpenStreetMap"
                }
            },
            layers: [{
                type: "tile"
            }]
        });
    </script>

### layerDefaults.tile.attribution `String`

The attribution of all tile layers.

#### Example - set default attribution for all tile layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    attribution: "&copy; OpenStreetMap"
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png"
            }]
        });
    </script>

### layerDefaults.tile.subdomains `Array`

The subdomain of all tile layers.

#### Example - set subdomains for all tile layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    subdomains: ["a", "b", "c"]
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://#= subdomain #.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layerDefaults.tile.opacity `String` *(default: 1)*

The the opacity of all tile layers.

#### Example - set tile layer default opacity
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layerDefaults: {
                tile: {
                    opacity: 0.5
                }
            },
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layers `Array`

The configuration of the map layers.
The layer type is determined by the value of the type field.

#### Example - configure map layers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }, {
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.autoBind `Boolean` *(default: true)*

If set to `false` the layer will not bind to the data source during initialization. In this case data binding will occur when the [change](/api/framework/datasource#events-change) event of the
data source is fired. By default the widget will bind to the data source specified in the configuration.

> Setting `autoBind` to `false` is useful when multiple layers (widgets) are bound to the same data source. Disabling automatic binding ensures that the shared data source doesn't make more than one request to the remote service.

#### Example - using manual binding
    <div id="map"></div>
    <script>
        var ds = new kendo.data.DataSource({
            type: "geojson",
            data: [{
                "type": "Polygon",
                "coordinates": [
                    [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                ]
            }]
        });

        $("#map").kendoMap({
            layers: [{
                type: "shape",
                autoBind: false,
                dataSource: ds
            }]
        });

        ds.read();
    </script>

### layers.type `String`

The layer type. Supported types are:

* "tile" - a generic "slippy map" tile layer
* "shape" - a vector shape layer, e.g. bound to GeoJSON data

#### Example - creating a tile layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layers.dataSource `Object|Array|kendo.data.DataSource`

The data source of the layer. Can be a JavaScript object which represents a valid data source configuration, a JavaScript array or an existing [kendo.data.DataSource](/api/framework/datasource)
instance.

#### Example - binding to inline GeoJSON data
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

#### Example - binding to existing data source
    <div id="map"></div>
    <script>
        var ds = new kendo.data.DataSource({
            type: "geojson",
            data: [{
                "type": "Polygon",
                "coordinates": [
                    [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                ]
            }]
        });

        $("#map").kendoMap({
            layers: [{
                type: "shape",
                dataSource: ds
            }]
        });
    </script>

### layers.attribution `String`

The attribution for the layer. Accepts valid HTML.

#### Example - set attribution text
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layers.subdomains `Array`

A list of subdomains to use for loading tiles.
Alternating between different subdomains allows more requests to be executed in parallel.

#### Example - setting subdomains for OpenStreetMap tiles
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://#= subdomain #.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                subdomains: ["a", "b", "c"],
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layers.opacity `String` *(default: 1)*

The the opacity for the layer.

#### Example - setting layer opacity
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                opacity: 0.5,
                urlTemplate: "http://#= subdomain #.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                subdomains: ["a", "b", "c"],
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### layers.style `Object`

The default style for shapes.

#### Example - setting style for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    fill: {
                        color: "red",
                        opacity: 1
                    },
                    stroke: {
                        color: "green",
                        width: 4,
                        dashType: "longDashDot",
                        opacity: 0.5
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.fill `Object`

The default fill for layer shapes.
Accepts a valid CSS color string or object with detailed configuration.

#### Example set shape fill
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    fill: {
                        color: "red",
                        opacity: 1
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.fill.color `String`

The default fill color for layer shapes.
Accepts a valid CSS color string, including hex and rgb.

#### Example - setting fill color for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    fill: {
                        color: "red"
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.fill.opacity `Number`

The default fill opacity (0 to 1) for layer shapes.

#### Example - setting fill opacity for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    fill: {
                        color: "red",
                        opacity: 0.5
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.stroke `Object`

The default stroke for layer shapes.
Accepts a valid CSS color string or object with detailed configuration.

#### Example - setting stroke style for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    stroke: {
                        color: "green",
                        width: 4,
                        dashType: "longDashDot",
                        opacity: 0.5
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.stroke.color `String`

The default stroke color for layer shapes.
Accepts a valid CSS color string, including hex and rgb.

#### Example - setting stroke color for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    stroke: {
                        color: "green",
                        width: 4
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.stroke.dashType `Number` *(default: 1)*

The default dash type for layer shapes.
The following dash types are supported:

* "dash" - a line consisting of dashes
* "dashDot" - a line consisting of a repeating pattern of dash-dot
* "dot" - a line consisting of dots
* "longDash" - a line consisting of a repeating pattern of long-dash
* "longDashDot" - a line consisting of a repeating pattern of long-dash-dot
* "longDashDotDot" - a line consisting of a repeating pattern of long-dash-dot-dot
* "solid" - a solid line

#### Example - setting stroke dash type for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    stroke: {
                        width: 4,
                        dashType: "longDashDot"
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.stroke.opacity `Number`

The default stroke opacity (0 to 1) for layer shapes.

#### Example - setting stroke opacity for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    stroke: {
                        width: 4,
                        opacity: 0.5
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.style.stroke.width `Number` *(default: 1)*

The default stroke width for layer shapes.

#### Example - setting stroke width for shape layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "shape",
                style: {
                    stroke: {
                        width: 4
                    }
                },
                dataSource: {
                    type: "geojson",
                    data: [{
                        "type": "Polygon",
                        "coordinates": [
                            [[30, 10], [40, 40], [20, 40], [10, 20], [30, 10]]
                        ]
                    }]
                }
            }]
        });
    </script>

### layers.urlTemplate `String`

The URL template for tile layers. Template variables:

* x - X coordinate of the tile
* y - Y coordinate of the tile
* zoom - zoom level
* subdomain - Subdomain for this tile. See [subdomains](#configuration-layers-tile-subdomains)

#### Example - setting URL template for tile layer
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://#= subdomain #.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                subdomains: ["a", "b", "c"],
                attribution: "&copy; OpenStreetMap"
            }]
        });
    </script>

### markerDefaults `Object`

The default options for all markers.

#### Example - setting default shape for all markers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                shape: "pin"
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.shape `String` *(default: "pinTarget")*

The default marker shape. The following pre-defined marker shapes are available:

* pinTarget
* pin

Marker shapes are implemented as CSS classes on the marker element (span.k-marker).
For example "pinTarget" is rendered as "k-marker-pin-target".

#### Example - setting default shape for all markers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                shape: "pin"
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip `Object`

Default Kendo UI Tooltip options for this marker.

### markerDefaults.tooltip.autoHide `Boolean`*(default: false)*

Specifies if the tooltip will be hidden when mouse leaves the target element. If set to false a close button will be shown within tooltip. If set to false, showAfter is specified and the showOn is set to "mouseenter" the Tooltip will be displayed after the given timeout even if the element is no longer hovered.

#### Example - hide tooltip on mouse leave
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    autoHide: true
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation `Object`

A collection of {Animation} objects, used to change default animations. A value of **false**
will disable all animations in the widget.

#### Example - disable animations
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: false
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.close `Object`

The animation that will be used when a Tooltip closes.

#### Example - set close animation
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                      close: {
                        effects: "fade:out"
                      }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.close.effects `String`

Effect to be used for closing of the tooltip.

#### Example - set close animation effect
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                        close: {
                            effects: "fade:out"
                        }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.close.duration `Number`

Defines the animation duration.

#### Example - set close animation duration
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                        close: {
                            duration: 1000
                        }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.open `Object`

The animation that will be used when a Tooltip opens.

#### Example - set open animation
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                        open: {
                            effects: "fade:in",
                            duration: 1000
                        }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.open.effects `String`

Effect to be used for opening of the Tooltip.

#### Example - set open animation effect
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                        open: {
                            effects: "fade:in"
                        }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.animation.open.duration `Number`

Defines the animation duration.

#### Example - set open animation duration
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    animation: {
                        open: {
                            duration: "1000"
                        }
                    }
                }
            },
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }, {
                location: [40, 20],
                tooltip: {
                    content: "Bar"
                }
            }]
        });
    </script>

### markerDefaults.tooltip.content `Object|String|Function`

The text or a function which result will be shown within the tooltip.
By default the tooltip will display the target element title attribute content.

#### Example - extract the content from target marker
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    content: function(e) {
                        var marker = e.sender.marker;
                        return marker.options.location.toString();
                    }
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

#### Example - content as static text
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.content.url `String`

Specifies a URL or request options that the tooltip should load its content from.

>Note: For URLs starting with a protocol (e.g. http://),
a container iframe element is automatically created. This behavior may change in future
versions, so it is advisable to always use the [iframe configuration option](#iframe).

#### Example - load content from remote URL
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                      content: {
                        url: "http://demos.kendoui.com/content/web/tooltip/ajax/ajaxContent3.html"
                      },
                      width: 220,
                      height: 280
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.template `String|Template`

The [template](/api/framework/kendo#methods-template) which renders the tooltip content.

The fields which can be used in the template are:

* location - the marker location (kendo.dataviz.map.Location instance)
* marker - the marker instance

> Setting a template disables the content option.

#### Example - set tooltip template
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    template: "Lon:#= location.lng #, Lat:#= location.lat #"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.callout `Boolean`*(default:true)*

Specifies if the tooltip callout will be displayed.

#### Example - hide the tooltip callout
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    callout: false,
                    template: "Lon:#= location.lng #, Lat:#= location.lat #"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.iframe `Boolean`

Explicitly states whether content iframe should be created.

#### Example - load content from remote URL
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                      iframe: true,
                      content: {
                        url: "http://demos.kendoui.com/content/web/tooltip/ajax/ajaxContent3.html"
                      },
                      width: 220,
                      height: 280
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.height `Number`*(default: Infinity)*

The height (in pixels) of the tooltip.

#### Example - set the height of the tooltip
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    height: 80,
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.width `Number`*(default: Infinity)*

The width (in pixels) of the tooltip.

#### Example - set the width of the tooltip
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    width: 80,
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.position `String`*(default: "top")*

The position relative to the target element, at which the tooltip will be shown. Predefined values are "bottom", "top", "left", "right", "center".

#### Example - set tooltip position
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    position: "left",
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.showAfter `Number`*(default: 100)*

Specify the delay in milliseconds before the tooltip is shown. This option is ignored if showOn is set to "click" or "focus".

#### Example - set show delay
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    showOn: "mouseenter",
                    showAfter: 1000,
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markerDefaults.tooltip.showOn `String`*(default: "click")*

The event on which the tooltip will be shown. Predefined values are "mouseenter", "click" and "focus".

#### Example - show tooltip on mouse enter
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                tooltip: {
                    showOn: "mouseenter",
                    content: "Foo"
                }
            },
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markers `Array`

Static markers to display on the map.

#### Example - setting default shape for all markers
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27]
            }, {
                location: [40, 20]
            }]
        });
    </script>

### markers.location `Array|kendo.dataviz.map.Location`

The marker location on the map. Coordinates are listed as `[Latitude, Longitude]`.

#### Example - setting marker location
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markerDefaults: {
                shape: "pin"
            },
            markers: [{
                location: [42, 27]
            }]
        });
    </script>

### markers.shape `String` *(default: "pinTarget")*

The marker shape. The following pre-defined marker shapes are available:

* pinTarget
* pin

Marker shapes are implemented as CSS classes on the marker element (span.k-marker).
For example "pinTarget" is rendered as "k-marker-pin-target".

#### Example - setting marker shape
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                shape: "pin",
                location: [42, 27]
            }]
        });
    </script>

### markers.tooltip `Object`

Kendo UI Tooltip options for this marker.

### markers.tooltip.autoHide `Boolean`*(default: false)*

Specifies if the tooltip will be hidden when mouse leaves the target element. If set to false a close button will be shown within tooltip. If set to false, showAfter is specified and the showOn is set to "mouseenter" the Tooltip will be displayed after the given timeout even if the element is no longer hovered.

#### Example - hide tooltip on mouse leave
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    autoHide: true,
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation `Object`

A collection of {Animation} objects, used to change default animations. A value of **false**
will disable all animations in the widget.

#### Example - disable animations
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: false,
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.close `Object`

The animation that will be used when a Tooltip closes.

#### Example - set close animation
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                      close: {
                        effects: "fade:out"
                      }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.close.effects `String`

Effect to be used for closing of the tooltip.

#### Example - set close animation effect
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                        close: {
                            effects: "fade:out"
                        }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.close.duration `Number`

Defines the animation duration.

#### Example - set close animation duration
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                        close: {
                            duration: 1000
                        }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.open `Object`

The animation that will be used when a Tooltip opens.

#### Example - set open animation
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                        open: {
                            effects: "fade:in",
                            duration: 1000
                        }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.open.effects `String`

Effect to be used for opening of the Tooltip.

#### Example - set open animation effect
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                        open: {
                            effects: "fade:in"
                        }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.animation.open.duration `Number`

Defines the animation duration.

#### Example - set open animation duration
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    animation: {
                        open: {
                            duration: "1000"
                        }
                    },
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.content `Object|String|Function`

The text or a function which result will be shown within the tooltip.
By default the tooltip will display the target element title attribute content.

#### Example - extract the content from target marker
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: function(e) {
                        var marker = e.sender.marker;
                        return marker.options.location.toString();
                    }
                }
            }]
        });
    </script>

#### Example - content as static text
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.content.url `String`

Specifies a URL or request options that the tooltip should load its content from.

>Note: For URLs starting with a protocol (e.g. http://),
a container iframe element is automatically created. This behavior may change in future
versions, so it is advisable to always use the [iframe configuration option](#iframe).

#### Example - load content from remote URL
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                      content: {
                        url: "http://demos.kendoui.com/content/web/tooltip/ajax/ajaxContent3.html"
                      },
                      width: 220,
                      height: 280
                }
            }]
        });
    </script>

### markers.tooltip.template `String|Template`

The [template](/api/framework/kendo#methods-template) which renders the tooltip content.

The fields which can be used in the template are:

* location - the marker location (kendo.dataviz.map.Location instance)
* marker - the marker instance

> Setting a template disables the content option.

#### Example - set tooltip template
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    template: "Lon:#= location.lng #, Lat:#= location.lat #"
                }
            }]
        });
    </script>

### markers.tooltip.callout `Boolean`*(default:true)*

Specifies if the tooltip callout will be displayed.

#### Example - hide the tooltip callout
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    callout: false,
                    template: "Lon:#= location.lng #, Lat:#= location.lat #"
                }
            }]
        });
    </script>

### markers.tooltip.iframe `Boolean`

Explicitly states whether content iframe should be created.

#### Example - load content from remote URL
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                      iframe: true,
                      content: {
                        url: "http://demos.kendoui.com/content/web/tooltip/ajax/ajaxContent3.html"
                      },
                      width: 220,
                      height: 280
                }
            }]
        });
    </script>

### markers.tooltip.height `Number`*(default: Infinity)*

The height (in pixels) of the tooltip.

#### Example - set the height of the tooltip
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    height: 80,
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.width `Number`*(default: Infinity)*

The width (in pixels) of the tooltip.

#### Example - set the width of the tooltip
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    width: 80,
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.position `String`*(default: "top")*

The position relative to the target element, at which the tooltip will be shown. Predefined values are "bottom", "top", "left", "right", "center".

#### Example - set tooltip position
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    position: "left",
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.showAfter `Number`*(default: 100)*

Specify the delay in milliseconds before the tooltip is shown. This option is ignored if showOn is set to "click" or "focus".

#### Example - set show delay
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    showOn: "mouseenter",
                    showAfter: 1000,
                    content: "Foo"
                }
            }]
        });
    </script>

### markers.tooltip.showOn `String`*(default: "click")*

The event on which the tooltip will be shown. Predefined values are "mouseenter", "click" and "focus".

#### Example - show tooltip on mouse enter
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            markers: [{
                location: [42, 27],
                tooltip: {
                    showOn: "mouseenter",
                    content: "Foo"
                }
            }]
        });
    </script>

### minZoom `Number` *(default: 2)*

The minimum zoom level.

### maxZoom `Number` *(default: 19)*

The maximum zoom level.

### minSize `Number` *(default: 256)*

The size of the map in pixels at zoom level 0.

### wraparound `Boolean` *(default: true)*

Specifies whether the map should wrap around the east-west edges.

#### Example - disable map wrap-around
    <div id="map"></div>
    <script>
        $("#map").kendoMap({
            layers: [{
                type: "tile",
                urlTemplate: "http://a.tile.openstreetmap.org/#= zoom #/#= x #/#= y #.png",
                attribution: "&copy; OpenStreetMap"
            }],
            wraparound: false
        });
    </script>

### zoom `Number` *(default: 3)*

The initial zoom level.

Typical web maps use zoom levels from 0 (whole world) to 19 (sub-meter features).

The map size is derived from the zoom level and minScale options: `size = (2 ^ zoom) * minSize`

## Methods

### destroy

Prepares the widget for safe removal from DOM. Detaches all event handlers and removes jQuery.data attributes to avoid memory leaks. Calls destroy method of any child Kendo widgets.

> This method does not remove the widget element from DOM.

## Events

### click

Fired when the user clicks on the map.

### reset

Fired when the map is reset, e.g. on initial load or during zoom.

### pan

Fired while the map viewport is being moved.

### panEnd

Fires after the map viewport has been moved.

### shapeClick

Fired when a shape is clicked or tapped.

### shapeCreated

Fired when a shape is created, but is not rendered yet.

### shapeMouseEnter

Fired when the mouse enters a shape.

### shapeMouseLeave

Fired when the mouse leaves a shape.

### zoomStart

Fired when the map zoom level is about to change.

### zoomEnd

Fired when the map zoom level has changed.

