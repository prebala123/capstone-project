# Data Science Capstone

Our capstone project involves learning about graph analysis methods and how they are applied to chip data to optimize them for power usage, performance, and size. The first part of the project is about understanding graph methods and algorithms, and implementing them on a New York City MTA dataset for subway rides. By representing subway stations as nodes in a graph and rides between them as edges, we found insights into the behavior of riders on average. The second part of the project is then applying graph machine learning to chip data, and reproducing the results of another paper's experiments. We developed models to predict congested areas of the chip to fix them before the physical creation of the chips.

# Folder Structure
```
|
└───data
|   |   chips
|   └───mta
└───results
|   |   chips
|   └───mta
└───src
|   |   chips
|   └───mta
└───README.md
└───requirments.txt
```

# Prerequisites
The dependencies are listed under requirements.txt and are all purely python based. To install them simply run

```
pip install -r requirements.txt
```

# MTA Analysis

This project analyzes the average ridership between different subway stations in the New York City MTA to understand where the highest levels of congestion are. The MTA records information about every station in their network, as well as the average ridership between two stations at any given hour and day of the week. We use a graph representation to model the subway network and use properties of graphs to summarize the congestion at and between stations at various times of the week.

## Dataset
First download the two datasets from <br>
(1) https://data.ny.gov/Transportation/MTA-Subway-Stations/39hk-dx4f/about_data <br>
(2) https://data.ny.gov/Transportation/MTA-Subway-Origin-Destination-Ridership-Estimate-2/jsu2-fbtj/about_data <br>

Make sure that the files are called <br>
(1) MTA_Subway_Stations_updated.csv <br>
(2) MTA_Subway_Origin-Destination_Ridership_Estimate__2024_20241008.csv <br>

Then add the csv files to the `data/mta/` folder.

## Running

Navigate to `src/mta/` to find the code for the project. The entire code is written inside the jupyter notebook called `mta.ipynb`. Run each code cell to get the results of the analysis.

# Chip Profiling

This project analyzes cells and nets in a given netlist for a chip to determine areas of high congestion. We represent the chip as a hypergraph and use a message passing neural network with virtual nodes to create a model that we believe accurately predicts congestion. Our work is a reimplementation of this paper (https://arxiv.org/abs/2404.00477).

## Dataset

Download the dataset from [here](https://zenodo.org/records/10795280?token=eyJhbGciOiJIUzUxMiJ9.eyJpZCI6Ijk5NjM2MzZiLTg0ZmUtNDI2My04OTQ3LTljMjA5ZjA3N2Y1OSIsImRhdGEiOnt9LCJyYW5kb20iOiJlYzFmMGJlZTU3MzE1OWMzOTU2MWZkYTE3MzY5ZjRjOCJ9.WifQFExjW1CAW0ahf3e5Qr0OV9c2cw9_RUbOXUsvRbnKlkApNZwVCL_VPRJvAve0MJDC0DDOSx_RLiTvBimr0w). Extract all the files and create a folder called `2023-03-06_data`. 

Then add this folder to `data/chips/`.

## Running

Go to `src/chips/` to find the code for the project. Run the notebooks in this order.

(1) `load_data.ipynb` takes in the raw data and creates the bipartite graph representation <br>
(2) `create_eigen.ipynb` computes eigenvectors to encode the spatial location of each cell <br>
(3) `model.ipynb` takes features such as cell size and spatial location and outputs the predicted congestion, as well as model accuracy