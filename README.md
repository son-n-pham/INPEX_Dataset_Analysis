# INPEX_Dataset_Analysis

This is an analysis based on published dataset from INPEX in NOPIMS

All data used in this repo is published by INPEX, which can be found in NPIMS:

https://nopims.dmp.wa.gov.au/Nopims/Search/Wells

![image](https://github.com/son-n-pham/INPEX_Dataset_Analysis/assets/79841341/1a0c8833-8f36-4b3c-abde-df76b0e45a61)

ChatGPT 4 with Noteable is used to quickly create a Jupyter Notebook to work with the data and create a Jupyter Notebook template to work more effectively with this type of dataset.

Youtube video testing Noteable

https://youtu.be/NlLBMyig6ro

# Data Extraction

- Mud drilling report with structured and unstructured data is placed in the DDR folder in data folder
- The data_extraction.ipynb is exploring on how to extract data from the mud drilling report effectively.
- LLM models are tested to define which model is reliable to extract data.
- So far, gpt-3.5-turbo-0613 is giving the most reliable answer.
- Below is the testing prompt.

```
<|im_start|>system
This is a text extraction task. You must ONLY output the requested data in valid JSON format, without any other text or explanation whatsoever. If the requested data cannot be found, output an empty JSON object {}.
<|im_end|>
<|im_start|>user
What is the Azi from the below? The data below is extracted from structured and unstructured data, thus you need to identify the required data for answer in unstructured or structured tables for precise extraction.

DAILY MUDLOGGING REPORT
WELL INFORMATION:
Rig: JACK BATES  Field: ICHTHYS  Well: BDC-1B-03  Planned TD : 5234.0 mMDRT
Planned TVDRT : 4112.0 m

Date:  30Apr-2016 Report #:  08 Corresponding DDR:  08

Midnight Depths  MD:  1795.0  mMDRT TVDBRT:  1794.11 mTVDRT  TVDLAT: -1765.11  m
Last Deviation survey Depth: 1781.66 mMDRT Inc: 3.27° Azi: 311.52°
Last casing:  Size:  20"  Shoe depth: 702.94 mMDRT
Liner:   Size:    Shoe depth:

Hydraulics:
OPERATIONS SUMMARY (last 24 hrs)
Drilled 17 ½" hole from 1044.0 mMDRT to 1795.0 mMDRT.

Note: Estimated down hole Losses: 628 bbls                                                                                  Esti mated 24 Hour Surface Losses : 1187 bbls
DAILY TIME ANALYSIS (Hours): FORMATION
Drilled from
(m) Drilled
to (m)  Meterage
(m) Rotary Drilling hours on
bottom (hrs)  Sliding Drilling
hours (hrs) Average ROP
(m/hr)  Hours in hole
( hrs)  Pumping Hours
( hrs)
Daily 1044 1795 751.0 16.62 1.25 41.97 24.0 21.94
Total 710.8 1795 1084.2 24.74 4.23 37.42 45.75 37.12

DRILLING FORMATION
Depth Interval
(m)
ROP range
(m/hr)
Min/Max/Avg  WOB range
(Klbm)
Min/Max/Avg  BIT RPM range
( 1/min)
Min/Max/Avg  TD RPM range
(1/min)
Min/Max/Avg  Torque range
(Klbf.f)
Min/Max/Avg  Flow Pumps
(gpm)
Min/Max/Avg  SPP (psi)
Min/Max/Avg
1044.0-
1795.0 2.1 / 213.8 /
41.97 0 / 25.6 / 1.1 68 / 162 / 136 0 / 64 / 46 0 / 18.4 / 4.63 850 / 1156 / 1125 1277 / 2331 / 2016

<|im_end|>
<|im_start|>assistant
```
- Arena (side-by-side) in chat.lmsys.org is used to test the models.
