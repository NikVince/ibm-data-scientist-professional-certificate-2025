# Course 8, Chapter 3: Advanced Visualizations and Geospatial Data

## Overview
This chapter introduces geospatial visualization with Folium and advanced map styling. You learned how to configure base map tiles, center maps, add interactive markers and popups, group features, and build choropleth maps from regional boundary data.

## Folium Basics
- Folium is a Python library for visualizing geospatial data.
- Create maps with different base styles (e.g., street-level, Stamen) using the `tiles` parameter.
- The `location` parameter sets the map center via latitude/longitude coordinates.

## Markers and Interactivity
- Add markers with `folium.Marker()`; specify `location` and optional `popup` text.
- Use popups to label or describe locations on click.
- Organize multiple markers with a feature group for clarity and control.

## Choropleth Maps
- Choropleths shade regions proportional to a statistical variable.
- Building a choropleth requires a GeoJSON file containing regional boundaries.
- The Mapbox Bright tileset can display country names to enhance geographic context.

## Takeaways
- Switch `tiles` to tailor context; center with `location` for the target region.
- Combine markers, popups, and feature groups to enrich interactivity.
- Construct choropleths with proper GeoJSON boundaries and matched keys.


