# Product Review Analysis

These notebooks separate product-review collection from analysis. [scraper.ipynb](scraper.ipynb) contains the collection workflow, and [analyzer.ipynb](analyzer.ipynb) processes the resulting data. They are related to the related [Flask review application](https://github.com/oldprize47-SH/ceneo-review-webapp).

## Project goal

Turn collected product reviews into structured records, summary statistics and readable plots.

![Project goal: ceneo-review-analysis](docs/goals/project-focus-v1.png)

AI-generated concept illustration. Device appearance, interface layout and example graphics are illustrative, not project photographs or measured results.

## Where it could be used

The workflow could help someone explore collected product feedback by reading review text alongside rating and recommendation distributions. Keeping structured review records also makes it possible to repeat an analysis without recollecting every page. The summaries describe the collected sample rather than all customers, and collection depends on the source site and permitted access.

## At a glance

![Ceneo review-analysis notebooks](docs/flowcharts/ceneo-notebooks.png)

Overview reconstructed from the documented project and code. Results and verification limits are described below. [SVG](docs/flowcharts/ceneo-notebooks.svg)

## Collection and analysis are separate steps

The collection notebook takes a product identifier, requests the review pages and extracts fields such as the score, recommendation, text, advantages and disadvantages. It follows pagination and saves structured review records as JSON. The selectors and conversion functions are the connection between the original HTML and the fields used by the analysis.

The analysis notebook reads the saved records into a Pandas DataFrame. It counts reviews, checks how many contain advantages or disadvantages, calculates the average rating and plots rating and recommendation distributions. The rating chart shows how reviews are spread across scores; the recommendation chart separates positive, negative and missing responses. Neither chart is a representative survey of all customers: it describes the collected reviews.

## Where to begin

For a read-only review, open `analyzer.ipynb` on GitHub and follow the path from JSON loading to summary statistics and plots. Then read `scraper.ipynb` to see where each input field comes from. This order helps separate a data-processing question from a website-extraction question.

To execute a local copy, use a Jupyter-compatible environment, inspect [requirements.txt](requirements.txt), and reconcile the notebook's product ID and data paths. Run analysis only against a compatible saved dataset. The collection notebook makes network requests and depends on the site's current structure; it is not an offline test fixture.

This work comes from Sangheon Park's 2024 exchange-student coursework. The archive retains the original learning context; it does not establish individual authorship of every supplied cell or a production deployment.

The saved notebooks can be read on GitHub. Both passed notebook JSON checks on 28 September 2026, but their cells were not rerun. Changes to the website, remote services or the original Python environment may affect execution. The dependency snapshot is in [requirements.txt](requirements.txt).

Existing output is historical coursework. No new review collection was performed for this copy, and the review text remains the property of its original authors.

[Original repository](https://github.com/sangheon47/CeneoScraperAI11). Original history and attribution are retained.
