# Digital Forensics Lab: Metadata & Signature Analysis

![Forensics](https://img.shields.io/badge/Forensics-Metadata-blue)
![Autopsy](https://img.shields.io/badge/Tool-Autopsy_4.22.1-green)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey)

------------------------------------------------------------------------

## 📋 Overview

This repository documents a completed **Digital Forensics investigation
lab** focused on metadata analysis and file signature examination.

The lab simulates a real-world forensic scenario involving:

-   Document tampering\
-   Hidden files\
-   Extension mismatches\
-   GPS-tracked photographs\
-   Metadata correlation

All analysis was conducted using industry-recognized forensic tools in a
controlled academic environment.

------------------------------------------------------------------------

## 🎯 Learning Objectives

-   Analyze **system metadata (MAC times)**\
-   Examine **application metadata** in Microsoft Office documents\
-   Perform **signature analysis** to detect extension mismatches\
-   Extract and interpret **EXIF data**, including GPS coordinates\
-   Conduct forensic examination using Autopsy\
-   Create evidentiary bookmarks and forensic reports

------------------------------------------------------------------------

## 🛠️ Tools Used

  Tool                 Purpose
  -------------------- --------------------------------------------
  **Autopsy 4.22.1**   Primary digital forensic analysis platform
  **IrfanView**        EXIF metadata extraction & GPS review


------------------------------------------------------------------------

## 🔍 Case Study Scenario

### Background

Leonard Kufner allegedly created a fraudulent harassment document to
falsely accuse his supervisor, Laquita Hishaw, after personal workplace
tensions arose.

The document was allegedly planted on Laquita's system during her
absence.

### Investigation Goal

Determine whether Laquita created the document or whether it was planted
from another source by analyzing:

-   File system metadata\
-   Application metadata\
-   Timestamps\
-   Ownership data\
-   File signature information


------------------------------------------------------------------------

# 🔬 Key Findings

## Task 1: Harassment Document Metadata Analysis

  -----------------------------------------------------------------------
  Metadata Type        Finding       Forensic Interpretation
  -------------------- ------------- ------------------------------------
  Created              2017-08-09    Appeared while suspect was absent
                       09:07:29      

  Modified             2017-08-08    Modified before creation → likely
                       14:23:11      copied

  Author               Leonard       Application metadata revealed origin
                       Kufner        

  Word Version         16.0000       Microsoft Word 2016

  Owner                Laquita       Ownership changed after copy
  -----------------------------------------------------------------------

### Conclusion

The document was created on another machine, copied to Laquita's system,
and falsely attributed to her. Application metadata confirmed the true
author.

------------------------------------------------------------------------

## Task 5: Signature Analysis -- Hidden PCB Design File

A `.brd` file was identified with a mismatched extension.

  File          Extension   True Format   Software
  ------------- ----------- ------------- ----------------------
  Circuit.brd   .brd        XML           Autodesk EAGLE 7.3.0

### Hex Signature

    <?xml version="1.0" encoding="utf-8"?>
    <!DOCTYPE eagle SYSTEM "eagle.dtd">
    <eagle version="7.3.0">

------------------------------------------------------------------------

## Task 6: Hidden Evidence Images

Multiple image files were verified through header signature analysis:

  Format   Hex Signature
  -------- -------------------------
  PNG      89 50 4E 47 0D 0A 1A 0A
  BMP      42 4D
  GIF      47 49 46 38
  JPEG     FF D8 FF E0
  TIFF     49 49 2A 00

------------------------------------------------------------------------

## Task 7: GPS Metadata in Photographs

EXIF metadata revealed:

-   Camera make/model\
-   Timestamps\
-   GPS coordinates\
-   Device identification

Example:

    Make: Apple
    Model: iPhone 6s
    Date: 2017:07:05 14:23:45
    GPS Latitude: 51°30'26.47"N
    GPS Longitude: 0°7'39.63"W
    Altitude: 34.2m

------------------------------------------------------------------------

# 📊 Core Forensic Concepts

-   MAC Times (Modified, Accessed, Created)\
-   Signature vs Extension Matching\
-   EXIF Data Extraction\
-   Evidence Bookmarking\
-   Report Generation

------------------------------------------------------------------------

# ⚖️ Legal & Ethical Notice

This project was completed for educational purposes in a controlled lab
environment. All case details are fictional.

------------------------------------------------------------------------

# 📝 Author

Arinze Ihekweme\
Digital Forensics Student\
2026
