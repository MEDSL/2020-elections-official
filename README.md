# 2020-elections-official

This is the MEDSL repository for official precinct returns for 2020 General Election.

 Users can download data by the level of office returns (president, US senate, US house, state, or local levels). For each state that is complete, users can also download all of the precinct-level returns separately in the folders above.
 
![Screenshot](precinct_progress_map_2021-09-07.png)



The returns are in progress, and will be updated periodically until completion. The following states and districts are included in the dataset:

## Alabama

Added 02-22-2021. Local data not included at the moment. Overvotes and Undervotes were not reported on offical canvas results so were not verified.

## Alaska

Added 02-23-2021. 

## Arizona

Added 09-07-2021. Local data not included at the moment. Precinct data for write-in candidates currently unavailable.

## Arkansas

Added 02-16-2021. Local data not included at the moment.

## California

Added 07-29-2021. Local data not included at the moment.

* Votes for Ventura County State Senate District 19 were listed as 0 in the official precinct results. The county aggregate results were added with the precinct "COUNTY FLOATING". All State Senate District 19 rows are subsequently marked 'readme_check == "TRUE"'.

## Colorado

Added 08-26-2021.

## Connecticut

Added 02-22-2021. Local data not included at the moment.

There were a small number of discrepancies between our cleaned precinct results and the results from the Secretary of State's website (https://ctemspublic.pcctg.net/#/selectTown). These seem to be from a couple of duplicate rows in the exported data, which we have removed in our cleaned data. This means that for a small number of offices, we will report a slightly lower number of total votes than the results posted online. 

Here are the discrepancies:

For office STATE SENATE district 024, SUSAN CHAPMAN has 823 in our data instead of 827 reported online

For office US HOUSE district 003, MARGARET STREICKER has 6026 in our data instead of 6030 reported online

For office US PRESIDENT, HAWKINS AND WALKER has 7529 in our data instead of 7538 reported online

For office US PRESIDENT, JORGENSEN AND COHEN has 20225 in our data instead of 20230 reported online

## Delaware

Added 08-19-2021.

* The “precinct” field for Delaware’s cleaned results is formatted as “Election District #-State House District #”. This is following the format of Delaware’s Election District Structure as seen at https://elections.delaware.gov/districtmaps/pdfs/EDRD2012_2022v1.pdf This is reversed from the format of the precinct/election district name published in the official results, to remain consistent with previously cleaned election results from 2016/2018.

* Precincts 17-41 and 17-31 received 0 votes in the official results. These precincts are not present in previous election returns.

## District of Columbia

Added 01-29-2021. For DC, the jurisdiction_name variable indicates ward number. Local data not included at the moment.

## Florida

Added 03-08-2021. Local data not included at the moment. 

* Overvotes, Undervotes and some write-in candidate votes were not reported on offical canvas results so were not verified.

There are a number of very small discrepancies between our precinct data and  in the Florida data. Most of the discrepancies, when looking at aggregate vote totals, are less than 10 votes. The discrepancies come from Monroe County, Seminole County, and for some of the elections that had recounts. Here is a list of offices and districts with small discrepancies:

All statewide offices, including us president, supreme court, and all of the constitutional amendments

CIRCUIT JUDGE		15TH JUDICIAL CIRCUIT, GROUP 30

US HOUSE			District 007

US HOUSE			District 026

STATE SENATE		District 009

STATE SENATE		District 037

STATE SENATE		District 039

STATE HOUSE			District 028

STATE HOUSE			District 029

STATE HOUSE			District 030

STATE HOUSE			District 120

## Georgia

Added 03-18-2021. Local data not included at the moment.

## Hawaii

Added 04-02-2021. 

## Idaho

Added 04-05-2021. Local data not included at the moment.

* For Constitutional Amendment HJR 4, Power County reported 2,017 votes for YES (https://sos.idaho.gov/elections-division/2020-results-statewide/) while the raw data reported 1,967 votes. This accounts for the entirety of the vote difference when comparing the Secretary of State total (525,779) versus the raw data total (525,729).

## Illinois

Added 03-31-2021. Local data not included at the moment.

* Official IL results report only certain individual write-in candidates, while precinct data reports scatter wrtie-ins

* Judge McGlynn (District 020 Retention Race) is missing from official IL results. They were nominated and approved to serve in a federal district court in 2020.

## Iowa

Added 05-06-2021. Local data not included at the moment.

* Counts in the race for US HOUSE District 2 in Scott County are short by a total of 184 votes across all candidates.

## Kansas

Added 05-17-2021. Local and Judicial District Court data and not included at the moment. 

## Kentucky

Added 08-04-2021. Local data not included at the moment.

* Kentucky precinct data source is: https://results.enr.clarityelections.com/KY/106379/web.264614/#/summary. These results are "unofficial", thus vote totals are marginally undercounted in certain counties/races. 

* Certain Kentucky counties do not report data at the precinct level, either aggregated by voting mode at the county level or total votes at the county level. Certain Kentucky counties chose to centralize voting at the county level, allowing voters to vote at any open polling location as a result of poll closures during the COVID-19 pandemic. Such counties are marked in the precinct field as "COUNTY FLOATING".

## Louisiana

Added 04-20-2021. Local data not included at the moment.

## Maine

Added 07-01-2021.

* Maine reports election results at the township level, rather at the precinct level. Township/municipality is treated as precinct in the cleaned data. 

* Certain rows contain county-fips info in place of jurisdiction-fips info for one of two reasons: (1) Maine reports state UOCAVA vote totals for each candidate aggregated at the county level. (2) Township information for certain towns could not be matched to our jurisdiction-fips merger file. 


## Maryland

Added 02-09-2021. Local data not included at the moment.

## Massachusetts

Added 02-19-2021. Local data not included at the moment. State legislative results added 03-23-2021.

## Michigan

Added 07-16-2021. Local data not included at the moment.

* Precinct data are taken from https://miboecfr.nictusa.com/cgi-bin/cfr/precinct_srch.cgi?elect_year_type=2020GEN&county_code=00&Submit=Search

* Precinct data contain precinct "9999", which are "statistical adjustments" rows that must be carefully considered when aggregating vote totals by office/county. 

* Vote totals aggregated by county that include this 9999 precinct do not match the official county totals for every race.

* Vote totals aggregated by county that DO NOT include this 9999 precinct do not match the official county totals for every race either, but are significantly closer to the official totals than when the 9999 precinct rows are kept.

* All rows that have a discrepancy when aggregated by county (with or without the 9999 precinct rows) are marked readme_check == "TRUE". 

* More information about "9999" precincts and the nature of the discrepancies will be added to the README.md as we receive it.


## Minnesota

Added 04-26-2021. No local data available at the moment.

* Some candidates for state legislature are missing from the precinct-level raw data:
- Joshua Price (state senate district 16)
- Myron Arthur Wilsom (state rep district 15B)
- Antonio Nerios (state rep district 43B)
- Lisa Neal-Delgado (state rep district 59B)
- Calvin Lee Carpenter (state rep district 60A)

## Mississippi

Added 05-10-2021. No local data available at the moment.

* Only includes US President, US Senate, and US House results at the moment.

* Many of the race totals are off by a handful of votes, and we are not able to identify the individual precincts which are off. 

* Here are some of the discrepancies reported for president. (Values in parentheses are how much higher or lower our data is relative to what is reported in official results, i.e. MEDSL total minus the official reported total.)

STATEWIDE
Trump (+102)
Biden (-1814)

Counties with discrepancies:

Trump
AMITE (+80)
COAHOMA (+25)
KEMPER (-3)

Biden
BOLIVAR (-200)
COAHOMA (+111)
COVINGTON (-3)
HINDS (-1400)
SCOTT (-322)

## Missouri

Added 07-27-2021. No local data available at the moment.

## Montana

Added 02-02-2021.

## Nebraska

Added 08-04-2021.

## Nevada

Added 06-02-2021. Local data not included at the moment.

* From the official Nevada 2020 Election results spreadsheet: "Note: In cases where the cumulative turnout for a precinct for a race or ballot question is greater than 0 but less than 10, the numbers have been replaced with an asterisk in order to protect the secrecy of a voter's ballot, as required by Nevada Law. As a result, the total for a precinct may be different from what is reported on official documents." 
* We have included these cases in our cleaned results, replacing the asterisk with -1 to preserve the votes values as ints. These results should be dropped when aggregating results at the state/county level. Certain county aggregated results in affected races are marginally different from the official reported vote totals due to the masking of votes for privacy purposes.

## New Hampshire

Added 07-13-2021.

* Districts marked with an F are floterial districts.

* State House district numbers reset for every county. Thus, state house members need to have their districts concatenated with county when inspecting district information.

* Our aggregated results do not match official totals for certain races. Those races include (but may not be limited to):
- All County Register of Probate candidates in Grafton County (Excel spreadsheet sum cells missed two rows).
- Scatter candidates in State House District 18 in Strafford County (Sum cell is off by one).

* No full names could be found for writein candidates Teszler and Townsend for County Register of Probate in Grafton County.

* Recounts in the state do not seem to include scatter votes, so they were not included. This explicitly affects all races with stage 'GEN RECOUNT' but State Senate District 12 (which did not list any scatters for the original race either).

## New Mexico

Added 03-28-2021. Local data not included at the moment.

* New Mexico "masks" vote totals in precinct results for candidates with small vote tallies, to protect the privacy of voters. These masked votes are denoted as "-1" in the votes column.

## North Carolina

Added 01-27-2021.

## North Dakota

Added 02-24-2021. Local data and state legislative election results not included at the moment.

## Ohio

Added 03-16-2021. Local data not included at the moment.

Ohio records its data with precincts on rows and candidates on columns. However, they record candidates that were not selectable in a particular precinct (because they did not run in a the associated district) as having received 0 votes, which is otherwise indistinguishable from candidates who ran in a precinct but received no votes. Keeping all these entries as is yields over 3 million records records and an extremely large file, so 0 vote records were manually dropped as follows:
  - Records for candidates running for US President were kept as is.
  - For all other records, entries with 0 votes were discarded.
This leads to the situation where every other race (including US House, State Senate and State House elections, which are district based but do not list name of county) will have more records than needed removed (namely, records of candidates who ran in a precinct but got 0 votes there).

Ohio does not provide precinct-based vote totals for writein candidates, but they do provide a county-based vote total for each writein. The cleaned dataset aggregates all writeins per office on a county basis.

## Oklahoma

Added 02-01-2021. Local data not included at the moment.

## Oregon

Added 08-27-2021. Only includes presidential data at the moment.

## Rhode Island

Added 07-16-2021.

## South Carolina

Added 05-13-2021. Local data not included at the moment.

## South Dakota

Added 07-16-2021. Local data not included at the moment.

* State house district 012 features original results and recount results. The two counts are differentiated by the mode field (either "GEN" or "GEN RECOUNT").

## Tennessee

Added 01-28-2021. Local data not included at the moment.

## Texas

Added 07-12-2021. Local data not included at the moment.

* Raw data were obtained from the Texas Legislative Council (https://data.capitol.texas.gov/dataset/2020_general). 

* When comparing the precinct results to the official county results, MEDSL identified a list of precinct results (aggregated by county/office/candidate/district) that do not match the offical totals. The majority of discrepancies are insignificant relative to the total votes, but larger counties (eg Williamson), have more substantial discrepancies. Documentation containing the exact vote total discrepancies is available upon request. 

* The Texas Legislative Council data contains breakdown by Voting Tabulation District (VTD). This is treated as the precinct field in our data. The number of VTDs in a county do not always match the number of precincts in a given county (https://data.capitol.texas.gov/topic/about/elections)

* Races where candidates ran unopposed and recieved 100% of the votes were not included in the raw precinct data.

## Utah

Added 03-16-2021. Local data not included at the moment.

* Duchesne county is short one vote compared to official sources (https://electionresults.utah.gov/elections/). As such, the county of Duchesne is flagged readme_check==True. 

## Vermont

Added 07-06-2021. 

* For State Senate races, Vermont has floating towns: towns that are physically located in one county but vote for senator in another county, so special care must be taken care off when aggregating votes. These towns are marked in the precinct column with " - FLOAT" and affect the following races:
- Addison State Senate: Huntington is in Chittenden County and votes for Addison State Senator.
- Bennington State Senate: Wilmington is in Windham County and votes for Bennington State Senator.
- Caledonia State Senate: Bradford, Fairlee, West Fairlee, Newbury, Topsham are in Orange County and vote for Caledonia State Senator.
- Essex-Orleans State Senate: Wolcott is in Lamoille County and votes for Essex-Orleans State Senator.
- Franklin State Senate: Alburgh is in Grand Isle County and votes for Franklin State Senator.
- Grand Isle State Senate: Colchester is in Chittenden County and votes for Grand Isle State Senator.
- Windsor State Senate: Londonderry is in Windham County and votes for Windsor State Senator.

## Virginia

Added 01-27-2021.

Many of the write-in candidates in the Virginia elections show small discrepancies between the vote totals reported on the Virginia SOS website (here: https://results.elections.virginia.gov/vaelections/2020%20November%20General/Site/Presidential.html) and the votes in the raw data sheets. 

## Washington

Added 01-27-2021. Local data not included at the moment.

## West Virginia

Added 06-02-2021. Local data not included at the moment.

## Wisconsin

Added 01-29-2021.

## Wyoming

Added 02-03-2021.
