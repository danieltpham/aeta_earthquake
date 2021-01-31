`eqlst.csv` contains an earthquake list from Oct 1st, 2016 to Nov 30th, 2020.

 **Criteria**

1.  In target region (22°N -34°N, 98°E -107°E)
2. Magnitude  ≥3.5 
3.  There is at least one AETA station within 100km 

**Columns**

|   Column    |                         Description                          |
| :---------: | :----------------------------------------------------------: |
| `Longitude` |                 East Longitude of epicenter                  |
| `Latitude`  |                 North Latitude of epicenter                  |
| `Magnitude` |                          Magnitude                           |
|   `Time`    |                  Time of earthquake (UTC+8)                  |
| `Timestamp` |             Time of earthquake (Unix Timestamp)              |
|   `Week`    | Earthquake occurs on which week (Week 1 is Oct 3rd, 2016 to Oct 9th, 2016 and so on) |
| `Location`  |               Administrative name of epicenter               |
