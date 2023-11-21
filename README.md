# Hotel Business Analysis  

<div align="center">
<img src="https://img.freepik.com/free-photo/type-entertainment-complex-popular-resort-with-pools-water-parks-turkey-with-more-than-5-million-visitors-year-amara-dolce-vita-luxury-hotel-resort-tekirova-kemer_146671-18728.jpg?w=1060&t=st=1700551436~exp=1700552036~hmac=260eb3c8cbc29d5bc0072947167bba19c710d696f4dfb6d2094902163acfceb5" alt="hotelbusiness" style="width:800px;height:500px;" align="center">
</div> 

<br>
It is very important for a company to always analyze its business performance. On this occasion, we will delve deeper into business in the hospitality sector. Our focus is to find out how our customers behave in making hotel reservations, and its relationship to the rate of cancellation of hotel reservations. We will present the results of the insights we find in the form of data visualization to make it easier to understand and more persuasive.
<br> 

This project will analyze hotels based on customer behavior using data visualization.  
<br>

## Points to Analyze

- Monthly Booking Analysis Based on Hotel Type  
- Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates
- Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates
<br>

# Data Overview  

| Feature Name | Description |
| --- | --- |
|**hotel** | Type of hotel |
|**is_canceled** | Value indicating if the booking was canceled (1) or not (0)|  
|**lead_time** | Number of days that elapsed between the entering date of the booking into the PMS and the arrival date|
|**arrival_date_year** | Year of arrival date|
|**arrival_date_month** | Month of arrival date with 12 categories: “January” to “December” |
|**arrival_date_week_number**| Week number of the arrival date |
|**arrival_date_day_of_month** | Day of the month of the arrival date  |
|**stays_in_weekend_nights** | Number of weekend nights (Saturday or Sunday) the guest stayed or booked to stay at the hotel  |
|**stays_in_weekdays_nights** | Number of weeknights (Monday to Friday) the guest stayed or booked to stay at the hotel BO and BL/Calculated by counting the number of weeknights |
|**adults** | Number of adults  |
|**children** | Number of children |
|**babies** | Number of babies |  
|**meal** | Meal menu |
|**city** | City of origin  |
|**market_segment** | Market segment designation. In categories, the term “TA” means “Travel Agents” and “TO” means “Tour Operators”  |
|**distribution_channel** | Booking distribution channel. The term “TA” means “Travel Agents” and “TO” means “Tour Operators”  |
|**is_repeated_guest** | Value indicating if the booking name was from a repeated guest (1) or not (0) |  
|**previous_cancellations** | Number of previous bookings that were canceled by the customer prior to the current booking |
|**previous_bookings_not_canceled** | Number of previous bookings not canceled by the customer prior to the current booking |  
|**booking_changes** | Number of changes/amendments made to the booking from the moment the booking was entered on the PMS until the moment of check-in or cancellation |
|**deposit_type** |  Type of deposit |
|**agent** | ID of the travel agency that made the booking  |
|**company** | ID of the company/entity that made the booking or is responsible for paying the booking. ID is presented instead of designation for anonymity reasons  |
|**days_in_waiting_list** | Number of days the booking was in the waiting list before it was confirmed to the customer  |
|**customer_type** | TYpe of customer |
|**adr** | Average Daily Rate (Calculated by dividing the sum of all lodging transactions by the total number of staying nights) |  
|**required_car_parking_spaces** | Number of car parking spaces required by the customer |
|**total_of_special_requests** | Number of special requests made by the customer (e.g. twin bed or high floor) |
|**reservation_status** |  Status of reservation |


1. This hotel business has a large amount of customers,119,930 records with 29 features. But still, this dataset is raw and needs to be cleaned first before analysis.
2. This dataset uses 2 types of hotels, they are City Hotel and Resort Hotel.
3. There are 4 columns containing null values, the `children`, `city`, `agent`, and `company` features  
4. After exploring, the null and abnormal values will be analyzed more deeply to ensure our assumptions. We also need to check the unique value for categorical columns and other analysis
5. In this case, `company` contains 94% null values, which means this column doesn’t give us important thing to know and lack of information. Delete this column is the best way. Furthermore, the duplicated rows and `city` have been deleted as well
6. The missing and abnormal values will be replaced by appropriate values.
<br>

# Data Analysis  
## 1. Monthly Booking Analysis Based on Hotel Type  
**a.** <br>
<img width="750" alt="rsvhotel" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/cd2f22bd-08a1-4a98-8699-83cc23fcb2e2">
<br>
In this section, we’ll try to see the hotel booking trend based on hotel type, they are City Hotel and Resort Hotel.  
The dataset tells us three types of reservation status after they make a reservation based on arrival date. The status is:  

  - Check Out 	
  - Canceled 	
  - No Show 		

From the graph above, we can see that the City Hotel has more reservations including more check-outs, more canceled, and more no-shows than the Resort Hotel. The canceled reservations in city hotels are almost half of the total checkout so need to be analyzed further to avoid this in the future. 
<br> 

**b.** <br>
<img width="750" alt="monthlybooking" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/7f637dca-6077-4649-846c-38d5ea8f26d9">
<br>  
The graph shows the hotel booking trend from City Hotel and Resort Hotel for three years. Reservations seem to fluctuate but are increasing over time. The number of bookings from City Hotel began to exceed Resort Hotel in November 2017 and got more reservations over three years. We also can see the peak season around June to October but it is not the holiday season, and the majority of customers are not families. Therefore, it is likely that many customers are traveling for business purposes or reasons other than vacation.  
<br>  

## 2. Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates  
<br>
**a.** <br>
<img width="750" alt="grup-stayduration" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/7744167a-ef34-4687-b129-4c1a40a1d38a">
<br> 

The next analysis is to see the cancellation rates based on the stay duration of customers. 
The stay duration starts from 1 to the longest 69 days. From the statistical data, the most stay duration has happened is around one to seven days (a week). The difference in stay duration seems very large, so it needs to be kept simpler by grouping the durations, they are :  
  - Group 1 : 1-7 days
  - Group 2 : 8-14 days
  - Group 3 : 15-21 days
  - Group 4 : 22-30 days
  - Group 5 : More than 1 month

As we can see, the frequencies are too unequal, only group 1 is dominant.  
<br>

**b.** <br>
<img width="750" alt="grup-stayduration-cancelrates" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/ec98ed95-5748-4c64-afc5-de37fa9cc256">
<br> 
From the trends, some observations are : 
The least canceled bookings were on around 1-7 days. The good thing is that this is the group with the most frequent stays but the cancellation rate is also the smallest.
Customers who stayed around 8-14 days have the highest cancellation rates. 
The cancellation rate for customers who stayed more than a month is also high, need to be aware of junk leads.  
<br>  


## 3. Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates 
<br>

**a.** <br>
<img width="750" alt="grup-leadtime" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/7cecfa68-505e-4e32-93dc-39ec53919a83">
<br> 
As we can see from the analysis, the lead time range is way too large from 1 day to 2 years. Well, the 2 year lead-time seems quite nonsense and the customer counts are also few so we can group them as one group. Now, for a lead time of under a year, the most frequent is around 1 week which reaches thousands of customers.  
So, we can group the lead time based on frequency and duration of lead time as follows :  
  a. 1-week (1-8 days)  
  b. 2-3 weeks (9-20 days)  
  c. 1-month (21-31 days)  
  d. 2 months  
  e. 3-4 months  
  f. 5-6 months  
  g. 7-9 months  
  h. 1 year (10-12 months)  
  i. >1 year
<br>

**b.** <br>
<img width="750" alt="grup-leadtime" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/2f5128ff-782b-482d-a5b1-5339ea582c74">
<br>  
No matter what type of hotel, the lead time really has a big impact on the cancellation rate.  
For Resort Hotel, the cancellation rate seems quite stable around the thirties to seventies.  
For City Hotel, the highest cancellation rate comes from 2 months of lead time (reaches 88.76%) and the lowest is a month (11.24%). It indicates that 1 month is an optimal lead time for city hotels.
<br>  

# Business Recommedantion  


  

 

