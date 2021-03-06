## Differences between these results and the Phase 1 results for this model.

The outputs are not the same as the originals.  In addition to the *_tract_building_fire_per_1k.csv files,
states_coverage.csv relies on the data files

    national_county.txt
    us2010trf.txt

These files could not be found in the originals Google folder (at least not by these names), so we had to find them online at https://www2.census.gov/geo/docs/reference/codes/files/ 
and https://www2.census.gov/geo/docs/maps-data/data/rel/trf_txt/, respectively.  This could also be producing a different result.

-- from September 2018 update --

The prior issue has not been solved yet.

We are dealing with a new data source NFIRS_2009_2016.txt.  This data is different than the original basic_incident.txt and fire_incident.txt, and it is said to be more accurate (it filters out fires such as auto that **were** included previously).  Therefore, our results should be different than before (so we will ignore the issues from earlier for now).  Validation cannot be done, even when the years are filtered.  2012 results were examined, just in case, and it can be seen that the new results (labeled with **new**) are not comparable to the Original results or the August 2018 results (which were the most similar to the Original results).  

The code phase1-code-modified.R is the original code changed to account for the different data source.

-- from August 2018 update ---

The code in phase2-code/phase1-code-documented.R, for the July update, did not take into consideration the fire_incident.txt and basic_incident.txt for all years.  The code in the repository is now updated appropriately, and so is the input and output data.  The output are seemingly accurate.  The first 800 or so entries of each file are exactly the same as the Original's results.  However, the remaining elements are not.  Therefore, the relative error is too large.  Next step is to determine the issue.

--- from July 2018 update ---

In May 2018, model was validated, but resulting data is empty?  Perhaps the validating volunteer accidentally emptied data.  However, when the same code is implemented, do not get results as before but get empty data.  Still working through what the issue is, but have found a "fix".  The July 2018 data is the result.

A few differences in the lines of code may have attributed to result differences.  For example, for 2013_tract_building_fire_per_1k, our replicated results vary by 0.7% from the Original's results according to the relative percentage  

    *||ours - theirs||_2 / ||theirs||_2*.  

For the number of entries that differ, the Original's result is 19 entries longer and only 872 elements are exactly the same (to get the percentage previously stated, the differing elements may be relatively close in value).

**Note**, although the primary code in July 2018 get different *_tract_building_per_1k data, the states_coverage.csv seems to be the same, but different than the Original's states_coverage.csv.


