# Malawi Project

> This repository contains some initial exploration of satellite data for Lake Malawi.

## Landcover

The Landcover notebook defines the coordinates for the lake boundary and then expands those coordinates outward to create a 25km buffer around the lake. It then extracts data from satellite data where the coorinates of the data are within the coordinates of the buffered zone. This data is subsequently analyzed for landcover categories. The analysis is performed on data spanning from 2017 to 2024, showing change over time.

## Evapotranspiration

The evapotranspiration notebook downloads satellite data for Lake Malawi and extracts evapotranspiration data where the coordinates of the data are within the coordinates of the buffered zone. This data spans 2017 to 2024 and shows change over time.

## Future Directions

- Extract additional types of data for the 25km buffered zone around the lake.
- Use machine learning (Random Deicison Forest) to find weights for each parameter (data type) to predict evapotranspiration.
- Simulate changes to weights to model effect on evapotranspiration over time into the future.
