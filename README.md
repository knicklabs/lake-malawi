# Lake Malawi

This repository is an exploratory data analysis project. It uses satellite data to study land and water conditions around Lake Malawi from 2017 to 2024. Specifically, it focuses on data from a 25KM buffered zone around the lake boundary to understand environmental changes over time.

Landcover and evapotranspiration in particular are important factors in sustainable agriculture, water system conservation, and mitigating impacts of climate change.

## Analysis

### Landcover

The landcover notebook defines the lake's boundary and creates a 25km buffer around the boundary. The notebook also processes the raw satellite data from the region. For each year of data, the pixels whose coordinates fall inside the buffered area are extracted. The extracted data is segmented into landcover categories (e.g. different surface types) and examined for changes year-over-year between 2017 and 2024, inclusively.

### Evapotranspiration

The evapotranspiration notebook downloads satellite data from the buffered area around the Lake Malawi boundary. The evapotranspiration values are extracted from the raw data and then examined for changes year-over-year between 2017 and 2024, inclusively.

## Future Directions

> Author's note: I worked on this project to learn how to work with satellite data and do some exploratory analysis. I had hoped to also do some ML work with this data, but I didn't have the time to get that far. Nonetheless, if the future directions that I laid out based on my work look interesting to you, I would encourage you to run with it (and hopefully share your results). If the source code in this repository may be useful to you, then I would also encourage you to fork this project. Take from it and/or extend it &mdash; however you see fit. I am licensing the code in this project under the permissive [MIT license](./LICENSE.md).

- Collect and extract additional types of data (i.e. soil moisture) for the 25km buffered area around the lake.
- Use machine learning (i.e. Random Decision Forest) to find weights for each parameter to predict evapotranspiration.
- Simulate changes to in properties (i.e. increased landcover) to model the effect on evapotranspiration to better understand the impact that specific environmental changes or interventions could have on agriculture, acquaculture, conservation, and sustainability.

## Related Research

Machine learning and deep learning have been used in other regions to predict evapotranspiration values. It might be possible to use the approaches found in the literature to do prediction in the Lake Malawi region. This could be useful in environmental and water management and sustainability efforts in the region.

- [Estimate reference evapotranspiration using machine learning methods](https://www.scitepress.org/Papers/2025/131318/131318.pdf)
- [Estimating reference evapotranspiration using a machine learning approach](https://iwaponline.com/wst/article/92/6/819/109335/Estimating-reference-evapotranspiration-using-a)
- [Evaluating maching learning models for estimating evapotranspiration in Colmbia's Cauca River Valley](https://www.nature.com/articles/s41598-025-29514-0)
- [Machine learning approaches for enhanced estimation of reference evapotranspiration (ETo): a comparative evaluation](https://www.nature.com/articles/s41598-025-23166-w)
- [Prediction of monthly evapotranspiration by artificial neural network model development with Levenberg-Marquit Method in Elazig, Turkey](https://pmc.ncbi.nlm.nih.gov/articles/PMC10948580/)
- [Prediction of potential evapotranspiration via machine learning and deep learning for Sustainable Water Management in the Murat River Basin](https://www.mdpi.com/2071-1050/16/24/11077)

## Other Resources

- [Lake Malawi GeoJSON data](https://geo2day.com/africa/malawi.geojson)
- [Lake Malawi GeoJSON data (alternative)](https://polytope-edr.ecmwf.int/collections/lakes/items/10?f=json)
- [Landcover classification ML tutorial](https://github.com/microsoft/PlanetaryComputerExamples/blob/main/tutorials/landcover.ipynb): Learn how to apply land cover classification model to planetary computer imagery
- [Planetary Computer](https://planetarycomputer.microsoft.com): Multi-petabyte catalog of global environmental data
- [Sentinel-2 Land Cover Classes](https://collections.sentinel-hub.com/impact-observatory-lulc-map/readme.html)

## Development

### Project Structure

This project is organized as a research-style codebase with data folders and executable notebooks. For convenience, output generated from running the notebooks has been committed to this repository.

```
lake-malawi/
├─ data/          # Raw and intermediate data
│  ├─ raw/        # Definition of lake boundary and raw satellite data
│  ├─ processed/  # Definition of buffered region and masked satellite data
├─ notebooks/     # Notebooks for landcover and evapotranspiration analysis
├─ out/           # HTML exports of executed notebooks
```

### Requirements

This project uses [Mise](https://github.com/jdx/mise), [UV](https://docs.astral.sh/uv/), and [Python 3.13](https://www.python.org/).

If you are not familiar with these tools, you can use the preconfigured container to work with this project. In [VS Code](https://code.visualstudio.com/), open the project in a dev container when prompted. See this article on [developing inside a container](https://code.visualstudio.com/docs/devcontainers/containers) for more details. This container has all the required software and dependencies.

### Getting Started

Install dependencies with `mise run install`

Download datasets:

1. [Raw GeoJSON and satellite data files](https://gtvault-my.sharepoint.com/:u:/g/personal/nkenyeres3_gatech_edu/IQDNWwsJ3l5xSJhRUrjmPrXMARbRRrJC6zCKENAXrd6Jlmw?e=5pAs8v)
2. [Processed GeoJSON and satellite data files](https://gtvault-my.sharepoint.com/:u:/g/personal/nkenyeres3_gatech_edu/IQDxrMppFMiwTYxF0yGmuyTSAZfWs3q7s7XBp2KZleINxh4?e=0gGNBw) (optional)

These datasets were not included in the repository because they are not being licensed under the license of this project and they are quite large. That is why you will need to download them separately.

Extract:

1. Extract the contents from the downloaded `raw.zip` archive into `./data/raw/`.
2. Optionally extract the contents from the downloaded `processed.zip` archive into `./data/processed/`. 

Note: If you run the `landcover` notebook first, the `processed` files will be generated and so there is no need to download or extract them. However, if you want to run only the `evapotranspiration` notebook, then you will need to download and extract the processed files since you won't be generating them yourself.

Run the landcover notebook:

For landcover analysis, run `mise run landcover_notebook` and then visit `http://localhost:8888/notebooks/landcover.ipynb` in your browser to open the notebook. Select `Run > Run all cells` from the main menu to execute the notebook in its entirety. It may take several minutes to complete running.

Run the evapotranspiration notebook:

For evapotranspiration analysis, run `mise run evapo_notebook` and then visit `http://localhost:8888/notebooks/evapotranspiration.ipynb` in your browser to open the notebook. Select `Run > Run all cells` from the main menu to execute the notebook in its entirety. It may take several minutes to complete running.

Special instructions when running notebooks from inside a dev container:

Note: If running from the dev container, you may be prompted to enter a token. You can find it in the CLI output, as part of the URL. It should look like this: `http://localhost:8888/notebooks/landcover.ipynb?token=123`. Copy the part after `?token=` and paste it into the web page where prompted.

## Questions

Please feel free to contact the author with any questions you have.
