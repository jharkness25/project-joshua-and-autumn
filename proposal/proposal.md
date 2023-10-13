Project proposal: Contaminated sediments in the Gulf of Maine
================
Joshua Harkness and Autumn Pauly,
October 2023

``` r
library(tidyverse)
library(broom)
library(readxl)
```

## 1. Introduction

We will be looking at distributions and frequencies of contaminated
sediments in the Gulf of Maine, using the Gulf of Maine Contaminated
Sediments Database published by the U.S. Geological Survey in their
Open-File Report 02-403.

There are seven data files in this database which we will use in some
form, principally these include geographic information on stations
(collection sites), textural sediments data, and contaminants data.

We are most interested in examining patterns in distribution and
abundance of organic contaminants, which, in this dataset, are
represented by polychlorinated biphenyls (PCBs), polycyclic aromatic
hydrocarbons (PAHs), and organochlorine pesticides. We may, however,
examine inorganic contaminants, such as heavy metals, if we find that
there is not as much organic contaminant data to be useful for our
purposes here.

## 2. Data

``` r
stations = read_excel("/cloud/project/data/STAT2002.xls", sheet = 2, skip = 3)
sediments = read_excel("/cloud/project/data/TXTR2002.xls", sheet = 2, skip = 3)
PCBs = read_excel("/cloud/project/data/PCBP2002.xls", sheet = 2, skip = 3)
PAHs = read_excel("/cloud/project/data/PAHS2002.xls", sheet = 2, skip = 3)
Organics = read_excel("/cloud/project/data/GENO2002.xls", sheet = 2, skip = 3)
Inorganics = read_excel("/cloud/project/data/INOR2002.xls", sheet = 2, skip = 3)
```

``` r
stations %>%
  ggplot(aes(x = LONGITUDE, y = LATITUDE))+
  geom_point()+
  theme_bw()
```

    ## Warning: Removed 318 rows containing missing values (`geom_point()`).

![](proposal_files/figure-gfm/unnamed-chunk-1-1.png)<!-- --> Map of raw
station data for Gulf of Maine, representing sediment sampling
locations. You can see the outline of the New England coast where points
are dense, representing greater sampling.

## 3. Ethics review

## 4. Data analysis plan
