## 1. Description
A software package has a standard expression of dependencies, licensing, and security-related issues. 

## 2. Use Cases
For managers acquiring open source software as part of an IT or Open Source Program Office portfolio, the "Software Bill of Materials" ("SBOM") is an increasingly essential "core piece of management information".  This arises because, as software packages exist in complex software supply chains, it is important to clearly express, in a standardized way, the associated dependencies, licenses, and security-related issues with that software package. A Software Bill of Materials provides a single source document that provides this information both for internal use and downstream distribution of software packages. A Software Bill of Materials assists in how organizations routinize open source work to better integrate with their own open source risk management routines.

## 3. Formula
This is an enumeration of a "bill of materials", as as such is not expressed as a metric. It is more accurate to consider this CHAOSS metric as an "inventory of components" that is uniquely important in many risk oriented open source software acquisition conversations. 

## 4. Sample Filter and Visualization
DoSOCSv2 was used to scan the GitHub Repository. Here are some of the core license values from the scan, which may be used as an example of the format:
```
LicenseID: LicenseRef-See-URL
LicenseName: See-URL
ExtractedText: com/license
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Dual-license
LicenseName: Dual-license
ExtractedText:  MIT or new BSD license.
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-BSD
LicenseName: BSD
ExtractedText: Available via the MIT or new BSD license.
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Python
LicenseName: Python
ExtractedText: license. Your class definition should look\nsomething like this:\n\n.. code:: python\n\n #SPDX-License
LicenseCrossReference:
LicenseComment: found by nomos

LicenseID: LicenseRef-Non-profit
LicenseName: Non-profit
ExtractedText: nonprofit
LicenseCrossReference:
LicenseComment: found by nomos
```
A full text file for this scan may be found here:
https://drive.google.com/file/d/18ClTeQo64sU8dVzSQDMYzO6jLHHa9TPg/view?usp=sharing


## 5. Sample Implementation
A file by file SBOM is available with Augur configured using the DoSOCSv2 plugin.  The relevant parts of the database schema are illustrated below. The most important points, from an SBOM perspective, is simpler than the software licensing metrics described elsewhere.  For the SBOM, we simply look at the enumeration of : 
1. Packages
2. Package_Files
3. Files (which may be, but are unlikely to be also included in other packages). 
License information is included as part of an SBOM, but the complexity of license identification is clarified in the [License_Count](./License_Count.md), [License_Coverage](./License_Coverage.md), and [License_Declared](./License_Declared.md) metrics. 
![](./images/SBOM.png)

## 6. Known Implementations
1. DoSOCSv2 embedded as an Augur Service. 

## 7. Test Cases (Examples)
**See the sample filter and visualization section of this metric**. 

## 8. External References (Literature)
1. https://spdx.org  
