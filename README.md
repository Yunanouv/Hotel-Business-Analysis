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
<br>
<img width="550" alt="rsvhotel" src="https://github.com/Yunanouv/Hotel-Business-Analysis/assets/146415555/cd2f22bd-08a1-4a98-8699-83cc23fcb2e2">
<br>
In this section, we’ll try to see the hotel booking trend based on hotel type, they are City Hotel and Resort Hotel.  
The dataset tells us three types of reservation status after they make a reservation based on arrival date. The status is:  
  - Check Out 	
  - Canceled 	
  - No Show 		

From the graph, we can see that the City Hotel has more reservations including more check-outs, more canceled, and more no-shows than the Resort Hotel. The canceled reservations in city hotels are almost half of the total checkout so need to be analyzed further to avoid this in the future. 






  

 

