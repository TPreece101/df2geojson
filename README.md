# df2geojson
## Introduction
This module does exactly what it says on the tin, it allows you to easily convert Pandas dataframes into GeoJSON format, all you have to do is tell it what the names of your longitude and latitude columns are in your dataframe. All of the other columns in the dataframe will be added to the properties section of the geoJSON!

## Installation
This module can be installed by cloning this repository or via pip as shown below:
```bash
    $ pip install df2geojson
```
## Usage
I will show a brief example of each of the functions:

### Convert

#### Syntax

df2geojson.<b>convert</b>(df, LongitudeColumnName, LatitudeColumnName, progress=True)

#### Explanation

This function has 3 necessary arguments: the data frame, the name of the column containing the longitude coordinates in your data frame and the name of the column containing the latitude coordinates in your data frame. The `progress` argument is by default set to true, this denotes whether you want progress of the function as a percentage printed to the console.

#### Example

```Python
import pandas as pd
import df2geojson

#Create example dataframe
```
