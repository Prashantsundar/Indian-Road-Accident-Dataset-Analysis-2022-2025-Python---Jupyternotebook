# 🚦 Turning Data into Road Safety Insights Across India
Leveraged a large-scale data set analyzing traffic accidents in India to identify high-risk periods and environmental factors. My analysis focused heavily on pinpointing the specific "peak death hour" and the associated meteorological conditions that contribute to severe accidents

Overview
This repository contains a comprehensive exploratory data analysis (EDA) of a detailed Indian traffic accident dataset, with a sharp focus on the Chennai metropolitan area. The goal of this analysis is to pinpoint the exact time, day, and environmental conditions that present the highest risk of severe accidents.

We identify and quantify the specific convergence of factors—Friday evenings during rush hour, compounded by low visibility—that creates what this project identifies as the "Ticket to HELL" Period.


accident_id	city	state	latitude	longitude	date	time	hour	day_of_week	is_weekend	...	visibility	temperature	traffic_density	cause	accident_severity	vehicles_involved	casualties	is_peak_hour	festival	risk_score
19995	19995	Bangalore	Karnataka	13.092276	77.599571	2022-09-29	3:00	3	Thursday	0	...	high	31	low	distraction	minor	3	2	0	NaN	0.10
19996	19996	Chennai	Tamil Nadu	13.172928	80.157062	2023-11-25	1:00	1	Saturday	1	...	high	20	low	distraction	major	4	2	0	NaN	0.10
19997	19997	Chennai	Tamil Nadu	12.997170	80.150724	2022-06-18	15:00	15	Saturday	1	...	high	22	low	weather	minor	3	3	0	NaN	0.10
19998	19998	Kolkata	West Bengal	22.454882	88.322213	2023-03-12	4:00	4	Sunday	1	...	high	33	low	poor road	minor	1	0	0	NaN	0.10
19999	19999	Delhi	Delhi	28.510266	77.065301	2024-07-05	23:00	23	Friday	0	...	low	39	high	overspeeding	minor	4	2	0	NaN	0.65
5 rows × 24 columns

accident_id              0
city                     0
state                    0
latitude                 0
longitude                0
date                     0
time                     0
hour                     0
day_of_week              0
is_weekend               0
road_type                0
lanes                    0
traffic_signal           0
weather                  0
visibility               0
temperature              0
traffic_density          0
cause                    0
accident_severity        0
vehicles_involved        0
casualties               0
is_peak_hour             0
festival             19885
risk_score               0
dtype: int64
<class 'pandas.DataFrame'>
RangeIndex: 20000 entries, 0 to 19999
Data columns (total 24 columns):
 #   Column             Non-Null Count  Dtype  
---  ------             --------------  -----  
 0   accident_id        20000 non-null  int64  
 1   city               20000 non-null  str    
 2   state              20000 non-null  str    
 3   latitude           20000 non-null  float64
 4   longitude          20000 non-null  float64
 5   date               20000 non-null  str    
 6   time               20000 non-null  str    
 7   hour               20000 non-null  int64  
 8   day_of_week        20000 non-null  str    
 9   is_weekend         20000 non-null  int64  
 10  road_type          20000 non-null  str    
 11  lanes              20000 non-null  int64  
 12  traffic_signal     20000 non-null  int64  
 13  weather            20000 non-null  str    
 14  visibility         20000 non-null  str    
 15  temperature        20000 non-null  int64  
 16  traffic_density    20000 non-null  str    
 17  cause              20000 non-null  str    
 18  accident_severity  20000 non-null  str    
 19  vehicles_involved  20000 non-null  int64  
...
 22  festival           115 non-null    str    
 23  risk_score         20000 non-null  float64
dtypes: float64(3), int64(9), str(12)
memory usage: 3.7 MB
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
accident_id	latitude	longitude	hour	is_weekend	lanes	traffic_signal	temperature	vehicles_involved	casualties	is_peak_hour	risk_score
count	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000	20000.000000
mean	9999.500000	20.389207	78.173330	11.487200	0.286150	3.493950	0.499850	27.579600	2.992000	1.726450	0.247400	0.437585
std	5773.647028	6.165791	4.485967	6.945563	0.451972	1.705406	0.500012	7.454746	1.415534	1.489104	0.431512	0.218130
min	0.000000	12.800172	72.700017	0.000000	0.000000	1.000000	0.000000	15.000000	1.000000	0.000000	0.000000	0.100000
25%	4999.750000	13.198653	73.997979	5.000000	0.000000	2.000000	0.000000	21.000000	2.000000	1.000000	0.000000	0.250000
50%	9999.500000	18.812008	77.297000	12.000000	0.000000	4.000000	0.000000	28.000000	3.000000	1.000000	0.000000	0.450000
75%	14999.250000	28.402467	80.111089	18.000000	1.000000	5.000000	1.000000	34.000000	4.000000	3.000000	0.000000	0.600000
max	19999.000000	30.799960	88.499861	23.000000	1.000000	6.000000	1.000000	40.000000	5.000000	5.000000	1.000000	1.000000
accident_id	city	state	latitude	longitude	date	time	hour	day_of_week	is_weekend	...	visibility	temperature	traffic_density	cause	accident_severity	vehicles_involved	casualties	is_peak_hour	festival	risk_score
6550	6550	Kolkata	West Bengal	22.625977	88.223833	2022-04-07	5:00	5	Thursday	0	...	low	32	low	overspeeding	minor	1	1	0	NaN	0.45
1 rows × 24 columns

<StringArray>
[      'Pune',     'Mumbai', 'Chandigarh',    'Chennai',      'Delhi',
  'Bangalore',  'Hyderabad',    'Kolkata']
Length: 8, dtype: str
=======================================================
  ACCIDENTS BY TEMPERATURE — INDIA
=======================================================

🌡️  Temperature stats (°C):
 count    20000.000000
mean        27.579600
std          7.454746
min         15.000000
25%         21.000000
50%         28.000000
75%         34.000000
max         40.000000
📊 Chart saved → india_accidents_by_temperature.png
=======================================================
  ACCIDENTS BY VISIBILITY — INDIA
=======================================================

👁️  Accidents by Visibility level:
visibility
low       9987
high      6690
medium    3323

⛅ Accidents by Weather:
weather
clear    6690
rain     6677
fog      6633
📊 Chart saved → india_accidents_by_visibility.png
✅ Chennai rows: 2,575
=======================================================
  CHENNAI — TOTAL ACCIDENTS OVERVIEW
=======================================================

📍 Total Accidents in Chennai : 2,575
   Fatal   : 371
   Major   : 794
   Minor   : 1410
📊 Chart saved → chennai_accident_severity.png
=======================================================
  CHENNAI — TIME OF ACCIDENT
=======================================================

⏰ Accidents per Hour (Chennai):
hour
0     112
1     112
2     126
3      96
4     103
5     104
6     116
7     113
8      98
9     102
10    100
11    111
12    106
13    116
14    103
15    103
16     93
17    121
18    108
...
Sunday       351
Thursday     374
Tuesday      372
Wednesday    319
Output is truncated. View as a scrollable element or open in a text editor. Adjust cell output settings...
📊 Chart saved → chennai_accidents_by_time.png
=======================================================
  CHENNAI — WEATHER CONDITIONS
=======================================================

⛅ Accidents by Weather (Chennai):
weather
clear    874
fog      859
rain     842

Weather × Severity Cross-Tab:
accident_severity  fatal  major  minor
weather                               
clear                129    261    484
fog                  124    266    469
rain                 118    267    457
📊 Chart saved → chennai_accidents_by_weather.png
=======================================================
  CHENNAI — COMPLETE SUMMARY
=======================================================
  Total Accidents                    : 2575
  Peak Accident Hour                 : 19:00
  Busiest Day                        : Friday
  Most Common Weather                : clear
  Highest Risk Visibility            : low
  Fatal Accidents                    : 371
  Major Accidents                    : 794
  Minor Accidents                    : 1410
  Avg Temperature (°C)               : 27.6
  Peak Hour Accidents                : 658
  Weekend Accidents                  : 737

📋 Hour × Weather × Visibility Breakdown (Chennai):
 hour weather visibility  accident_count
   19   clear       high              53
   20   clear       high              52
    6   clear       high              49
   11   clear       high              48
    7     fog        low              47
    0     fog        low              47
   17     fog        low              46
    5     fog        low              43
   13     fog        low              43
   13   clear       high              41
    8     fog        low              41
   18     fog        low              40
    2     fog        low              40
    2   clear       high              40
   15     fog        low              39
   14     fog        low              39
   18   clear       high              39
    7   clear       high              38
   16   clear       high              37
   22   clear       high              37
=======================================================
  CHENNAI — Ticket to HELL Period 💀 
=======================================================

Quick findings from the data:
•	Chennai has 2,575 accidents — peak at 7 PM, worst day Friday
•	Fog + low visibility is the most dangerous combo in Chennai
•	Average temperature in Chennai accidents: 27.6°C 

=======================================================
Author = Prasanth Sundar
DATA ANALYST
Linkedin =https://www.linkedin.com/in/prasanth-sundar-b65475359/
Github = https://github.com/Prashantsundar 
=======================================================
