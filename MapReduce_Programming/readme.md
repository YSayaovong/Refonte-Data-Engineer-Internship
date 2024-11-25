# Call Logs Aggregator

```python
# What I Accomplished:
# =====================

# Data Aggregation:
# - Built a Python-based tool to efficiently aggregate call durations for multiple users.
# - Used a structured approach to process a list of user call logs and group data dynamically.

# Algorithm Design:
# - Leveraged Python's `defaultdict` to simplify the handling of dynamic data grouping.
# - Eliminated the need for manual checks or initialization for missing keys, ensuring concise and efficient logic.

# Results Output:
# - Programmatically calculated total call durations for each user based on raw input data.
# - Presented the aggregated results in a clear and concise format for better readability and analysis.

# Problem Solving:
# - Addressed a common real-world scenario involving grouped data processing.
# - Applied fundamental Python programming concepts like loops, dictionaries, and string manipulation 
#   to deliver a robust solution.

# Modular and Extendable Code:
# - Designed the program to handle a variety of datasets without requiring significant code changes.
# - Made it easy to customize the input format, modify processing logic, or expand functionality 
#   (e.g., adding features like filtering by duration or sorting results).

from collections import defaultdict

# Example call logs data
call_logs = [
    ('user1', 120),  # Example log entry: user1 made a call of 120 seconds
    ('user1', 120),
    ('user2', 60),
    ('user2', 30),
    ('user3', 300)
]

# Data Aggregation: Initialized a defaultdict to store total call durations for each user
user_call_durations = defaultdict(int)

# Algorithm Design: Iterate through the call logs to calculate total durations
for user, duration in call_logs:
    user_call_durations[user] += duration  # Aggregate duration for each user

# Results Output: Display the total call durations in a user-friendly format
for user, total_duration in user_call_durations.items():
    print(f"{user}: {total_duration} seconds")  # Example: "user1: 240 seconds"

# Next Steps for Customization (if needed):
# - Add functionality to filter users by minimum or maximum call durations.
# - Include options to sort users by their total durations or alphabetically.
# - Integrate data input from external sources like CSV files or databases.
