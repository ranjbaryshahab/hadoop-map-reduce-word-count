# Hadoop MapReduce Word Count

A simple Hadoop MapReduce program to count word occurrences in a given text file.

## How It Works
This application uses Hadoop's MapReduce framework to process large-scale text data. It consists of:
- **TokenizerMapper**: Splits text into words and emits each word with a count of `1`.
- **IntSumReducer**: Aggregates word occurrences and outputs the final word count.

## Prerequisites
- Java 8+
- Hadoop installed and configured
- `hadoop` command-line tool available

## Compilation & Execution

### 1. Compile the Java program
```sh
hadoop com.sun.tools.javac.Main Application.java
jar cf wordcount.jar Application*.class
```
### 2. Run the MapReduce Job
```sh
hadoop jar wordcount.jar Application /input /output
# Replace /input with the path to the input text file (HDFS location).
# Replace /output with the desired HDFS output directory.
```


### 3. View Results
```sh
hdfs dfs -cat /output/part-r-00000
```

## Notes
- Ensure Hadoop is running before executing the job.
- The program reads text files from HDFS, processes them, and writes results back to HDFS.
- The Combiner optimizes performance by reducing data transfer between map and reduce tasks.

