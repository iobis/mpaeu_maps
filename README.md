# <img src="logos/mpaeu_obis_logo.jpg" align="right" width="240" /> Mapping marine species distributions to inform the design of protected areas in Europe

[![DOI](https://img.shields.io/badge/DOI-10.5281/zenodo.23018410-blue)](https://doi.org/10.5281/zenodo.23018410)
[![Products catalogue](https://raw.githubusercontent.com/iobis/badges/refs/heads/main/badges/obis-products_catalogue.svg)](https://products.obis.org/dataset/10-5281-zenodo-23018410)
[![IOC](https://raw.githubusercontent.com/iobis/badges/refs/heads/main/badges/ioc-hlo1_healthy_ocean.svg)](https://www.ioc.unesco.org/en/mission-and-objectives)
[![IOC](https://raw.githubusercontent.com/iobis/badges/refs/heads/main/badges/ioc-hlo3_resilience_to_climate_change.svg)](https://www.ioc.unesco.org/en/mission-and-objectives)

## Species distribution models for the MPA Europe project

This repository contains the core information about the Species Distribution Models (SDMs) for marine species occurring in European waters, developed by OBIS as part of the MPA Europe project. It covers **12,039 species** and **6 biogenic habitats** (produced using Stacked SDMs).

## Access

All range maps and accompanying data are available through AWS: [https://obis-maps.s3.amazonaws.com/index.html](https://obis-maps.s3.amazonaws.com/index.html)

Content is also provided as a STAC catalogue (https://obis-maps.s3.us-east-1.amazonaws.com/sdm/stac/catalog.json), which you can explore [here](https://browser.moregeo.it/external/obis-maps.s3.us-east-1.amazonaws.com/sdm/stac/catalog.json). You can explore maps dynamically through the [maps platform](https://iobis.github.io/mpaeu_map_plat_static).

To download range maps, we recommend using the [AWS CLI](https://aws.amazon.com/cli/):

``` bash
# download data for one single species
aws s3 sync --no-sign-request s3://obis-maps/sdm/species/taxonid=1005409/ ./taxonid=1005409/
```

You can also explore the [notebooks](notebooks/) folder, which contains some examples of use in R and Python.

## License

The dataset as a whole is licensed under [**CC-BY-NC 4.0**](https://creativecommons.org/licenses/by-nc/4.0/deed.en), respecting the license of the underlying occurrence data used to fit the models, which comes from OBIS and GBIF.

A considerable number of species were fit with CC-BY (or CC0) data and may instead be used under that license. Check the [`species-details.csv`](species-details.csv) file for more details.

## Authors

Silas C. Principe<sup>1</sup>, Pieter Provoost<sup>1</sup>, Ward Appeltans<sup>1</sup>, Jorge Assis<sup>2,5</sup>, Michael T. Burrows<sup>3</sup>, Fabrice Stephenson<sup>4</sup>, Anna Addamo<sup>5</sup>, Mark John Costello<sup>5</sup>

_<sup>1</sup>Ocean Biodiversity Information System, International Oceanographic Data and Information Exchange, Intergovernmental Oceanographic Commission, UNESCO, Oostende, 8400, Belgium_  
_<sup>2</sup>Centre for Marine Sciences, University of Algarve, Faro, 8005-139, Portugal_  
_<sup>3</sup>Scottish Association for Marine Science, Oban, Argyll, PA37 1QA, United Kingdom_  
_<sup>4</sup>Newcastle University, Newcastle upon Tyne, NE1 7RU, United Kingdom_  
_<sup>5</sup>Faculty of Biosciences and Aquaculture, NORD University, Bodø, 8026, Norway_  

## Code availability

The full pipeline used to develop the SDMs is licensed under [**CC-BY 4.0**](https://creativecommons.org/licenses/by/4.0/deed.en) and can be found in the repository [iobis/mpaeu_sdm](https://github.com/iobis/mpaeu_sdm).

The core functions behind our modelling framework are in the repository [iobis/mpaeu_msdm](https://github.com/iobis/mpaeu_msdm) (from 'methods' SDM), which contains the package `obissdm`. More detailed documentation of our framework can be found [here](https://iobis.github.io/mpaeu_docs).

> [!IMPORTANT]
> Species distribution models (SDMs) are valuable tools, but it's important to understand how to interpret their results correctly. Before using the maps generated in this project, read the documentation available [here](https://iobis.github.io/mpaeu_docs/understanding.html). Results reflect the data available at the time of the project and the modelling decisions made. After this project is concluded, OBIS will continue to develop and improve its SDM framework, so newer versions of the maps may be available in the future.
