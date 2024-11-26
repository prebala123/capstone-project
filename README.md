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

## Dataset
