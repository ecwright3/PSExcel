PSExcel: A Rudimentary Excel PowerShell Module
=============

This is a rudimentary PowerShell module for working with Excel via the [EPPlus](http://epplus.codeplex.com/) library.

* Thanks to Doug Finke for his [ImportExcel example](https://github.com/dfinke/ImportExcel/blob/master/ImportExcel) - hadn't seen EPPlus before this!
* Thanks to Philip Thompson for his [expansive module](https://excelpslib.codeplex.com/) illustrating how to work with EPPlus in PowerShell
* Thanks to the team and contributors behind [EPPlus](http://epplus.codeplex.com/) for a fantastic solution allowing .NET Excel interaction, without Excel.

Caveats:

* This covers limited functionality; contributions to this function or additional functions would be welcome!
* Minimal testing.  Will add Pester tests at some point.  Contributions welcome!

#Functionality

* Export random PowerShell output to Excel spreadsheets:
* Import Excel spreadsheets to PowerShell as objects
* No dependency on Excel being installed

![Example](/Media/Example.png)

#Instructions

```powershell
# One time setup
    # Download the repository
    # Unblock the zip
    # Extract the PSExcel folder to a module path (e.g. $env:USERPROFILE\Documents\WindowsPowerShell\Modules\)

# Import the module.
    Import-Module PSExcel    #Alternatively, Import-Module \\Path\To\PSExcel

# Get commands in the module
    Get-Command -Module PSExcel

# Get help for a command
    Get-Help Import-XLSX -Full

# Export data to an XLSX spreadsheet
    Get-ChildItem C:\ -File |
        Export-XLSX -Path C:\Files.xlsx

# Import data from an XLSX spreadsheet
    Import-XLSX -Path C:\Files.xlsx
```

#Notes

TODO:

* Import-XLSX should handle CSV data
* Export-XLSX should provide options similar to those Philip provides:
  * Format cells based on object type
  * Allow various common styles.
     * Freeze the top, or specify row/column to freeze on.
     * Format headers.  Perhaps bold. Or highlight the background.  Maybe not.
     * Alignment
