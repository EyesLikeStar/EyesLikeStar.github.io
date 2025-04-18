---
name: Bigfoot Sightings Visualization
tools: [Python, HTML, vega-lite, altair]
image: assets/pngs/Sightings.png
description: These two charts show the number of UFOs and the distribution of the top 15+ UFOs in each state across the U.S. from 1950 to 2023.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


## HW5：UFO Sightings
These two charts show the number of UFOs and the distribution of the top 15+ UFOs in each state across the U.S. from 1950 to 2023.


---
### UFO Sightings Map

<iframe src="/assets/html/ufo_sightings.html" width="1000" height="600" style="border:none;"></iframe>

**Visualization Description:**
This scatter plot maps UFO sightings across the United States, visualizing each reported sighting as a dot positioned by latitude and longitude. The map highlights patterns of sightings geographically, clearly illustrating higher densities in specific regions, notably along the coasts and populated areas.

**Design Choices & Encoding:**
Each UFO sighting is encoded with a distinct color representing its reported shape, using a categorical color scheme (category20) to differentiate numerous categories effectively. Spatial encoding clearly positions each sighting geographically, creating an intuitive visual understanding of distribution.

**Data Transformations:**
Data was filtered to include sightings only within valid U.S. locations, standardizing geographical coordinates and cleaning textual descriptions (such as UFO shapes) for consistency.


### UFO Shapes Distribution Bar Chart

<vegachart schema-url="{{ site.baseurl }}/assets/json/ufo_sightings_distribution.json" style="width: 100%"></vegachart>

**Visualization Description:**
This horizontal bar chart depicts the frequency of reported UFO shapes for a user-selected state (e.g., Oregon), clearly emphasizing the most commonly sighted shapes. It simplifies comparisons among shape categories and clearly identifies "Light" as the most frequent type of sighting.

**Design Choices & Encoding:**
The chart employs length encoding effectively, representing the number of sightings per shape. It uses distinct categorical colors consistently aligned with shapes to enhance visual differentiation, facilitating easy interpretation.

**Data Transformations:**
UFO shapes were grouped into the top 15 most common categories, with less common shapes aggregated into an "Other" category to enhance readability and simplify interpretation.

**Interactivity:**
The bar chart incorporates a dropdown selection allowing users to choose a specific state and dynamically update the shape distribution. This state-based filtering highlights regional differences clearly, making the visualization more interesting and enabling focused analysis tailored to the user's curiosity or specific investigative questions.

- [CSV link](https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv)
- [Github Notebook](https://github.com/EyesLikeStar/EyesLikeStar.github.io/blob/main/python_notebooks/HW5.ipynb)