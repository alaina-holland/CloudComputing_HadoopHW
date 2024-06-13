# CloudComputing_HadoopHW
Homework for Cloud Computing

# Word Count with Hadoop Streaming

This repository contains modified `mapper.py` and `reducer.py` scripts for a Hadoop streaming word count job. The scripts treat words as "contiguous strings of letters."

## HW Assignment 
- https://gist.github.com/cd-public/50da4b723b9e53079b8b8b4bb9e56227 
  
## Dataset

The three books available in the public domain as shown in the exercise:
- `austen.txt`
- `shelley.txt`
- `bronte.txt`

The books were downloaded from the following URLs:
- [Austen](https://raw.githubusercontent.com/cd-public/books/main/pg1342.txt)
- [Shelley](https://raw.githubusercontent.com/cd-public/books/main/pg84.txt)
- [Bronte](https://raw.githubusercontent.com/cd-public/books/main/pg768.txt)

## Hadoop Streaming Command

The following command was used to run the Hadoop streaming job:

```bash
hdfs dfs -rm -r /user/sandbox/words
mapred streaming \
  -input /user/sandbox/books \
  -output /user/sandbox/words \
  -mapper mapper.py \
  -reducer reducer.py \
  -file scripts/mapper.py \
  -file scripts/reducer.py
