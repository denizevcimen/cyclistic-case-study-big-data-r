# Install packages, prepare the workspace

```R
library(tidyverse)
library(lubridate)
library(ggplot2)
setwd("/Home/Desktop/cyclistic_case_study/cyclistic_data_original")
```

# Upload datasets

```R
march_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-03_trip_data/202203-divvy-tripdata_original.csv")

april_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-04_trip_data/202204-divvy-tripdata_original.csv")

may_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-05_trip_data/202205-divvy-tripdata_original.csv")

june_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-06_trip_data/202206-divvy-tripdata_original.csv")

july_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-07_trip_data/202207-divvy-tripdata_original.csv")

august_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-08_trip_data/202208-divvy-tripdata_original.csv")

sept_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-09_trip_data/202209-divvy-tripdata_original.csv")

oct_2022_trip <- read.csv("/Home/Desktop/project/cyclistic_case_study/cyclistic_data_original/2022-10_trip_data/20221-divvy-tripdata_original.csv")
```

# Rename columns  to make them consistent

```R
colnames(march_2022)

march_2022 <- plyr::rename(march_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                      "started_at" = "start_time", "ended_at" = "end_time",
                      "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                      "end_station_name" = "to_station_name",
                      "end_station_id" = "to_station_id", 
                      "member_casual" = "usertype"))

april_2022 <- plyr::rename(april_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                       "started_at" = "start_time", "ended_at" = "end_time",
                                       "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                       "end_station_name" = "to_station_name",
                                       "end_station_id" = "to_station_id", 
                                       "member_casual" = "usertype"))

may_2022 <- plyr::rename(may_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                         "started_at" = "start_time", "ended_at" = "end_time",
                                         "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                         "end_station_name" = "to_station_name",
                                         "end_station_id" = "to_station_id", 
                                         "member_casual" = "usertype"))

june_2022 <- plyr::rename(june_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                          "started_at" = "start_time", "ended_at" = "end_time",
                                          "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                          "end_station_name" = "to_station_name",
                                          "end_station_id" = "to_station_id", 
                                          "member_casual" = "usertype"))

july_2022 <- plyr::rename(july_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                           "started_at" = "start_time", "ended_at" = "end_time",
                                           "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                           "end_station_name" = "to_station_name",
                                           "end_station_id" = "to_station_id", 
                                           "member_casual" = "usertype"))

august_2022 <- plyr::rename(august_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                             "started_at" = "start_time", "ended_at" = "end_time",
                                             "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                             "end_station_name" = "to_station_name",
                                             "end_station_id" = "to_station_id", 
                                             "member_casual" = "usertype"))

sept_2022 <- plyr::rename(sept_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                           "started_at" = "start_time", "ended_at" = "end_time",
                                           "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                           "end_station_name" = "to_station_name",
                                           "end_station_id" = "to_station_id", 
                                           "member_casual" = "usertype"))

oct_2022 <- plyr::rename(oct_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                          "started_at" = "start_time", "ended_at" = "end_time",
                                          "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                          "end_station_name" = "to_station_name",
                                          "end_station_id" = "to_station_id", 
                                          "member_casual" = "usertype"))

nov_2022 <- plyr::rename(nov_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                          "started_at" = "start_time", "ended_at" = "end_time",
                                          "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                          "end_station_name" = "to_station_name",
                                          "end_station_id" = "to_station_id", 
                                          "member_casual" = "usertype"))

dec_2022 <- plyr::rename(dec_2022, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                          "started_at" = "start_time", "ended_at" = "end_time",
                                          "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                          "end_station_name" = "to_station_name",
                                          "end_station_id" = "to_station_id", 
                                          "member_casual" = "usertype"))

jan_2023 <- plyr::rename(jan_2023, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                          "started_at" = "start_time", "ended_at" = "end_time",
                                          "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                          "end_station_name" = "to_station_name",
                                          "end_station_id" = "to_station_id", 
                                          "member_casual" = "usertype"))

feb_2023 <- plyr::rename(feb_2023, vec_c("ride_id" = "trip_id", "rideable_type" = "bike_id", 
                                         "started_at" = "start_time", "ended_at" = "end_time",
                                         "start_station_name" = "from_station_name", "start_station_id" = "from_station_id",
                                         "end_station_name" = "to_station_name",
                                         "end_station_id" = "to_station_id", 
                                         "member_casual" = "usertype"))
```

# Union all trips

```R
all_trips <- bind_rows(march_2022, april_2022, may_2022, june_2022, july_2022, august_2022, sept_2022, oct_2022, nov_2022, dec_2022, jan_2023, feb_2023) 
```

# List of column names

```R
colnames(all_trips)
```

# Row numbers of the data frame

```R
nrow(all_trips)
```

# Dimensions of the data frame

```R
dim(all_trips)
```

# First 6 rows of the data frame

```R
head(all_trips)
```

# List of columns and data types

```R
str(all_trips)
```

# Statistical summary of data

```R
summary(all_trips)
```

# Checking user-type columns 

```R
membership_counts<- table(all_trips$usertype)
print(membership_counts)
```

# Adding columns that list the date, month, day, and year of each ride

```R
all_trips$date <- as.Date(all_trips$start_time)
all_trips$month <- format(as.Date(all_trips$date), "%m")
all_trips$day <- format(as.Date(all_trips$date), "%d")
all_trips$year <- format(as.Date(all_trips$date), "%Y")
all_trips$day_of_week <- format(as.Date(all_trips$date), "%A")
```

# Add a "ride_length" calculation to all_trips (in seconds)

```R
all_trips$ride_length <- difftime(all_trips$end_time, all_trips$start_time)
str(all_trips)
```

# Convert "ride_length" from Factor to numeric

```R
is.factor(all_trips$ride_length)
class(all_trips$ride_length)

all_trips$ride_length <- as.numeric(as.character(all_trips$ride_length))
is.numeric(all_trips$ride_length)
```

# Remove bad data

```R
all_trips_v2 <- all_trips[!(all_trips$from_station_name == "HQ QR" | all_trips$ride_length < 0), ]
```

# Descriptive analysis on ride_length

```R
is.numeric(all_trips_v2$ride_length)
class(all_trips_v2$ride_length)
```

# Mean value of ride length

```R
mean(all_trips_v2$ride_length)
```

# Median value of ride length

```R
unique_values <- unique(all_trips_v2$ride_length)
print(unique_values)

filtered_data <- all_trips_v2[all_trips_v2$ride_length != 0, ]
median_value <- median(filtered_data$ride_length)
print(median_value)
```

# Longest ride 

```R
max(all_trips_v2$ride_length)
```

# Shortest ride

```R
min(all_trips_v2$ride_length)
```

# Summary

```R
summary(all_trips_v2$ride_length)
```

# Compare members and casual users

```R
aggregate(all_trips_v2$ride_length ~ all_trips_v2$usertype, FUN = mean)
aggregate(filtered_data$ride_length ~ filtered_data$usertype, FUN = median)
aggregate(all_trips_v2$ride_length ~ all_trips_v2$usertype, FUN = max)
aggregate(all_trips_v2$ride_length ~ all_trips_v2$usertype, FUN = min)
```

# See the average ride time by each day for members vs casual users

```R
aggregate(all_trips_v2$ride_length ~ all_trips_v2$usertype + all_trips_v2$day_of_week, FUN = mean)
```

# The days of the week order fixation

```R
all_trips_v2$day_of_week <- ordered(all_trips_v2$day_of_week, levels=c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))
```

# The average ride time by each day for members vs casual users

```R
aggregate(all_trips_v2$ride_length ~ all_trips_v2$usertype + all_trips_v2$day_of_week, FUN = mean)
```

# Analyze user-type data by type and weekday

```R
usertype_avg_ride_time <- aggregate(ride_length ~ usertype + day_of_week, data = all_trips_v2, FUN = mean)

print(usertype_avg_ride_time)
```

# Create visualization for the average ride duration by user type

```R
avg_time_by_usertype <- aggregate(ride_length ~ usertype, data = all_trips_v2, FUN = mean)
ggplot(avg_time_by_usertype, aes(x = usertype, y = ride_length, fill = usertype)) +
  geom_bar(stat = "identity") +
  geom_text(aes(label = round(ride_length, 2)), vjust = -0.3, size = 4) +
  xlab("User Type") +
  ylab("Average Ride Time(seconds)") +
  ggtitle("Average Ride Time by User Type")
```

# Create average ride duration by user type and day of week

```R
ggplot(usertype_avg_ride_time, aes(x = day_of_week, y = ride_length, fill = usertype)) +
  geom_bar(stat = "identity", position = "dodge", color = "black") +
  geom_text(aes(label = round(ride_length, 2)), position = position_dodge(width = 0.7), vjust = -0.5) + 
  labs(x = "Day of the Week", y = "Average Ride Time", title = "Average Ride Time by User Type and Day of the Week") +
  scale_fill_discrete(name = "User Type") +
  theme_minimal()
```

# Create average ride duration by user type and day of week

```R
ggplot(usertype_avg_ride_time, aes(x = day_of_week, y = ride_length, fill = usertype)) +
  geom_bar(stat = "identity", position = "dodge", color = "black") +
  geom_text(aes(label = round(ride_length, 2)), position = position_dodge(width = 0.7), vjust = -0.5) + 
  labs(x = "Day of the Week", y = "Average Ride Time", title = "Average Ride Time by User Type and Day of the Week") +
  scale_fill_discrete(name = "User Type") +
  theme_minimal()
```

# Create a visualization of the number of rides by user-type

```R
ride_count_by_usertype <- table(all_trips_v2$usertype)

ggplot(data.frame(usertype = names(ride_count_by_usertype), count = as.numeric(ride_count_by_usertype)), aes(x = usertype, y = count, fill = usertype)) +
  geom_bar(stat = "identity") +
  geom_text(aes(label = count), vjust = -0.4, size = 4) + 
  xlab("User Type") +
  ylab("Number of Rides") +
  ggtitle("Number of Rides by User Type") +
  scale_y_continuous(labels = scales::comma)
```

# Create a visualization for the number of rides by day of the week

```R
ride_count_by_day <- table(all_trips_v2$day_of_week)
ride_count_df <- data.frame(day_of_week = names(ride_count_by_day), ride_count = as.numeric(ride_count_by_day))
ride_count_df$day_of_week <- factor(ride_count_df$day_of_week, levels = c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))
ggplot(ride_count_df, aes(x = day_of_week, y = ride_count, fill = day_of_week)) +
  geom_bar(stat = "identity", color = "black") +
  geom_text(aes(label = ride_count), vjust = -0.4, size = 4) + 
  xlab("Day of the Week") +
  ylab("Number of Rides") +
  ggtitle("Number of Rides by Day of the Week") +
  scale_fill_discrete(name = "Day of the Week") +
  theme_minimal()
```

# Create visualization for the number of rides by user type and day of the week

```R
rides_by_usertype_day <- table(all_trips_v2$usertype, all_trips_v2$day_of_week)
rides_df <- as.data.frame(rides_by_usertype_day)
rides_df$Day_of_Week <- rownames(rides_df)
rownames(rides_df) <- NULL
colnames(rides_df) <- c("User_Type", "Day_of_Week", "Number_of_Rides")
rides_df$Day_of_Week <- factor(rides_df$Day_of_Week, levels = c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))

ggplot(rides_df, aes(x = Day_of_Week, y = Number_of_Rides, fill = User_Type)) +
  geom_bar(stat = "identity", position = "dodge", color = "black") +
  geom_text(aes(label = Number_of_Rides), vjust = 0.5, size = 2.7, angle = 60, position = position_dodge(width = 0.9), fontface = "bold") +
  xlab("Day of the Week") +
  ylab("Number of Rides") +
  ggtitle("Number of Rides by User Type and Day of the Week") +
  scale_fill_discrete(name = "User Type") +
  theme_minimal() +
  theme(axis.text.x = element_text(angle = 45, hjust = 1),   
        axis.text.y = element_text(size = 10),          
        axis.title.y = element_text(size = 12),            
        plot.title = element_text(size = 14),         
        legend.title = element_text(size = 12),          
        legend.text = element_text(size = 10)) +           
  scale_y_continuous(labels = scales::comma) 
```