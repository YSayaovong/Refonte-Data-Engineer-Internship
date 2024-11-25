# Apache Spark Basics

This project demonstrates the basics of using Apache Spark to process video logs. It includes parsing, filtering, and aggregating data to count the number of times each video was played.

---

## Key Features

### **1. Input Data Processing**
- Parses raw video log data into structured tuples `(user, video, action)`.
  ```plaintext
  "user1,video1,play"
  "user2,video2,pause"
  "user1,video1,stop"
  "user3,video3,play"
  "user2,video2,play"

### 2. Filtering and Transformation
- Filters logs to include only the play action.
- Maps and reduces data to calculate aggregated statistics.

### 3. Result Presentation
- Outputs the number of times each video was played in a clear and concise format.
Video Play Counts:
```plaintext
video1: 1 times
video2: 1 times
video3: 1 times

## Accomplishments
### Data Parsing
- Parsed raw data into structured tuples (user, video, action) for easier access and processing.

### Dynamic Filtering
- Filtered logs to include only entries with the play action.

### Aggregation
- Used the reduceByKey transformation to count the occurrences of each video being played.

### Scalable Processing
- Leveraged Spark's RDDs to demonstrate scalable parallel data processing.

### Result Clarity
- Programmatically calculated and displayed results clearly and concisely.

### Summary of Accomplishments
- Data Parsing: Parsed raw data into structured tuples for efficient processing.
- Dynamic Filtering: Focused on specific actions (e.g., play) using filters.
- Aggregation: Used reduceByKey to calculate total play counts for each video.
- Scalable Processing: Demonstrated distributed data processing with Spark RDDs.
- Clear Output: Displayed results in an easy-to-understand format.
