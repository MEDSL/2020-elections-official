# 2020-elections-official

MEDSL's official precinct data for state and federal office levels has been migrated to the Harvard Dataverse here: https://dataverse.harvard.edu/dataverse/2020_precincts

This is the MEDSL repository for local office level precinct returns for 2020 General Election. Local results are being hosted here until we obtain more complete data for missing states and ensure the data meets our quality assurance standards. If a user notices a mistake in a state's published local results, they are encouraged to raise an issue in this Github repository. 

 Users can download local level of office returns for all available states from the "all_states" folder, or by individual state from the "individual_states" folder.
 
General Note: The format of certain states precinct results sometimes lead to the inclusion of zero votes in a precinct. These rows are not systematically dropped due to the fact that these are not always errors as a result of formatting, but can sometimes reflect true precincts with no voters. There is no straightforward way to systematically identify and drop illegitimate zero-vote precincts while retaining legitimate ones. This means that sometimes there are location-office combinations that do not actually correspond to a real election that occurred, but in the data are assigned 0 votes (for example, a state house candidate might be listed as receiving 0 votes in a precinct that isn't actually part of their district). If a user plans to perform an analysis which might be sensitive to extra nonexistent 0 vote precincts, it is advisable to first double check that each of these precincts was really one of the locations where that race occurred.

The returns are in progress, and will be updated periodically until completion. The following states are included in the dataset:

## Alabama

Added 02-22-2021. 

## Alaska

Added 02-23-2021. 

## Arkansas

Added 02-16-2021. 

## Colorado

Added 08-26-2021.

## Connecticut

Updated 02-28-2022. 

* Small, marginal discrepancies are present between the raw aggregated precinct data from the state and the official reports (for certain offices).

## Delaware

Added 08-19-2021.

* The “precinct” field for Delaware’s cleaned results is formatted as “Election District #-State House District #”. This is following the format of Delaware’s Election District Structure as seen at https://elections.delaware.gov/districtmaps/pdfs/EDRD2012_2022v1.pdf This is reversed from the format of the precinct/election district name published in the official results, to remain consistent with previously cleaned election results from 2016/2018.

* Precincts 17-41 and 17-31 received 0 votes in the official results. These precincts are not present in previous election returns.

## District of Columbia

Added 01-29-2021. For DC, the jurisdiction_name variable indicates ward number.

## Florida

Added 03-08-2021. 

* There are a number of very small discrepancies between our precinct data and  in the Florida data. Most of the discrepancies, when looking at aggregate vote totals, are less than 10 votes. The discrepancies come from Monroe County, Seminole County, and for some of the elections that had recounts.

## Georgia

Added 03-18-2021.

## Hawaii

Added 04-02-2021. 

## Idaho

Added 04-05-2021.

## Illinois

Added 03-31-2021.

* Official IL results report only certain individual write-in candidates, while precinct data reports scatter write-ins

## Kentucky

Added 08-04-2021.

* Kentucky precinct data source is: https://results.enr.clarityelections.com/KY/106379/web.264614/#/summary. These results are "unofficial", thus vote totals are marginally undercounted in certain counties/races. 

* Certain Kentucky counties do not report data at the precinct level, either aggregated by voting mode at the county level or total votes at the county level. Certain Kentucky counties chose to centralize voting at the county level, allowing voters to vote at any open polling location as a result of poll closures during the COVID-19 pandemic. Such counties are marked in the precinct field as "COUNTY FLOATING".

## Louisiana

Added 04-20-2021.

## Maine

Added 07-01-2021.

* Maine reports election results at the township level, rather at the precinct level. Township/municipality is treated as precinct in the cleaned data. 

* Certain rows contain county-fips info in place of jurisdiction-fips info for one of two reasons: (1) Maine reports state UOCAVA vote totals for each candidate aggregated at the county level. (2) Township information for certain towns could not be matched to our jurisdiction-fips merger file. 

## Maryland

Added 02-09-2021.

## Montana

Added 02-02-2021.

## Nebraska

Added 08-04-2021.

## Nevada

Added 06-02-2021.

* From the official Nevada 2020 Election results spreadsheet: "Note: In cases where the cumulative turnout for a precinct for a race or ballot question is greater than 0 but less than 10, the numbers have been replaced with an asterisk in order to protect the secrecy of a voter's ballot, as required by Nevada Law. As a result, the total for a precinct may be different from what is reported on official documents." 
* We have included these cases in our cleaned results, replacing the asterisk with -1 to preserve the votes values as ints. These results should be dropped when aggregating results at the state/county level. Certain county aggregated results in affected races are marginally different from the official reported vote totals due to the masking of votes for privacy purposes.

## New Hampshire

Added 07-13-2021.

* Districts marked with an F are floterial districts.

* Our aggregated results do not match official totals for certain races. Those races include (but may not be limited to):
	- All County Register of Probate candidates in Grafton County (Excel spreadsheet sum cells missed two rows).
	- Scatter candidates in State House District 18 in Strafford County (Sum cell is off by one).

* No full names could be found for writein candidates Teszler and Townsend for County Register of Probate in Grafton County.

* Recounts in the state do not seem to include scatter votes, so they were not included. This explicitly affects all races with stage 'GEN RECOUNT' but State Senate District 12 (which did not list any scatters for the original race either).

## North Carolina

Added 01-27-2021. Updated 09-20-2021 to include sorted precinct data within "individual_states" zipfile. The file "2020-nc-precinct-general-sorted.csv" contains the mode for transfer ballots. Matching these votes to specific precincts introduces small amounts of error to the overall vote totals when aggregating by office/county.

Updated 03-14-2022.
* The raw data source for the sorted precinct results is: https://dl.ncsbe.gov/?prefix=ENRS/2020_11_03/results_precinct_sort/

* The codebook for the original fields in the raw sorted precinct results is: https://s3.amazonaws.com/dl.ncsbe.gov/ENRS/2020_11_03/layout_results_precinct_sort.txt

* The raw data for the sorted precinct results contains two precinct columns (number and name). We combine these fields in the latest update, separating with an underscore "_" (name_code). If the fields match exactly or one is left blank, we only report one field that contains information.

* The raw data sorted precinct results contains a field for the "group number", which is related to the voting mode. This field was initially excluded, but this introduced error to our version of the results in the form of near duplicate rows. Therefore, we have added the "Group number" to the mode field, separated by an underscore "_" (voting method_group number).


## Ohio

Added 03-16-2021. 

* Ohio records its data with precincts on rows and candidates on columns. However, they record candidates that were not selectable in a particular precinct (because they did not run in a the associated district) as having received 0 votes, which is otherwise indistinguishable from candidates who ran in a precinct but received no votes. Keeping all these entries as is yields over 3 million records records and an extremely large file, so 0 vote records were manually dropped as follows:
  - Records for candidates running for US President were kept as is.
  - For all other records, entries with 0 votes were discarded.
* This leads to the situation where every other race (including US House, State Senate and State House elections, which are district based but do not list name of county) will have more records than needed removed (namely, records of candidates who ran in a precinct but got 0 votes there).

* Ohio does not provide precinct-based vote totals for writein candidates, but they do provide a county-based vote total for each writein. The cleaned dataset aggregates all writeins per office on a county basis.

## Oklahoma

Added 02-01-2021. 

## Rhode Island

Added 07-16-2021.

## South Carolina

Added 05-13-2021.

## Texas

Added 07-12-2021.

* Raw data were obtained from the Texas Legislative Council (https://data.capitol.texas.gov/dataset/2020_general). 

* When comparing the precinct results to the official county results, MEDSL identified a list of precinct results (aggregated by county/office/candidate/district) that do not match the offical totals. The majority of discrepancies are insignificant relative to the total votes, but larger counties (eg Williamson), have more substantial discrepancies. Documentation containing the exact vote total discrepancies is available upon request. 

* The Texas Legislative Council data contains breakdown by Voting Tabulation District (VTD). This is treated as the precinct field in our data. The number of VTDs in a county do not always match the number of precincts in a given county (https://data.capitol.texas.gov/topic/about/elections)

* Races where candidates ran unopposed and recieved 100% of the votes were not included in the raw precinct data.

## Vermont

Updated 03-04-2022. 

* Vermont provides the township level data broken down further by representative districts within township. The precinct field is thus a combination of the "Township" and "Rep District" fields, separated by an underscore "_".


## Virginia

Added 01-27-2021.

* Many of the write-in candidates in the Virginia elections show small discrepancies between the vote totals reported on the Virginia SOS website (here: https://results.elections.virginia.gov/vaelections/2020%20November%20General/Site/Presidential.html) and the votes in the raw data sheets. 

## West Virginia

Added 06-02-2021.

## Wisconsin

Added 01-29-2021.

* 9 Two towns in Wisconsin (Waukesha, Waukesha County; Vernon, Waukesha County) were upgraded to villages in 2020 [1](https://www.jsonline.com/story/communities/waukesha/news/2020/05/06/town-waukesha-residents-ok-incorporation-referendum-huge-margin/5175520002/) [2](https://www.villageofvernonwi.org/newsdetail_T2_R397.php). However, both the [Wisconsin](https://doa.wi.gov/DIR/Changes_in_WI_Munis_2000.xlsx) and [US Census]  (https://www.census.gov/programs-surveys/acs/technical-documentation/table-and-geography-changes.html) directories do not reflect the changes. For the moment, their jurisdiction FIPS code is listed as the one they had while they were a town.

## Wyoming

Added 02-03-2021.
