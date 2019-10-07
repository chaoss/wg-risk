## 1. Description
The Linux Foundation (LF) Core Infrastructure Initiative (CII) Best Practices badge is a way for Free/Libre and Open Source Software (FLOSS) projects to show that they follow best practices. Projects can voluntarily self-certify, at no cost, by using this web application to explain how they follow each best practice. 

CII badging indicates a projects level of compliance with “open source project best practices" as defined by the Linux Foundation's core infrastructure initiative, which focuses on CyberSecurity in open source software. The goal of the program is to encourage projects to produce better more secure software and allow others to determine if a project is following best practices.

Projects receive the passing badge if they meet all of the required criteria. The status of each criterion, for a given project, can be 'Met', 'Unmet', 'N/A' or 'unknown'. Each criterion is in one of four categories: 'MUST', 'SHOULD', 'SUGGESTED', or 'FUTURE'. To obtain a badge, all MUST and MUST NOT criteria must be met, all SHOULD criteria must be met OR the rationale for not implementing the criterion must be documented, and all SUGGESTED criteria have to be rated as met or unmet.

## 2. Use Cases

Consumers of the badge can quickly assess which FLOSS projects are following best practices and as a result are more likely to produce higher-quality secure software. 

## 3. Formula

GET Request to CII Best Practices API with a specific URL -> JSON response with status information for the repository

## 4. Sample Filter and Visualization

![](https://i.imgur.com/mSformz.png)

## 5. Sample Implementation (JavaScript)

```
const owner = "box"
const repo = "bart"
//used as a sample repository
var request = new XMLHttpRequest();
              function loader() {
	            const basestr = owner + "/" + repo;
	            const augURL = 'https://github.com/' + basestr;
	            request.open('GET', 
                       'https://bestpractices.coreinfrastructure.org/projects.json?pq=' + augURL, true);
	            request.onload = function () {
    	        var data = JSON.parse(this.response)[0];
    	        if (data != undefined) {
        	        //console.log('CII NAME: ' + data.name);
        	        console.log(data)
        	   }
       };
    }
loader();
request.send();
```


## 6. Known Implementations

See https://github.com/Nebrethar/risk-flask for an isolated sample.

## 7. Test Cases (Examples)

The input is an API call; GET request to :
```
https://bestpractices.coreinfrastructure.org/projects.json?pq= + ciiURL
```
Where ciiURL is the URL that CII has on file for the project. This value is often a GitHub URL

Below is an example of a queryt that returns API data on zephyrproject-rtos/Zephyr
```
https://bestpractices.coreinfrastructure.org/projects.json?pq=zephyr
```
The output is a set of values pertaining to CII pest practices.
Here is a snippet of values from an API call regarding box/bart:
```
dynamic_analysis_enable_assertions_justification: ""
dynamic_analysis_enable_assertions_status: "?"
dynamic_analysis_fixed_justification: ""
dynamic_analysis_fixed_status: "?"
dynamic_analysis_justification: ""
dynamic_analysis_status: "?"
dynamic_analysis_unsafe_justification: ""
dynamic_analysis_unsafe_status: "?"
english_justification: "https://github.com/box/bart/wiki and GitHub support for bugs. "
english_status: "Met"
enhancement_responses_justification: ""
enhancement_responses_status: "?"
external_dependencies_justification: null
external_dependencies_status: "?"
floss_license_justification: "The Apache-2.0 license is approved by the Open Source Initiative (OSI)."
floss_license_osi_justification: "The Apache-2.0 license is approved by the Open Source Initiative (OSI)."
floss_license_osi_status: "Met"
floss_license_status: "Met"
general_comments: ""
governance_justification: null
governance_status: "?"
hardened_site_justification: null
hardened_site_status: "?"
hardening_justification: ""
hardening_status: "?"
​homepage_url: "https://github.com/box/bart"
homepage_url_justification: null
homepage_url_status: "?"
​id: 84
implement_secure_design_justification: null
​implement_secure_design_status: "?"
​implementation_languages: "PHP, Shell (CII estimate)"
input_validation_justification: null
```

## 8. External References (Literature)

CII Badging Website: https://bestpractices.coreinfrastructure.org/en
