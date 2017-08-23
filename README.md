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

This function has 3 necessary arguments: the data frame, the name of the column containing the longitude coordinates in your data frame and the name of the column containing the latitude coordinates in your data frame. The `progress` argument is by default set to true, this denotes whether you want progress of the function as a percentage printed to the console. The returned object will be a dictionary in GeoJSON format which can be edited or you can export it using the next function.

#### Example

```Python
import pandas as pd
import df2geojson

#Create example dataframe
data = pd.DataFrame([{'name':'Beechbridge', 'population':7658, 'Lon':35.08439, 'Lat':-75.02809},
                     {'name':'Wheatland', 'population':4695, 'Lon':-24.44890, 'Lat':-63.35822},
                     {'name':'Northbush', 'population':8955, 'Lon':114.08806, 'Lat':-41.13366},
                     {'name':'Glassapple', 'population':5994, 'Lon':50.62616, 'Lat':28.01296}])
#Convert
geo = df2geojson.convert(data, "Lon", "Lat" )

```

### Dump

#### Syntax

df2geojson.<b>dump</b>(FilePath, geoJSONDict)

#### Explanation

This function takes two arguments, the file path including the ```.geojson``` file extension and the object that you want to dump to the file.

#### Example

```Python
#Using the geo object created above
df2geojson.dump("features.geojson", geo)
```

### Convert and dump

#### Syntax

df2geojson.<b>convert_and_dump</b>(df, LongitudeColumnName, LatitudeColumnName, FilePath, progress=True)

#### Explanation

This function is in essence a wrapper for combining the top two functions as I find myself doing this alot, it will convert the data frame and the dump it to the specified file path.

#### Example

```Python
#Using the dataframe from above
df2geojson.convert_and_dump(data, "Lon", "Lat", "features.geojson")
```
