# License Declared

Question: What are the declared software package licenses?

## Description
The total number and specific licenses declared in a software package. This can include both software and documentation source files.

### Formula
This metric is an enumeration of licenses, and the number of files with that particular license declaration. For Example:

| SPDX License Type  | Number of Files with License    | License Notes  |
| ------------- |-------------| -----|
| MIT      | 44 | None |
| AGPL      | 2      |   Pending removal |
| Apache | 88      |   None |


## Objectives

The total number and specific licenses declared is critical in several cases:
1. A software package invariability carries for multiple software licenses and it is critical in the acquisition of software packages to be aware of the declared licenses for compliance reasons. Licenses Declared can provide transparency for license compliance efforts.
2. Licenses can create conflicts such that not all obligations can be fulfilled across all licenses in a software package. Licenses Declared can provide transparency on potential license conflicts present in software packages.

## Sample Filter and Visualization
### Filters
* Time: Licenses declared in a repository can change over time as the dependencies of the repository change. One of the principle motivations for tracking license presence, aside from basic awareness, is to draw attention to any unexpected new license introduction.
* Declared and Undeclared: Separate enumeration of files that have license declarations and files that do not.

## Reference Implementation
The DoSOCSv2 package is implemented as an Augur Plugin, and uses this data model for storing file level license information. Specifically:
* Each `package` (repository) can have a declared and declared license, as determined by the scan of all the files in the repository.
* Each `package` can also have a number of different non-code `documents`, which are SPDX license declarations.
* Each `file` can be associated with one or more `packages_files`. Through the relationship between `files` and `packages_files`, DoSOCSv2 allows for the possibility that one file in a large collection of repositories could be part of more than one package, although in practice this seems unlikely.
* `packages` and `packages_files` have a one to many relationship in both directions. Essentially, this is a reinforcement of the possibility that each `file` can be part of more than one `package`, though it is, again, typical that each `package` will contain many `package_files`.
* `licenses` are associated with `files` and `packages_files`. Each `file` could possibly have more than one `licenses` reference, which is possible under the condition that the `license` declaration changed between `DoSOCSv2` scans of the repository. Each `package` is stored in its most recent form, and each `packages_file` can have one `license` declaration.
![](https://github.com/chaoss/wg-risk/blob/master/metrics/images/licenses-DoSOCS2.png)

### Sample SQL to Extract License Information from a Package File
```sql
SELECT A
    .file_name,
    b.license_id,
    b."name" AS declared_license
FROM
    packages_files A,
    licenses b
WHERE
    A.declared_license_id = b.license_id
```

## Known Implementations
* [Augur](https://github.com/chaoss/augur)

### Examples
* Available in the Augur test schema for these repositories:
    - portable
    - openBSD
    - boringSSL

## Resources
* https://spdx.org/
* https://www.fossology.org
