# Course 8, Chapter 1: Introduction to Data Visualization Tools

## Overview
Data visualization presents data as charts, graphs, and maps to make patterns, trends, and anomalies easy to understand. It is used across business, science, healthcare, and finance, and relies on clear design and appropriate plot choices.

## Best Practices
- Match the chart type to the question and data
- Use readable colors, fonts, and scales; minimize clutter
- Label axes and provide titles/legends where useful

## Common Plot Types
- Line plots: show trends and changes over time
- Bar plots: compare values across categories
- Scatter plots: explore relationships between variables
- Box plots: summarize distributions (median, quartiles, outliers)
- Histograms: show distributions across bins

## Core Python Libraries
- Matplotlib: foundational plotting library with broad capabilities
- Pandas: integrated plotting from DataFrames/Series
- Seaborn: statistical visualizations with attractive defaults
- Plotly: interactive, dynamic charts across many types
- Folium: interactive maps
- PyWaffle: waffle charts for proportional representation

## Matplotlib Essentials
- Widely used; integrates into many environments (e.g., Jupyter)
- Architecture layers: Backend, Artist, Scripting
- Anatomy of a plot: figure, axes, axis labels, title, legend, ticks, grid
- Backends: multiple rendering backends available
- Add labels and title with `plt.xlabel`, `plt.ylabel`, `plt.title`

## Data Workflow
- Import data into a Pandas DataFrame before plotting
- Generate a line plot via `df.plot(kind="line", ...)`

## Takeaways
- Choose visualization types that align with the story and data
- Leverage Matplotlib, Seaborn, Plotly, and Pandas for a strong toolkit
- Start with clean DataFrames; label clearly; keep visuals simple and informative
