
###Project Summary
I'll be reviewing GPS probe data from a set of fleet vehicles that conduct operations for a major US energy company.  The data flows from the [Ford Crew Chief][1] system to Telogis where I have access to raw sensor data from factory installed telematics devices (black boxes).
#### Goals
Primarily - the goal of the analysis will be to try to identify characteristics of operations and or driver behavior that lead to unsafe driving  - culminating in airbag deployment. The idea is that we will be able tip our customers off to the behavior or other circumstances that tend to lead up to a dangerous event.

Secondarily - any descriptive statistics may hold some value, I need to think on this, discuss w/ instructors and others at my company.


###Methodology
####Culling Data from [Telogis Data Exachange][2]
   - ~~Create Template that will pull History points~~
       - ~~All cols of interest~~
       - Cull cols down to useful/populated data
       - DateTime - still need to decide on time horizon - probably best to figure out filtering first
       
   
####Filter Data Then Store Input
- Filter data before storage
       - UnitType = M
       - Has driver
       - Has useful event data
       - Maybe counts & other summary data of points that are not of interest to be able to say that there were x miles or updates where all was well...
       - Sumarize by trip?
       - Subset of entire fleet?
- Put it in a RDBMS (maybe a cloud database for scale - there is going to be a lot of data!)
####Analysis/Where the hell to begin....
- Descriptive stats on what is there
- OLS on subset of independent vars to id those w/ most impact
- Would like to look at Baysean probability to generate a signal vs one-time correlation
- Clustering sounds like it might be handy to id groups of dirvers that fit certain profiles (aggressive, moderate, passive) compare those to airbag events
- Will likely have the Tall/Skinny problem so perhaps think about employing the Eigenvalues and Eigenvectors techniques Paco touched on

----------


  [1]: https://crewchief.telogis.com/
  [2]: https://api-preview.telogis.com/documentation/