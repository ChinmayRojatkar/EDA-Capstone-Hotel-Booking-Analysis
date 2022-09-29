![image](https://user-images.githubusercontent.com/113965073/192941715-d19cb3f0-df98-4e7a-b843-a247e08c0d56.png)

                                                
                                                ## EDA-ON-Hotel-Booking-Analysis-
![lens-flare-png-46225](https://user-images.githubusercontent.com/113965073/192941347-47c6c6e1-c142-4c62-8ba2-a4a059734dfa.png)


## Objective

We are provided with a hotel bookings dataset. 

Out main objective is perform EDA on the given dataset and draw useful conclusions about general trends in hotel bookings and how factors governing hotel bookings interact with each other.

## Dataset
We are given a hotel bookings dataset. This dataset contains booking information for a city hotel and a resort hotel. It contains the following features.

```
- hotel: Name of hotel ( City or Resort)
- is_canceled: Whether the booking is canceled or not (0 for no canceled and 1 for canceled)
- lead_time: time (in days) between booking transaction and actual arrival.
- arrival_date_year: Year of arrival
- arrival_date_month: month of arrival
- arrival_date_week_number: week number of arrival date.
- arrival_date_day_of_month: Day of month of arrival date
- stays_in_weekend_nights: No. of weekend nights spent in a hotel
- stays_in_week_nights: No. of weeknights spent in a hotel
- adults: No. of adults in single booking record.
- children: No. of children in single booking record.
- babies: No. of babies in single booking record. 
- meal: Type of meal chosen 
- country: Country of origin of customers (as mentioned by them)
- market_segment: What segment via booking was made and for what purpose.
- distribution_channel: Via which medium booking was made.
- is_repeated_guest: Whether the customer has made any booking before(0 for No and 1 for 
                     Yes)
- previous_cancellations: No. of previous canceled bookings.
- previous_bookings_not_canceled: No. of previous non-canceled bookings.
- reserved_room_type: Room type reserved by a customer.
- assigned_room_type: Room type assigned to the customer.
- booking_changes: No. of booking changes done by customers
- deposit_type: Type of deposit at the time of making a booking (No deposit/ Refundable/ No refund)
- agent: Id of agent for booking
- company: Id of the company making a booking
- days_in_waiting_list: No. of days on waiting list.
- customer_type: Type of customer(Transient, Group, etc.)
- adr: Average Daily rate.
- required_car_parking_spaces: No. of car parking asked in booking
- total_of_special_requests: total no. of special request.
- reservation_status: Whether a customer has checked out or canceled,or not showed 
- reservation_status_date: Date of making reservation status.
```

- Total number of rows in data: 119390
- Total number of columns: 32
## Data Cleaning and Feature Engineering

### (1) Removing Duplicate rows
All duplicate rows were dropped.

### (2) Handling null values
- Null values in columns `company` and `agent` were replaced by 0.
- Null values in column `country` were replaced by 'others'.
- Null values in column `children` were replaced by the mean of the column.
  

### (3) Converting columns to appropriate data types

- Changed data type of `children`, `company`, `agent` to int type.
- Changed data type of `reservation_status_date` to date type.

### (4) Removing outliers

- One outlier was found in the `adr` column. Simply dropped it.

### (5) Creating new columns
- Created new column `total_stay` by adding `stays_in_weekend_nights`+`stays_in_week_nights`.
- Created new column `total_people` by adding `adults`+`children`+`babies`.

## Exploratory Data Analysis

Performed EDA and tried answering the following questions:

```
  • While doing Bivariate analysis of the given hotel booking dataset, we
    tried to figured answering the following questions:
      1. Which room type is in the demand?
      2. Which room type generated highest Revenue?
      3. In Which Year the Highest Number of Rooms booked by the each
      type of the Hotel?
      4. Maximum Number of the Rooms booked by ?
      5. In which Month the Highest Number of Customers came ?
      
  • While doing the Hotel Wise Analysis of the given hotel booking
    dataset, we tried to figured answering the following questions:
      1. Percentage of the bookings in each hotels?
      2. Which hotel makes more revenue?
      3. Which hotel has higher booking cancellations rates?
      4. What is most preferred stay length in each hotel?
      5. What is the preferred stay time by the Customers?

 • While doing this set of the analysis of provided hotel booking dataset,
   the Team Tried to find the answer of the following questions:
      1. What is the most common channel for making the booking of the
      hotels?
      2. Which distribution channel generates more revenue deals for the
      hotels?
      3. Which channel does have more repeated Customers?

• While doing the Cancelation Analysis The team figured to do the
  analysis and tried to answer the following:
      1. Which distribution channel has highest the cancellation
      percentage?
      2. Reasons behind the Cancelation Occurs?
      3. Which channels is affecting the most revenue of the Hotels?

• While doing the Time Wise Analysis The team figured to do the analysis
  and tried to answer the following:
      1. Which Months are the most busiest months for the hotels?
      2. In which year the Highest Number of Bookings were Done?
      3. What are the busiest days of the months in staying the Hotels?
      4. Trends of booking Changes and Months of Arrivals?

```

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:
  -  Bar Plot.
  -  Histogram.
   - Scatter Plot.
   - Pie Chart.
   - Line Plot.
   - Heatmap.
- Box Plot
             
###  Univariate Analysis:

Performed univariate analysis and made following conclusions:
```
 1.) Agent no. 9 has made most no. of bookings.
 2.) Most demanded room type is A, but better adr generating rooms H, G and C. Hotels should increase the no. of room types A and H to maximise revenue.
 3.) Most popular meal type is BB(Bed and Breakfast).
 4.) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel.
 5.) Guests use different channels for making bookings out of which most preferred way is TA/TO.
 6.) July- August are the most busier and profitable months for both of hotels. 
 7.) Most of the guests came from european countries, with highest number of guests from Portugal.
 8.) Most common stay length is less than 4 days and generally people prefer City hotel for short stay, but for long stays, Resort Hotel is preferred.
 

## Conclusion

```
(1) Around 60% bookings are for City hotel and 40% bookings are for Resort hotel, therefore City Hotel is busier than Resort hotel. Also the overall adr of City hotel is slightly higher than Resort hotel.
(2) Mostly guests stay for less than 5 days in hotel and for longer stays Resort hotel is preferred.
(3) Both hotels have significantly higher booking cancellation rates and very few guests less than 3 % return for another booking in City hotel. 5% guests return for stay in Resort hotel.
(4) Most of the guests came from european countries, with most of guests coming from Portugal.
(5) Guests use different channels for making bookings out of which most preferred way is TA/TO.
(6) For hotels higher adr deals come via GDS channel, so hotels should increase their popularity on this channel.
(7) Almost 30% of bookings via TA/TO are cancelled.
(8) Not getting same room as reserved, longer lead time and waiting time do not affect cancellation of bookings. Although different room allotment do lowers the adr.
(9) July- August are the most busier and profitable months for both of hotels. 
(10) Within a month, adr gradually increases as month ends, with small sudden rise on weekends.
(11) Couples are the most common guests for hotels, hence hotels can plan services according to couples needs to increase revenue.
(12) More number of people in guests results in more number of special requests.
(13) Bookings made via complementary market segment and adults have on average high no. of special request.
(14) For customers, generally the longer stays (more than 15 days) can result in better deals in terms of low adr.

And many more conclusions.
```
## Challenges
```
(1) There was a lot of duplicate data.
(2) Data was present in wrong datatype format.
(3) Choosing appropriate visualization techniques to use was difficult.
(4) A lot of null values were there in the dataset.


