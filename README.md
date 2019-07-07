# MapReduce

Hadoop MapReduce FollowerCount
Example code for CS6240
Spring 2019

Code author
-----------
Virat Goradia

## Program description

This program reads the input line by line, and splits the line based on a comma, done by my string tokenizer. For example, the input has the format “user_id_a, user_id_b”, which means user_id_a follows user_id_b. Hence, this means user_id_b is followed by one user. Thereby, the mapper function extracts the user_id_b and it outputs (user_id_b,1) . Since the split function will split on the basis of a “comma”, we need the string which is to the right of the comma, which means we need every second string after we perform the split. Thereby, I have an integer “i” initialized to 0, and on every even count of the value of “i”, we add (key: user_id, value: 1) to our mapper output.

The reduce function is pretty straightforward. It has a similar implementation to that of the word count demo program. It simply adds up the list of values for every key that exists and generates the final output.

### AWS Runs

- Amount of data transferred to mappers: 1319441892 bytes
- Amount of data transferred from mappers to reducers: 961483442 bytes 
- Amount of data transferred from reducers to output: 67641452 bytes
- Runtime: 1 minute 55 seconds



