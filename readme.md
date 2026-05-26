# FRED Dataset Classification

Classification for each of the FRED datasets, with tags denoting relevant 
information about each one.

## Format

Tags are in the CSV file. Each row is a dataset, ordered like this:

```
number, train/test, tags, ...
```

Each dataset will have a tag for the number of drones in it (1-drone, 2-drones,
etc.) and tags for any relevant obstructions (ie none, rain, darkness, etc.)
