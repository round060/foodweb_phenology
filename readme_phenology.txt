This readme.txt file was generated on 2025-02-14 by Christopher Rounds

-------------------
GENERAL INFORMATION
-------------------


1. Title of Dataset 
Data in support of: Phenology, food webs, and fish: the effects of loss of lake ice across multiple trophic levels

2. Author Information


  Principal Investigator Contact Information
        Name: Christopher I. Rounds
           Institution: University of Minnesota Twin Cities
           Email: https://orcid.org/0000-0003-1346-5707

  Associate or Co-investigator Contact Information
        Name: Gretchen J.A. Hansen
           Institution: University of Minnesota Twin Cities
           Email: ghansen@umn.edu
	   ORCID: https://orcid.org/0000-0003-0241-7048

  Associate or Co-investigator Contact Information
	Name: Jake Walsh
           Institution: University of Minnesota, Department of Fisheries and Wildlife
           Email: walsh229@gmail.com
	   ORCID: https://orcid.org/0000-0003-2292-6106

  Associate or Co-investigator Contact Information
	Name: Zachary S. Feiner
           Institution: Office of Applied Science, Wisconsin DNR, 
			Center for Limnology, University of Wisconsin-Madison 
           Email: zachary.feiner@wisconsin.gov
	   ORCID: https://orcid.org/0000-0001-7880-0778

  Associate or Co-investigator Contact Information
	Name:  Catherine A. Polik
           Institution: Department of Ecology, Evolution, and Behavior, University of Minnesota
           Email: polik020@umn.edu
	   ORCID: https://orcid.org/0000-0003-0440-1162

  Associate or Co-investigator Contact Information
        Name: John Manske
           Institution: Ramsey County
	   Email: John.Manske@co.ramsey.mn.us

 

3. Date of data collection (single date, range, approximate date) 

Different datasets had vary ranges
Walleye spawning - 1930-2024
Plankton data 1980-2024
Walleye recruitment data 1993 - 2022
Walleye adult abundance data 1984-2022

4. Geographic location of data collection (where was data collected?):  
Minnesota, USA

5. Overview of the data (abstract): 
This dataset and associated analyses are made to accompany the manuscript, "Phenology, food webs, and fish: the effects of loss of lake ice across multiple trophic levels". Accompanying data is split into components with distinct analyses (lake ice-off, phytoplankton, zooplankton, walleye spawning, walleye young-of-year recruitment, and walleye abundance). Plankton data is collected from Ramsey County, MN, USA lakes and filtered only to include open water season. Walleye spawning is collected by DNR staff as part of egg-take operations in the spring, walleye young-of-year recruitment is indexed by fall electrofishing and was filtered according to (Kundel et al. 2023). Walleye adult abundance is indexed through gillnets during the open water season and has minimum effort and sampling time of year filtering (see MNDNR 2017), unaged fish were applied a HALK to allow for cohort effects to be modeled (based on Frater et al. 2024). All analyses are done using the package mgcv in R and visualized using ggplot2.




Frater, P. N., Feiner, Z. S., Hansen, G. J. A., Isermann, D. A., Latzka, A. W., & Jensen, O. P. (2024). The Incredible HALK?: Borrowing Data for Age Assignment. Fisheries, 49(3), 117–128. https://doi.org/10.1002/fsh.11019

Kundel, H; Hansen, Gretchen J A. (2023). Data in Support of Widespread declines in walleye recruitment following zebra mussel invasion in Minnesota lakes. Retrieved from the Data Repository for the University of Minnesota (DRUM), https://doi.org/10.13020/N6TZ-VJ60.

Minnesota Department of Natural Resources (MNDNR). (2017). Manual of Instructions for Lake Survey. Minnesota Department of Natural Resources, Special Publication No. 180, St. Paul, Minnesota (version 1.04, released January 2019).

--------------------------
SHARING/ACCESS INFORMATION
-------------------------- 


1. Was data derived from another source?
           If yes, list source(s):

2. Terms of Use: Data Repository for the U of Minnesota (DRUM) By using these files, users agree to the Terms of Use. https://conservancy.umn.edu/pages/policies/#drum-terms-of-use


---------------------
DATA & FILE OVERVIEW
---------------------


1. File List
   A. Filename: data         
      Short description: folder containing cleaned data to be used in running models       

   B. Filename: models        
      Short description: folder containing model output (in the form of an .rds) output from the file model_code.rmd. Due to the long time required to run the model we recommend reading in this file instead of running the model.        
        
   C. Filename: foodweb_phenology.rproj       
      Short description: R Project file created to help project management.

   D. Filename: egg_ice.rmd       
      Short description: R markdown document that runs a model examining the relationship between walleye spawning phenology and ice-off. Outputs a .csv file into the data folder (called wae_spawning_modeled.csv).

   E. Filename: phyto_ice_s.rmd       
      Short description: R markdown document that runs a model examining the relationship between phytoplankton phenology and ice-off. Outputs a .csv file into the data folder (called phyto_modeled_peak.csv), a .rmd file into the models folder (called phyto.models_s.rds) and figures into a folder called figures.

   F. Filename: zoop_ice_s.rmd       
      Short description: R markdown document that runs a model examining the relationship between zooplankton phenology and ice-off. Outputs a  a .rmd file into the models folder (called zoop.models_s.rds) and figures into a folder called figures. Uses data outputted from egg_ice.rmd and phyto_ice_s.rmd.

   G. Filename:  ice_recruitment.rmd      
      Short description: R markdown document that runs a model examining the relationship between walleye age-o recruitment and ice-off.

   H. Filename: ice_gillnet.rmd      
      Short description: R markdown document that runs a model examining the relationship between walleye adult abundance and ice-off. 

2. Relationship between files:        
data contains the data files required to run the analyses. Models contain outputted models. RMD files contain code to reproduce the analyses. egg_ice.rmd and phyto_ice_s.rmd should be ran before zoop_ice_s.rmd because they output data used in zoop_ice_s.rmd. 

3. People involved with sample collection, processing, analysis and/or submission:
Ramsey county staff, DNR fisheries staff, Denver Link, Michael Verhoeven

-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: ice_off_summarized.csv
-----------------------------------------

File is largely a cleaned version of ice_out.csv from https://doi.org/10.13020/110f-j487 with added data for certain key lakes.

1. Number of variables: 8

2. Number of cases/rows: 20023

3. Missing data codes:
        Code/symbol        NA

4. Variable List
    A. Name: DOW
       Description: Department of Waterbody lake ID. Used as an identifier for different lakes in Minnesota.

    B. Name: year
       Description: Year corresponding to the ice-off observation

    B. Name: min_ice_off_julian
       Description: The earliest recorded julian day of year of ice off for the waterbody-year combination.

    C. Name: max_ice_off_julian
       Description: The latest recorded julian day of year of ice off. min_ice_off_julian and max_ice_off_julian will be the same if there is only one ice off record for that year-lake combination and will be different if there are records of ice off occurring on two or more different days.

    D. Name: min_ice_off_date
       Description: The earliest recorded date of ice off for the waterbody-year combination. Formatted as "YYYY-MM-DD".

    E. Name: max_ice_off_date
       Description: The latest recorded date of ice on for the waterbody-year combination. min_ice_off_date and max_ice_off_date will be the same if there is only one ice off record for that year-lake combination and will be different if there are records of ice off occurring on two or more different days. Formatted as "YYYY-MM-DD".

    F. Name: N_ice_off
       Description: The number of times ice on was recorded for a given lake-year combination.

    G. Name: range_ice_off
       Description: The range in days of the different ice on records in a given lake-year. If there is only one ice on record the range is zero.


-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: ramsey_county_phytoplankton.csv
-----------------------------------------

File contains phytoplankton abundance data from 28 Ramsey County MN lakes

1. Number of variables: 11

2. Number of cases/rows: 5997

3. Missing data codes:
        Code/symbol        NA

4. Variable List
                  
    A. Name: DNRID
       Description: 6-7 digit code to identify the waterbody

    B. Name: DATE
       Description: Date of sampling event (in the form of m/d/yyyy)

    C. Name: JULIANDAY
       Description: Day of year sampling occurred (January 1st is 1, February 1st is 32, etc.)

    D. Name: year
       Description: year of sampling event

    E. Name: ALL.CELLS
       Description: The number of phytoplankton cells recorded in natural units

    F. Name: CYANOS
       Description: The number of cyanobacteria cells recorded in natural units

    G. Name: GREEN
       Description: The number of green-algae cells recorded in natural units

    H. Name: DIATOM
       Description: The number of diatom cells recorded in natural units

    I. Name: DINOS
       Description: The number of dinoflagellate cells recorded in natural units

    J. Name: CRYPTOS
       Description: The number of cryptomonad cells recorded in natural units

    K. Name: CHRYSOS
       Description: The number of chrysophyte cells recorded in natural units



-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: ramsey_county_zooplankton.csv
-----------------------------------------

File contains zooplankton abundance data from 28 Ramsey County MN lakes

1. Number of variables: 11

2. Number of cases/rows: 5997

3. Missing data codes:
        Code/symbol        NA

4. Variable List
                  
    A. Name: DNRID
       Description: 6-7 digit code to identify the waterbody

    D. Name: SITE
       Description: Unique ID for the site within a lake

    C. Name: DATE
       Description: Date of sampling event (in the form of m/d/yyyy)

    D. Name: TOW
       Description: Depth of the zooplankton net tow in m

    E. Name: CYCLO.THOUS.M3
       Description: The number of thousand cyclopoid copepod zooplankton per M3 (or no./L)

    F. Name: CALA.THOUS.M3
       Description: The number of thousand calanoid copepod zooplankton per M3 (or no./L)

    G. Name: NAUP.THOUS.M3
       Description: The number of thousand nauplii zooplankton per M3 (or no./L)

    H. Name: ROTIFER.THOUS.M3
       Description: The number of thousand rotifer zooplankton per M3 (or no./L)

    I. Name: DAPH.THOUS.M3
       Description: The number of thousand daphnia zooplankton per M3 (or no./L)

    J. Name: BOSM.THOUS.M3
       Description: The number of thousand bosmina zooplankton per M3 (or no./L)

    K. Name: CHYD.THOUS.M3
       Description: The number of thousand chydorus zooplankton per M3 (or no./L)

    L. Name: CERIOD.THOUS.M3
       Description: The number of thousand ceriodaphnia zooplankton per M3 (or no./L)

    M. Name: DIAPHAN.THOUS.M3
       Description: The number of thousand diaphnasoma zooplankton per M3 (or no./L)

    N. Name: LEPTO.THOUS.M3
       Description: The number of thousand leptodoptera zooplankton per M3 (or no./L)

    O. Name: OTHER.THOUS.M3
       Description: The number of thousand unidentified zooplankton per M3 (or no./L)

    P. Name: JULIANDAY
       Description: Julian day of year sampling occurred (January 1st is 1, February 1st is 32, etc.)

    Q. Name: YEAR
       Description: year of sampling event


-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: wae_spawning_clean.csv
-----------------------------------------

File contains walleye spawn timing data from 13 walleye spawn take operations operated by the Minnesota DNR

1. Number of variables: 13

2. Number of cases/rows: 877

3. Missing data codes:
        Code/symbol        NA

4. Variable List
                  
    A. Name: DNRID
       Description: 6-7 digit code to identify the waterbody

    B. Name: location
       Description: Name of lake or river where the walleye egg take operation occurred 

    C. Name: year
       Description: Year of sampling event

    D. Name: date
       Description: Date of sampling event (in the form of m/d/yyyy)

    E. Name: event
       Description: What type of spawning event the row is describing (either start of spawning, peak spawning or the end of spawning)

    F. Name: strain
       Description: The strain that the given walleye population corresponds to

    G. Name: source
       Description: Who in the MN DNR provided the data

    H. Name: min_ice_off_julian
       Description: Julian day of year that the ice came off

    I. Name: min_ice_off_date
       Description: Date that the ice came off (in the form of m/d/yyyy)

    J. Name: mean_ice_off
       Description: mean julian day that the ice has come off for the given location prior to 1980. Used to calculate the ice-off anomaly column

    K. Name: count
       Description: Number of ice-off observations for the given location that have been made prior to 1980

    L. Name: ice_off_anomaly
       Description: The anomaly of ice-off taken as the difference between the julian ice-off date for the current year and the 1980 mean ice-off date. (current ice-off date - long term ice-off date). Negative numbers signify earlier ice-off.

    M. Name: julian_day
       Description: Day of year sampling occurred (January 1st is 1, February 1st is 32, etc.)

-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: yoy_data.csv
-----------------------------------------

File contains walleye young-of year relative abundance data from MN lakes indexed through electrofishing

1. Number of variables: 22

2. Number of cases/rows: 2433

3. Missing data codes:
        Code/symbol        NA

4. Variable List
                  
    A. Name: lake_id
       Description: 6-7 digit code to identify the waterbody

    B. Name: year
       Description: Year of sampling event 

    C. Name: lake_name
       Description: Name used for the lake

    D. Name: nhdhr_id
       Description: Unique Id for the lake that is used by the National hydrology dataset.

    E. Name: water_temp
       Description: Surface water temperature at the time of sampling.

    F. Name: date_survey
       Description: The date of the survey

    G. Name: date_sample
       Description: The date of the survey if it occurred over several days (relic from larger dataset).

    H. Name: total_effort_1
       Description: The effort associated with the sampling effort. Effort is expressed as the number of hours of "pedal-on" time for an electrofishing boat

    I. Name: catch
       Description: Number of young-of-year walleye caught

    J. Name: CPUE
       Description: Catch-per-unit-effort for young-of-year walleye (catch/total_effort_1).

    K. Name: julian_day
       Description: Day of year sampling occurred (January 1st is 1, February 1st is 32, etc.)

    L. Name: acres
       Description: The surface area of the lake in acres

    M. Name: shore_mi
       Description: the length of the shoreline in miles.

    N. Name: x
       Description: Latitude of the lake center point (WGS1984)

    O. Name: y
       Description: Longitude of the lake center point (WGS1984)

    P. Name: FRY
       Description: Number of spring walleye fry stocked in the lake in that year

    Q. Name: FGL
       Description: Number of fall walleye fingerlings stocked in the lake in that year

    R. Name: ADL
       Description: Number of adult walleye stocked in the lake in that year

    S. Name: YRL
       Description: Number of yearling walleye stocked in the lake in that year

    T. Name: FRL
       Description: Number of summer walleye frylings stocked in the lake in that year

    U. Name: fry.pa
       Description: Binary variable describing if any walleye fry stocked in the lake in that given year

    V. Name: STOCKED
       Description: Binary variable describing if any walleye were stocked in the lake in that given year



-----------------------------------------
DATA-SPECIFIC INFORMATION FOR: gillnet_aged_lake_year.csv
-----------------------------------------

File contains walleye adult relative abundance data from MN lakes indexed through standardized gillnets

1. Number of variables: 22

2. Number of cases/rows: 45208

3. Missing data codes:
        Code/symbol        NA

4. Variable List
                  
    A. Name: birth.year
       Description: Year that the walleye cohort was born 

    B. Name: lake.id
       Description: 6-7 digit code to identify the waterbody

    C. Name: lake.name
       Description: Name used for the lake

    D. Name: date
       Description: The starting date of the gillnet survey

    E. Name: year
       Description: Year of sampling event 

    F. Name: total.effort.1
       Description: The effort associated with the sampling effort. Effort is expressed as the number of "net-nights".

    G. Name: sampling.method
       Description: The sampling method. One of either "Standard gill net sets" or "Standard gill nets, set shallow in stratified assessment".

    H. Name: effort_ident
       Description: The unique id for the gill net survey.

    I. Name: est.age
       Description: The age of the fish estimated from a lake or lake-year age-length key (https://doi-org.ezp1.lib.umn.edu/10.1002/fsh.11019)

    J. Name: count
       Description: Number of adult walleye caught in the identified age-class.

    K. Name: cpue
       Description: Catch-per-unit-effort for adult walleye (count/total.effort.1).

    L. Name: jd
       Description: Julian day of year sampling occurred (January 1st is 1, February 1st is 32, etc.)

    M. Name: acres
       Description: The surface area of the lake in acres

    N. Name: shore_mi
       Description: the length of the shoreline in miles.

    O. Name: x
       Description: Latitude of the lake center point (WGS1984)

    P. Name: y
       Description: Longitude of the lake center point (WGS1984)

    Q. Name: non.fry
       Description: Identifier for if any fish besides fry were stocked into the lake. NA or 0 mean no fish were stocked and any number one or greater is the sum of the amount of life stages of walleye that were stocked.


Results from sessionInfo()
R version 4.1.2 (2021-11-01)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 10 x64 (build 22631)

Matrix products: default

locale:
[1] LC_COLLATE=English_United States.1252  LC_CTYPE=English_United States.1252    LC_MONETARY=English_United States.1252 LC_NUMERIC=C                          
[5] LC_TIME=English_United States.1252    

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] wiqid_0.3.3                mcmcOutput_0.1.3           HDInterval_0.2.4           cowplot_1.1.1              readxl_1.4.2              
 [6] mnsentinellakes_0.0.0.9000 gratia_0.7.2               arrow_13.0.0.1             mgcv_1.8-38                nlme_3.1-153              
[11] sf_1.0-10                  lubridate_1.9.3            forcats_1.0.0              stringr_1.5.0              dplyr_1.1.4               
[16] purrr_1.0.1                readr_2.1.4                tidyr_1.3.0                tibble_3.2.1               ggplot2_3.4.1             
[21] tidyverse_2.0.0.9000      

loaded via a namespace (and not attached):
 [1] bit64_4.0.5        splines_4.1.2      assertthat_0.2.1   cellranger_1.1.0   yaml_2.2.1         pillar_1.9.0       lattice_0.20-45    glue_1.8.0        
 [9] digest_0.6.29      RColorBrewer_1.1-3 colorspace_2.0-3   htmltools_0.5.8.1  Matrix_1.5-3       pkgconfig_2.0.3    patchwork_1.1.1    scales_1.3.0      
[17] tzdb_0.2.0         timechange_0.2.0   proxy_0.4-26       generics_0.1.2     farver_2.1.1       withr_2.5.2        cli_3.6.1          magrittr_2.0.3    
[25] crayon_1.5.2       mvnfast_0.2.7      evaluate_0.23      fansi_1.0.3        MASS_7.3-54        truncnorm_1.0-8    class_7.3-19       textshaping_0.3.7 
[33] tools_4.1.2        hms_1.1.3          lifecycle_1.0.3    munsell_0.5.0      compiler_4.1.2     e1071_1.7-9        systemfonts_1.0.4  rlang_1.1.4       
[41] classInt_0.4-3     units_0.8-0        grid_4.1.2         rstudioapi_0.15.0  labeling_0.4.2     rmarkdown_2.13     gtable_0.3.1       DBI_1.1.2         
[49] R6_2.5.1           knitr_1.39         fastmap_1.1.0      bit_4.0.4          utf8_1.2.2         ragg_1.2.6         KernSmooth_2.23-20 stringi_1.7.8     
[57] parallel_4.1.2     Rcpp_1.0.10        vctrs_0.6.5        tidyselect_1.2.1   xfun_0.39          coda_0.19-4.1   