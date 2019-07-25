# Reporting Services Date Selector Sample

This sample allows you a mechanism to introduce a date range into your where clause for your SQL Server Reporting Services report. This method can also be easily extended to access fields other than dates.

This sample does not include the Reporting Services report, but just the mechanism to call your own report and build the URL to include the variables for the date range. However, you will need to have an existing report and SSRS installation to test against. 

## History

Release | Notes
--------|--------
[v2.0.0](https://github.com/ArasLabs/ssrs-date-selector/releases/tag/v2.0.0) | Updated for Aras v11; expanded readme w/ usage 
[9.3v1](https://github.com/ArasLabs/ssrs-date-selector/releases/tag/9.3v1) | Initial Post

#### Supported Aras Versions

Project | Aras
--------|------
[v2.0.0](https://github.com/ArasLabs/ssrs-date-selector/releases/tag/v2.0.0) | v11 (SP12, 15 tested) 
[9.3v1](https://github.com/ArasLabs/ssrs-date-selector/releases/tag/9.3v1) | v9.3 

## Installation

#### Important!
**Always back up your code tree and database before applying an import package or code tree patch!**

### Pre-requisites

1. Aras Innovator installed
2. Aras Package Import tool
3. **SSRSDateSelector** import package
4. SSRS Installed*
   - See the Aras Microsoft Reporting Services [server version] documentation for assistance with installation
   - You may also need an edition of Visual Studio to design a report
5. A SSRS-based report to use with the package (including a date-based field to filter on)
   - You will need Parameters in your report to accept the fromDate and toDate being output in the method, otherwise change the names as appropriate.

### Install Steps

1. Backup your database and store the BAK file in a safe place.
2. Open up the Aras Package Import tool.
3. Enter your login credentials and click **Login**
	* _Note: You must login as root for the package import to succeed!_
4. Enter the package name in the TargetRelease field.
	* Optional: Enter a description in the Description field.
5. Enter the path to your local `..\SSRSDateSelector\Import\imports.mf` file in the Manifest File field.
6. Select all in the Available for Import field.
7. Select Type = **Merge** and Mode = **Thorough Mode**.
8. Click **Import** in the top left corner.
9. Close the Aras Package Import tool.

### Usage

1. Open Aras Innovator as Admin
2. Navigate to **Administration > Reports**
3. Select the SSRS Date Selector Report, and open the attached Method.
4. Replace the report name around line 25 with the report you wish to execute using this method.
5. If you wish the report to output in Excel or PDF switch the appropriate comment on or off here
6. Save the method.
7. Switch your view out of the method tab so you have access to general reports, select the reports menu dropdown, and click the SSRS Date Selector report.
8. Input dates as appropriate to filter and run the report.
9. Verify your results.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## Credits

Created by Aras Corporation Support. Update assistance from @angelalp for Version 11. Updated by @sampoearas

## License

Published to Github under the MIT license. See the [LICENSE file](./LICENSE.md) for license rights and limitations.
