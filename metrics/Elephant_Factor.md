## 1. Description
The minimum number of companies whose employees perform a parameterizable definition of the total percentage of commits in a software repository is a project's 'elephant factor'. For example, one common filter is to say the elephant factor is to say 50% of the commits are performed by `n companies` and that is the elephant factor. One would begin adding up to the parameterized percentage using the largest organizations making contributions, and then the next largest and so on. So, for example, a project with 8 contributing organizations who each contributed 12.5% of the commits in a project would, if the elephant factor is parameterized at 50%, have an elephant factor of "4". If one of those organizations was responsible for 50% of commits in the same scenario, then the elephant factor would be "1". 

Elephant Factor provides an easy-to-consume indication of the minimum number of companies performing a parameterized filter (i.e. 50%) of the work. The origin of the term "elephant factor" is not clearly delineated in the literature, though it may arise out of the general identification of software sustainability as a critical non-functional software requirements by Venters et al (2014).  

## 2. Use Cases
A company evaluating open source software products might use an elephant factor to compare how dependent each projects is on a small set of corporate contributors. Projects with low elephant factors are intuitively more vulnerable to decisions by one enterprise cascading through any enterprise consuming that tool. The parameterized filter should reasonably be different for a project to which 1,000 organizations contribute than one to which, perhaps 10 contribute. At some volume of organizational contribution, probably something less than 1,000 organizations, elephant factor is likely not a central consideration for software acquisition because reasonable managers will judge the project not vulnerable to the decisions of a small number of actors. Such thresholds are highly contextual. 

## 3. Formula
Essentially, the formula for elephant factor is a percentile calculation. If we have 8 organizations who each contribute the following number of commits to a project: `1000,202,90,33,332,343,42,433`, then we can determine the elephant factor by first identifying the 50th percentile of total commits for all the companies. 

**Summary:** 50th percentile = 267, so the elephant factor is 4. 

**Full Solution:** 
1. Arrange the data in ascending order: 33, 42, 90, 202, 332, 343, 433, 1000
2. Compute the position of the pth percentile (index i):
   -  `i = (p / 100) * n), where p = 50 and n = 8`
   -  `i = (50 / 100) * 8 = 4`
3. The index i is an integer ⇒ the 50th percentile is the average of the values in the 3th and 4th positions (202 and 332 respectively)
4. Answer: the 50th percentile is (202 + 332) / 2 = 267, therefore the `elephant factor = 4`. 

## 4. Sample Filter and Visualization
1. Time: Reasonably the Elephant Factor will change if one takes a snapshot of any prior time period, so the elephant factor over the life of a product may misrepresent the current level of organizational diversity supported by the project. 
2. Repository Group: Many open source projects include multiple repositories, and in some cases examining all of the repositories associated with any given project provides a more complete picture of elephant factor. 

## 5. Sample Implementation
Bitergia's implementation of elephant factor is pictured below. 
![](../images/elephant_factor.png)

## 6. Known Implementations
1. Augur
2. Bitergia 


## 7. Test Cases (Examples)
The elephant factor can be calculated for any Augur repository in this manner. 

## 8. External References (Literature)
1. Colin C. Venters, Lydia Lau, Michael K. Griffiths, Violeta Holmes, Rupert R. Ward, Caroline Jay, Charlie E. Dibsdale, and Jie Xu. 2014. The Blind Men and the Elephant: Towards an Empirical Evaluation Framework for Software Sustainability. Journal of Open Research Software 2, 1. https://doi.org/10.5334/jors.ao
2. http://philslade.blogspot.com/2015/07/what-is-elephant-factor.html 
3. https://blog.bitergia.com/2016/06/07/landing-the-new-eclipse-open-analytics-dashboard/ 