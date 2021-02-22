
# NYC Yellow Cab Efficiency 
---
> Independent project to explore the impact of shared rides on the efficiency of NYC transit by using trip aggregation strategies on NYC Yellow Cab trip data. I provide an estimate of gained efficiency if we switch from traditional yellow cab rides to aggressive ride sharing strategies. My approach starts by defining an efficiency metric and an aggregation strategy and then I compare the distribution of efficiency of yellow cabs and ride shares across a range of spatial and temporal gradients within Manhattan.

## Highlights
1. Custom-designed (very) comprehensive efficiency measurement for means of transportation that takes into account passenger displacement, driver salary, passenger opportunity-cost, fuel cost (in movement and idle) and carbon emissions.
2. Even without taking extra passengers midway or account for an improved traffic, 6 passenger mini-vans with an aggressive share ride strategy vastly outperforms NYC yellow cabs using the provided efficiency metric.
3. Depending on routes, bikes are still more efficient than shared-rides and yellow cabs barely beat walkers at 3.6 km/hr.
4. Differences between yellow cabs and shared rides are consistent across all times and all days of the week.


NYC traffic data available at their website or within Google BigQuery (notebook contains code for reading from bigquery)

## Contents:
1. Shapefiles with NYC borough boundaries and borough names.
2. Jupyter notebook with the entire EDA pipeline (also available as an html file with preprocessed outputs).
3. Plots summarizing comparison between yellow cab rides and aggregated rides.
4. Conda environment with all required packaged to reproduce the analysis.

---
## Instructions to reproduce :
1. install conda environment

``
conda env create -y yellowcab.yml   
``

2. open the notebook

``
jupyter notebook   
``

3. select the correct kernel 
   
4. swap in your google bigquery project string id 
   
5. run all cells!

*Feel free to change the date range but beware the volume of data, I am using two weeks here and am already on the gigabyte zone.*

*Depending on how good your CPU is, this can take quite a while, I an '.html' file with preprocessed outputs in the repo for convenience.*

---
## Efficiency formula

![\textbf{Efficiency} = \frac{\textit{Passenger Displacement}}{\textit{cost}}
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ctextbf%7BEfficiency%7D+%3D+%5Cfrac%7B%5Ctextit%7BPassenger+Displacement%7D%7D%7B%5Ctextit%7Bcost%7D%7D%0A)

![\textbf{Passenger Displacement} = \mu_{\textit{distance Covered}} * \mu_{\textit{number Of Passengers}}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ctextbf%7BPassenger+Displacement%7D+%3D+%5Cmu_%7B%5Ctextit%7Bdistance+Covered%7D%7D+%2A+%5Cmu_%7B%5Ctextit%7Bnumber+Of+Passengers%7D%7D)

![\textbf{Cost} = \textit{(fuel Cost + social Carbon Cost) * miles + idle Time} + \textit{(driver Salary + oppotunity Cost) time} 
](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+%5Ctextbf%7BCost%7D+%3D+%5Ctextit%7B%28fuel+Cost+%2B+social+Carbon+Cost%29+%2A+miles+%2B+idle+Time%7D+%2B+%5Ctextit%7B%28driver+Salary+%2B+oppotunity+Cost%29+time%7D+%0A)

*for further details about the formula and my assumptions, see the notebook.*

## Traffic maps preview

### Yellow cabs
![alt text](images/cab_map.png)

### Shared rides
![alt text](images/share_map.png)

*Red lines are comparable to walkers when it comes to efficiency and green lines are comparable to bicycles.*

*Interactive versions of these maps are available in the notebook and its html version.*

## Efficiency through time
![alt text](images/efficiency_plot.png)

