# Build-in-Public Launch Story

## I shipped my FlyRank ML project

Over the FlyRank internship, I worked on a search-intelligence ML problem: identifying content that shows signs of decline and using those signals to prioritize where review or refresh effort may be useful.

One decision that changed the project was building a transparent baseline before relying on machine learning. Instead of jumping straight to a model, I created a simple action score using signals such as content staleness and impression decline. The output could be interpreted as `REFRESH_NOW`, `REVIEW`, or `MONITOR`. That gave me a clear benchmark and made the ML results easier to judge.

The work also forced me to deal with something I had underestimated: scale. The warehouse workflow reached approximately 78.8 million processed examples. Getting data access and processing working reliably involved debugging authentication, parquet loading, notebook execution, and feature preparation. That experience taught me that ML engineering is as much about reliable data and verification as it is about the model itself.

AI was part of my workflow throughout the build. I used AI assistants to explain concepts, suggest debugging approaches, structure code, review ideas, and improve documentation. But I still had to run the code and check the results. One of the biggest lessons for me was that an AI answer can look convincing without being correct.

The biggest limitation is that the declining-content target is a proxy. A model score can help prioritize investigation, but it does not prove that a page should be refreshed or that a change will improve search performance.

My next step is to evaluate the approach across additional time periods and connect predictions more directly to real business outcomes. The goal is to turn this from an internship ML workflow into a more robust monitoring and decision-support system.

The portfolio and project package are now public. The important part for me is not claiming that the model is perfect; it is being able to show the work, explain the decisions, and be honest about what still needs to improve.
