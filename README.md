# Smart-Tools

# Usage

Download the data from the link provided below and put it in a folder called 'data'. The file tree should then look like:

```
.
├── data
│   ├── Human
│   │   ├── Processed Data
│   │   ├── Run_1_Samples
│   │   ├── Run_2_Samples
│   │   ├── Run_3_Samples
│   │   ├── Run_4_Samples
│   │   ├── Run_5_Samples
│   │   ├── Run_6_Samples
│   │   ├── Run_7_Samples
│   │   ├── Run_8_Samples
│   │   ├── Run_9_Samples
│   │   └── Subject_5_different_tool
│   ├── No Pretraining vs. Pretraining
│   │   ├── Human trained + no pretraining (Seed: 42).csv
│   │   ├── Human trained + no pretraining (Seed: 43).csv
│   │   ├── Human trained + no pretraining (Seed: 44).csv
│   │   ├── Human trained + no pretraining (Seed: 45).csv
│   │   ├── Human trained + no pretraining (Seed: 46).csv
│   │   ├── Human trained + Yaskawa pretraining (Seed: 42).csv
│   │   ├── Human trained + Yaskawa pretraining (Seed: 43).csv
│   │   ├── Human trained + Yaskawa pretraining (Seed: 44).csv
│   │   ├── Human trained + Yaskawa pretraining (Seed: 45).csv
│   │   └── Human trained + Yaskawa pretraining (Seed: 46).csv
|   └── Yaskawa
│       ├── Arduino_Yaskawa
│       ├── Processed Data
│       └── Raspberry_Yaskawa
```

# Data

Raw data from accelerometer, gyroscope, magnetometer, current sensor and microphone are collected using an arduino. 

Here's the link for both human and robot data. 

Source: [Drive link](https://utexas.box.com/s/ail8mdlvn97gygzu6eefn3nr0un53v46).

## Raw data from human subjects 

The raw data is separated into 4 folders under each subject folder representing the four activities we predict. The files under human subjects are named `Subject_X_<task><10-digit-timestamp>`. Here, the \<task> represents the task: 

1. E = Engrave
2. C = Cut
3. S = Sand
4. R = Route

## Raw data from Yaskawa Robot

The Yaskawa robot had both an arduino and a raspberry pi connected to it for redundancy in data collection. Therefore, 2 folders `Arduino_Yaskawa` and `Raspberry_Yaskawa` are present. The files in each folder are named: `A_<task>_Main_Data_<run_number>`. As in the human data case, \<task> can be one of the four activities: "Engrave", "Cut", "Sand", or "Route". 

## Processed data

Once the data is collected and stored into separate `.csv` files, it is cleaned and processed. In both the drive folders, `Human` and `Yaskawa`, there is a `Processed Data` folder consisting of one parquet file that contains this processed data. Note that the files are stored in `.parquet` for memory efficiency over `.csv`. 

# TODO

- [X] Add data links
- [X] Rename Tree - Level 1 folders (anonymize subjects)
- [X] Rename Tree - Level 2 folders (anonymize subjects)
- [ ] Add scripts to run each plot
  - [X] data vs accuracy
  - [ ] sensor comparisons
  - [ ] id ood barplot
- [ ] Write meaning of each column in the data in README
- [ ] Add comments in the code

 
