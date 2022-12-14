# NYC-Crime-Visualization
## Introduction  
My project dedicates to doing research on the criminal. I would like to visualize the happen of the criminal in New York City.
I thought the readers will be interested in this topic because this project could provide criminal information. The information could show the happening location of the criminal which includes the area or even the longitude and latitude. People could visualize a location that has a lot of crimes and avoid getting to this place. A mapping company such as Google could also add a function to navigate the user to their location without passing by this dangerous place.
According to the dataset I found, the dataset includes information with the time, date, location, crime types, etc.
In my project, I implemented the dashboard, therefore, the user can select the specific information, they are more likely to see.  
## Information I target
The phenomenon I am going to focus on includes the time, the date, the criminal types, the region, Latitude, and Longitude. Most of the data are used for filtering the information. The time will be represented by Eastern Standard time with a format such as 10:51:00 PM. The date will be represented as 09/30/2016. The region includes Bronx, Brooklyn, Manhattan, Queens, and Staten Island. The Latitude and Longitude can help us to pinpoint the crime happened location. With the information I collected and mentioned above, we could build a crime map to let the user sees the crime happened location and filter the information to get the data they are more concerned about. After collecting the data, I decided to include the information with the Google Map API, to implement a real crime map.
I decided to implement this project with Jupyter Notebook and Google Map API. Google Map API could be used to register a GCP account. Once we finished the preparation of this project, we could start to implement the application by Python3. I will create several buttons, when we click each button, then it may show the result I have already filtered.
But the data I collected have a great amount, therefore, I do not think it is a good way to pin all data on the map. This may lead the map looks messy, and this may also take a huge amount of time to pin all information. Therefore, in some cases, I think I could use some clustering skills, such as K-clustering to reduce the data. Even if we reduce the data, I thought the clustering skill could help us to keep the useful information and remove trivial data and biases that are not needed.  

# Dataset  
From the website NYC OpenData: https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Current-Year-To-Date-/5uac-w243, we could get the data on the crime in New York City. The data collected from 2021 until now and collected by NYPD. This dataset includes more than 360000 crimes and 24 different kinds of data on each crime. This dataset is keep updating. The website created by the New York Government (https://maps.nyc.gov/crime/) shows the result I am going to implement. But we cannot get the UI of this map, which means that we cannot use this map to make further development. The website I just mentioned is not open source, if we decided to add more features or different kinds of filters, it is impossible to do that.
From the same website with this link (https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i), we can find the whole historic data, the data collected from 2016 until now, which includes more than 7.83 million crimes and 35 types.  
## Information visualization techniques  
In this project, I would like to show crimes with different kinds of visualization techniques. I consider showing the crime types with a histogram. The x-axis will be the name of the crime, and the y-axis will be the amount of each crime. In each crime, I also consider showing the crime amount and time with a line chart. The x-axis will be the time, and the y-axis will be the amount of the specific crime during the specific time sections. By the line chart, it is easier to compare the information between different time sections. The line chart also can show the specific crime amount during different years. By this way, we could know if the safety of the specific region is getting better.
And if I have enough time, I hope to combine the crime data with Google map API. I hope to drop the pin on the map which will let the user much convenient to know the safe place. We have more than 3000000 data, therefore, before I drop the pin, I thought doing the clustering will be good and avoid the messy data.
I applied ipywidgets to build the dashboard. The dashboard can let the user select the specific information they are going to see more conveniently. I applied seaborn to draw the histogram and line-chart. I incorporated the gmplot to draw the pin on the map. With the dashboard, histogram, line-chart, and map, we can show the visualization result clearly.  
## Visualization Result

I designed a dashboard that could let the user select and see the specific city and the data they would like to see. At this section, we generate the histogram and line chart, and the dataset we used is the historical dataset which contains all the historical data and has more than 7 million crimes. Option city can let the user select a specific city; the default is to present all cities. Option col can let the user select the data type they are going to look at. CMPLNT_FR_DT is the year, CMPLNT_FR_TM is the time slot, and OFNS_DESC is the attack type. Every time when the user selects a new option, the project will automatically refresh to generate a new histogram and line chart.  
![1](https://user-images.githubusercontent.com/50438750/207516364-0e74e6df-e231-4d56-a505-2ebf01d59972.jpg)  
The below images show the number of crimes each year in all New York Cities  

![2](https://user-images.githubusercontent.com/50438750/207516506-63e958d9-9d60-46a6-8aa7-d00b4ec92b40.jpg)

The below images show the number of crimes in each attack mode in Brooklyn  


![3](https://user-images.githubusercontent.com/50438750/207516646-87b6a0f0-7ace-432a-8ccf-40b6e6d8fabb.jpg)  
Now. I am going to drop the pin on Google map. I incorporated the Google map API from the GCP. And because the data is too big, I ran the K-clustering algorithm first. The data I used more focus on recent, which is the one only contains 2021 and 2022, and I select the most recent month to show the result.
In this section, I also built an interactive dashboard to let the user able to select the information they would like to city. The pin is the pin type we are going to show on the map. The clusters num slider can let us adjust the value of K-clustering. City can let us focus the region we are going to look at.  

![4](https://user-images.githubusercontent.com/50438750/207516714-5d54d277-24e7-4aea-a7df-1015163b1c3e.jpg)  
The below image shows the result othe f city: ALL / pin: HEAT / clusters num: 30  

![5](https://user-images.githubusercontent.com/50438750/207516854-9035e72c-de76-41d6-8579-30b0a94be6eb.jpg)  
The below image show the result of city: Brooklyn / pin: SCATTER / clusters num: 50  
![6](https://user-images.githubusercontent.com/50438750/207516961-496da2a0-db6e-403a-918c-c0274e4cbc7f.jpg)

