# Design a ride-sharing like Uber

## Problem statement

Design a ride-sharing service like Uber where users can request a ride, and drivers can accept those requests. 
The system should handle real-time location updates and allow users to see the estimated time of arrival (ETA) of their driver.

## Solutions

### Scoping

#### Functional requirements

Dealing with ride-sharing problem, I can think about 2 applications, one for customer and one for driver. I would not expect the customer use web app to book a drive, because it less mobiality than mobile app, hence I will mainly focus on mobile applications on both of sides.

##### Customer app:
- Authentication
    - Register
    - Login
- Booking flow
    - Choose the pickup / arrived location
    - Choose type of vehicle: silver, gold, platium
    - See the estimated prices & estimated arrived time
- Real-time location updates
    - After booking, the trip is marked as in progress and customer can see updated location from driver.
- Support center
- Payment

##### Driver app:
- Authentication
    - Register will be done via backoffice user
    - Login
- Real-time notify when any booking from customer
- Chat / calling system to contact with customer
- Analytics
    - Time range: today, yesterday, a week, a month
    - How many trips?
    - Revenue, Profit?
    - Bonus?
- Support center

Let assume we focus on ride-booking and matching process.

#### Non-functional requirements

##### Scalability

1. Throughput
- How many active user per day?
- I'm asumming every active user will avarage have 2 trips per day.
- How many driver we have to leverage with these users, I'm assuming around 20% of DAU?
- In peak hour, how many requests will we have?

2. Storage
- Let say we have 2m trips per day, every trip will store some information about: user_id (int), driver_id (int), pickup_location_latitude (float), arrive_location_latitude (float), estimated price (float), promotion (string), trip_status.
- We need to store 2m records per day, and every record will take 100 bytes

```
100 bytes / records x 2.000.000 = 200mb / day
200mb * 30 days = 6000 mb / months = 6 Gb / months
```

##### Performance
- Latency
- Availability

##### Security
