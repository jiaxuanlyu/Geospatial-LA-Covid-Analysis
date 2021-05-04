# Final Project Rubric

**Group Members**

1. Jiaxuan Lyu

**Project Repository**

- https://github.com/MUSA-550-Fall-2020/final-project-jxl
- https://jiaxuanlyu.github.io/Geospatial-LA-Covid-Analysis/

**Grade: 73 / 80**

**Overall Comments**

# Grading

- **Concept (15/15)**:
  - **Criteria**
    - Is it sufficiently complex/challenging/sophisticated?
    - Is the final product useful/interesting/creative?
  - **Comments**
    - Well-designed with an interesting and timely
    - Good combination of multiple datasets to answer research questions

* **Technical implementation (21/25)**:

  - **Criteria**
    - Was it well thought out?
    - Was each step done correctly?
    - Does it satisfy 2 of the guidelines listed below?
  - **Comments**
    - Good job wrangling and visualizing multiple datasets
    - The 311 analysis and collision analysis could be improved by plotting relative differences aggregated at the CSA level (vs. side-by-side charts)
    - For the 311 analysis, it's difficult to analyze trends from the the side-by-side datashader maps. For datashader, you need to explicitly
      set the colorbar span to ensure color mapping is the same in both charts
    - An analysis of 311 tickets, aggregated at the CSA level, would have helped analyze the trends in a more quantitative manner

- **Visualization (22/25)**:
  - **Criteria**
    - How well does the data visualization serve its purpose?
    - Does it tell a clear story?
    - Are the colors/layout/titles well-chosen?
  - **Comments**
    - Good visuals overall, clearly conveying analysis results
    - For the collision analysis, I think a choropleth map would have communicated the result better than a bubble chart

* **Writeup (15/15)**:
  - **Criteria**
    - Is all of the above explained clearly?
    - Does the 1-2 page writeup explain in depth all aspects of the project's implementation and final results?
  - **Comments**
    - Clear and detailed explanation of the analysis
    - Good discussion of limitations and possible next steps

# Guidelines

The project is open-ended. The topic and technologies used are up to you.
However, the it must satisfy **at least two of the items below**:

- Data is collected through a means more sophisticated than downloading (e.g. scraping, API).
- At least one of the datasets contains more than 1,000,000 rows.
- It combines data collected from 3 or more different sources.
- The analysis of the data is reasonably complex, involving multiple steps
  (geospatial joins/operations, data shaping, data frame operations, etc).
- You use one of the analysis techniques for urban street networks (e.g., osmnx, pandana), clustering (e.g., scikit-learn), or raster datasets
- You perform a machine learning analysis with scikit-learn as part of the analysis.
- The webpage includes a significant interactive component (cross-filtering, interactive widgets, etc)
