# Arctic Shorebird Snow Cover Data

ARCTIC SHOREBIRD DEMOGRAPHICS NETWORK [https://doi.org/10.18739/A2222R68W](https://doi.org/10.18739/A2222R68W)

This dataset is hosted by the [NSF Arctic Data Center](https://arcticdata.io). Complete metadata for can be found at `01_ASDN_Readme.txt` provided in the [EDS 213 course repository](https://github.com/UCSB-Library-Research-Data-Services/bren-meds213-spring-2024-class-data/week1).

Field data on shorebird ecology and environmental conditions were collected from 1993-2014 at 16 field sites in Alaska, Canada, and Russia.

![Shorebird, copyright NYT](https://static01.nyt.com/images/2017/09/10/nyregion/10NATURE1/10NATURE1-superJumbo.jpg?quality=75&auto=webp)

Data were not collected every year at all sites. Studies of the population ecology of these birds included nest-monitoring to determine the timing of reproduction and reproductive success; live capture of birds to collect blood samples, feathers, and fecal samples for investigations of population structure and pathogens; banding of birds to determine annual survival rates; resighting of color-banded birds to determine space use and site fidelity; and use of light-sensitive geolocators to investigate migratory movements. 

Data on climatic conditions, prey abundance, and predators were also collected. Environmental data included weather stations that recorded daily climatic conditions, surveys of seasonal snowmelt, weekly sampling of terrestrial and aquatic invertebrates that are prey of shorebirds, live trapping of small mammals (alternate prey for shorebird predators), and daily counts of potential predators (jaegers, falcons, foxes). Detailed field methods for each year are available in the `ASDN_protocol_201X.pdf` files. All research was conducted under permits from relevant federal, state, and university authorities.

## Data and File Overview

#### 1. File List

- `data/processed/all_cover_fixed_hayleeoyler.csv`: contains the cleaned land cover type data. This includes percentages of snow cover, land cover, water cover, and total cover for the arctic shorebirds habitats. This is the cleaned version of the data originally found in `ASDN_Snow_Survey.csv`
- `data/processed/snow_cover.csv`: contains the partially cleaned data that cleaned only the `snow_cover` variable. This was done as part of an in-class exercise

- `data/raw/01_ASDN_Readme.txt`: The original data repository readme. Contains detailed metadata information about all datasets.
- `ASDN_Daily_species.csv`: Dataset containing shorebird species information.
- `ASDN_Snow_survey.csv`: Dataset containing the unprocessed snow survey data.

- `eds213_data_cleaning_assign_hayleeoyler.qmd`: Working document for the data cleaning process. Associated files and html for rendering and easier viewing. 

#### 2. Relationship Between Files
```
├── README.md
├── bren-meds213-data-cleaning.Rproj
├── data
│   ├── processed
│   │   ├── all_cover_fixed_hayleeoyler.csv        # Clean snow survey data
│   │   └── snow_cover.csv
│   └── raw
│       ├── 01_ASDN_Readme.txt
│       ├── ASDN_Daily_species.csv
│       └── ASDN_Snow_survey.csv                   # Unprocessed snow survey data
├── eds213_data_cleaning_assign_hayleeoyler.html 
├── eds213_data_cleaning_assign_hayleeoyler.qmd	   # Working doc to clean the snow survey data
└── eds213_data_cleaning_assign_hayleeoyler_files
```
#### 3. Additional related data collected that was not included in the current data package
The additional datasets can be accessed at the referenced parent dataset either from the [original source](https://arcticdata.io/catalog/view/doi%3A10.18739%2FA2CD5M), or from the [course repository](https://github.com/UCSB-Library-Research-Data-Services/bren-eds213-data/tree/main/ASDN_csv). 

#### 4. Are there multiple versions of the dataset?

There are two version of this data. The raw version can be found in `data/raw/ASDN_Snow_Survey.csv`. The clean version can be found in `data/processed/all_cover_fixed_hayleeoyler.csv`.

## Data-Specific Information for:

For the file  data/processed/all_cover_fixed_hayleeoyler.csv : 

#### 1. Number of variables:
11

#### 2. Number of cases/rows:
42830

#### 3.  Variable List: list variable name(s), description(s), unit(s)and value labels as appropriate for each

Column Name   | Definition                                                | Units
------------- | --------------------------------------------------------- | -----
Site          | Four-letter code of site at which data were collected     | N/A
Year          | Year in which data were collected                         | YYYY
Date          | Date on which data were collected                         | DD-MM-YYYY
Plot          | Name of study plot on which survey was conducted          | N/A
Location      | Name of dedicated snow-survey location, if applicable     | N/A
Snow_cover    | Percent cover of snow, including slush                    | Percentage
Water_cover   | Percent cover of water                                    | Percentage
Land_cover    | Percent cover of exposed land                             | Percentage
Total_cover   | Total sum (should always sum to 100)                      | Percentage
Observer      | Person who conducted the survey                           | N/A
Notes         | Any relevant comments on the survey                       | N/A

#### 4. Missing data codes: list code/symbol and definition
NA : Missing data. This data is missing either because of syntax errors during the data entry/recording process that were not interpretable, or because the missing data for a specific cover type could not be mathematically calculated given the corresponding values for the other cover types. 

Specifically, all non-numeric values for Snow cover, Land cover, and Water cover were replaced with NA. Additionally, any cover values that were far outside the range of 0-100 were removed. Some leeway was added (up to 120) for the total cover to account for possible calculation errors; this was to ensure we saved as much data as possible. Values for total cover were recalculated as the sum of the other three cover variables. In places where only two cover types were available, the missing cover type was filled by assuming the total cover was 100 and subtracting the difference of the two present cover types. 

#### 5. Specialized formats or other abbreviations used:
`Site` is abbreviated with a four-letter code that represents the sampling site. More detailed information about the site's name and description can be found in the data file `site.csv` [here](https://github.com/UCSB-Library-Research-Data-Services/bren-meds213-data-cleaning/tree/main/data/raw).

## Sharing and Access Information

#### 1. Licenses/restrictions placed on the data:
Potential users of these data should first contact the relevant data author(s), listed below.  This will enable coordination in terms of updates/corrections to the data and ongoing analyses.  Key analyses of the data are in progress and will be included in the theses and dissertations of graduate students who collected these field data. Disclaimers:  The dataset is distributed “as is” and with absolutely no warranty. The data providers have invested considerable effort to ensure that the data are of highest quality, but it is possible that undetected errors remain. Data have been processed with several steps for quality assurance, but the data providers accept no liability or guarantee that the data are up-to-date, correct, or complete. Access to data is provided on the understanding that the data providers are not responsible for any damages from inaccuracies in the data. 

#### 2. Links to publications that cite or use the data:

#### 3. Links to other publicly accessible locations of the data:
This data can be accessed via the National Science Foundation's [Arctic Data Center](https://arcticdata.io/catalog/view/doi%3A10.18739%2FA2CD5M)

#### 4. Links/relationships to ancillary data sets: any supplementary data sources that support analysis or classification of the datasets, eg., plant taxonomy table.
NA

#### 5. Was data derived from another source? If yes, list source(s): list citations to original sources
This is the cleaned version of the data originally found in `ASDN_Snow_Survey.csv` from the same data source. The original dataset is not derived from another source. 

#### 6. Recommended citation for the project:
Please acknowledge this dataset and the authors in any analysis, publication, presentation, or other output that uses these data. 
	If you use the full dataset, we suggest you cite it as:  
		 Lanctot, RB, SC Brown, and BK Sandercock. 2017. Arctic Shorebird Demographics Network. NSF Arctic Data Center. doi: INSERT HERE. 
	If you use data from only one or a few sites, we suggest you cite data for each site as per this example:  
		Lanctot, RB and ST Saalfeld. 2017. Barrow, 2014. Arctic Shorebird Demographics Network. NSF Arctic Data Center. doi: INSERT HERE.
Note that each updated version of the dataset has its own unique DOI.
