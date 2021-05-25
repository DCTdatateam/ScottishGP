# ScottishGP
Locations of Scottish GP surgeries and Patient to GP ratios


The source data for the map are available here:
https://www.isdscotland.org/Health-topics/general-practice/workforce-and-practice-populations/

Unfortunately most of those spreadsheets only list the practice code rather than the practice name, which make them not very user friendly. We joined the datasets using a simple VLOOKUP.
The GP numbers were calculated using a pivot table on the “List of GP details” spreadsheet and also joined using VLOOKUP.
The patients per GP data was a simple calculation based on the number of GPs and the number of patients registered (the “all ages” category of the list sizes spreadsheet). The age %s are also just a SUM of the age ranges/all ages.

The complete dataset can be found in the repository – accurate as at April 1 2021.

Geocoding
To geocode the surgery addresses we first concatenated the ‘name’, ‘address’ and ‘postcode’ columns to create an address string.
We then used a geocode API via a google sheet following instructions from Will Geary:
https://willgeary.github.io/data/2016/11/04/Geocoding-with-Google-Sheets.html
The google app script can be found in our repository
