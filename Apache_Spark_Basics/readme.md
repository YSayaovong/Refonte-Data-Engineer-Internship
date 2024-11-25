"""
Apache Spark Basics: Video Logs Processing
==========================================

This script demonstrates the basics of using Apache Spark to process video logs. 
It includes parsing, filtering, and aggregating data to count the number of times each video was played.

What this script accomplishes:
1. Parses raw video log data into structured tuples (user, video, action).
2. Dynamically filters logs to focus on the 'play' action.
3. Aggregates the number of times each video was played using Spark's `reduceByKey`.
4. Demonstrates scalable and parallel data processing with Apache Spark.
5. Outputs the results in a clear and concise format.

Example Input:
--------------
video_logs = [
    "user1,video1,play",
    "user2,video2,pause",
    "user1,video1,stop",
    "user3,video3,play",
    "user2,video2,play",
]

Example Output:
---------------
Video Play Counts:
video1: 1 times
video2: 1 times
video3: 1 times

"""

from pyspark import SparkContext, SparkConf

# Configure Spark Application
conf = SparkConf().setAppName("Apache Spark Basics").setMaster("local[*]")  # Use all CPU cores
sc = SparkContext(conf=conf)  # Create a Spark Context

# Video logs data
video_logs = [
    "user1,video1,play",
    "user2,video2,pause",
    "user1,video1,stop",
    "user3,video3,play",
    "user2,video2,play",
]

# What the script accomplishes:
# =============================
# 1. Parses raw data into structured tuples
# 2. Dynamically filters logs based on a specific action (e.g., "play")
# 3. Uses transformations like map, filter, and reduceByKey to process data efficiently
# 4. Leverages Spark's RDDs for parallel data processing
# 5. Clearly displays the results of video play counts

# Parallelize the video logs (create an RDD)
logs_rdd = sc.parallelize(video_logs)

# Step 1: Parse the log lines into structured tuples (user, video, action)
parsed_logs = logs_rdd.map(lambda log: tuple(log.split(",")))

# Step 2: Filter logs for a specific action (e.g., "play")
play_logs = parsed_logs.filter(lambda log: log[2] == "play")

# Step 3: Count occurrences of each video being "played"
video_play_count = (
    play_logs.map(lambda log: (log[1], 1))  # Map each video play to (video, 1)
    .reduceByKey(lambda x, y: x + y)  # Reduce by key to count plays per video
)

# Step 4: Collect the results to display
result = video_play_count.collect()

# Output the results
print("Video Play Counts:")
for video, count in result:
    print(f"{video}: {count} times")

# Stop the Spark Context
sc.stop()

"""
Accomplishments Summary:
=========================
1. Parsed raw data into structured tuples for processing.
2. Filtered logs dynamically to focus on the 'play' action.
3. Aggregated data efficiently using map and reduceByKey transformations.
4. Leveraged Apache Spark to demonstrate scalable parallel data processing.
5. Presented results in a clear and concise format for easy interpretation.

"""
