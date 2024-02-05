1. Count the total number of records
```SQL
SELECT* 
FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`;
```

<img width="465" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/fb375e5a-a54c-4fc5-8955-136ac6dd88f3">

2. Find the average trip fare
   ```SQL
   SELECT AVG(fare) AS average_fare
   FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`;
   ```

<img width="455" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/e101013f-be64-4f75-b768-d4007f5599dd">

3. Count the number of trips by payment type
   ```SQL
   SELECT payment_type, COUNT(*) AS trip_count
   FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
   GROUP BY payment_type;
   ```

<img width="202" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/7e5af93d-27ed-4a3b-838e-fded5be07463">

5. Find the maximum trip duration
   ```SQL
   SELECT MAX(trip_seconds) AS max_trip_duration
   FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`;
   ```

 <img width="467" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/bf9595e5-12f5-400c-b47a-290114331fd1">

5. Count the number of trips for each day of the week
   ```SQL
   SELECT EXTRACT(DAYOFWEEK FROM trip_start_timestamp) AS day_of_week, COUNT(*) AS trip_count
   FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
   GROUP BY day_of_week
   ORDER BY day_of_week;
   ```

<img width="272" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/3e0cb34a-a1b7-4788-b834-c58ffd162049">

 6. Find the most common payment type
    ```SQL
    SELECT payment_type, COUNT(*) AS payment_count
    FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
    GROUP BY payment_type
    ORDER BY payment_count DESC
    LIMIT 1;
    ```

  <img width="471" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/f85d0ce1-c5e4-4850-ab1a-09dbac565826">

7.  Count the number of trips by taxi company
    ```SQL
    SELECT company, COUNT(*) AS trip_count
    FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
    GROUP BY company
    ORDER BY trip_count DESC
    LIMIT 10;
    ```

<img width="187" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/0d987aed-e610-46c7-be5c-8f552179df63">

8. Calculate the total revenue for each taxi company
   ```SQL
   SELECT company, SUM(fare) AS total_revenue
   FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
   GROUP BY company
   ORDER BY total_revenue DESC
   LIMIT 10;
   ```
<img width="193" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/b1b7a9c0-f24d-4f18-91c7-44c4476a87b7">

9.  Calculate the average trip distance for each day of the week
    ```SQL
    SELECT EXTRACT(DAYOFWEEK FROM trip_start_timestamp) AS day_of_week, AVG(trip_miles) AS avg_trip_distance
    FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
    GROUP BY day_of_week
    ORDER BY day_of_week;
    ```

<img width="218" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/0dcae59b-661f-4630-86f9-d47c2b3d31af">

10.  Get the top 5 pickup locations with the highest average fare
     ```SQL
     SELECT pickup_community_area, AVG(fare) as avg_fare
     FROM `bigquery-public-data.chicago_taxi_trips.taxi_trips`
     GROUP BY pickup_community_area
     ORDER BY avg_fare DESC
     LIMIT 5;
     ```
     
 <img width="269" alt="image" src="https://github.com/MEGH0401/megh/assets/159043052/bd78b06a-2c0a-4c33-af5b-74f173727eee">












