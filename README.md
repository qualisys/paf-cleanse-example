# Qualisys PAF – Moveck Pipe / Cleanse Example

To download the latest version of the example project to your computer, you can either:

* [Click here](https://github.com/qualisys/paf-cleanse-example/archive/refs/heads/main.zip) to download the latest release.
<br>— or —
* Clone this repository to your computer.

## Preparing QTM project

There are two ways how to set up the project for QTM:

1. If you are going to use this example in a single project:
    1. Unzip the zip file with source code and copy its content into a QTM project
2. If you plan to create multiple projects based on this example, follow these steps to make the example available in the New Project dialog in QTM:
    1. Unzip the zip file with source code to `C:\Program Files\Qualisys\Qualisys Track Manager\Packages`
    2. Name the folder `Cleanse Example`
    3. Delete Settings.qtmproj. This makes the example available in QTM. Then for to QTM > File > New Project and create new project based on Cleanse Example.

## General Information

This repository provides an example of how to use the Moveck Pipe and Cleanse applications with QTM. It contains:
   - Two **walking trials** with **IOR**  marker set
   - Two force plates
   - Four EMG channels
   - Associated reconstruction method  

## Installation and Configuration for Automated Processing
The following steps describe the installation and configuration of Pipe and Cleanse to enable automated processing.

### 1. Installation Steps

1. Run the **Moveck Pipe installer**
2. Run the **Cleanse installer**

### 2. Pipe Processing Script Files

Copy and replace files from the GitHub repository to the following locations:

- From `Templates/configuration script`  
  → To `C:/Users/Public/Moveck/pipe/configurations/qtm`

- From `Templates/process pipeline`  
  → To `C:/Users/Public/Moveck/pipe/pipelines`

### 3. Cleanse Configuration

1. Open Cleanse  
2. Add the following template to your list of project templates:  
   `Templates/Cleanse - Template QTM Demo github.json`  
      *This allows you to view and clean the data.*

### 4. QTM Setup

1. Double click on `Settings.paf` to open the example project.

In QTM:

1. Go to `Project Options > Miscellaneous > Folder Options`
2. Set **PIQ** path to: `C:\Users\Public\Moveck\pipe\qtm\PIQ.exe`
3. Set **Cleanse** path to: `C:\Program Files\Moveck\cleanse\Moveck cleanse.lnk` 
      *`.lnk` is a shortcut to the actual version of Cleanse application*

## Processing

### QTM Processing

The execution of **Pipe** is directly integrated into QTM. 

1. To launch processing, simply select the session or a specific trial within QTM. 
      *The processing defined by the previously copied scripts will automatically run from there.*
2. Once the trial is selected, use **IOR2cleanse** to process the data using the configured pipelines. 
      *This step will automatically launch **Cleanse** with the appropriate project settings.*

The result of the processing will be accessible directly into the condition trial's folder, under a subdirectory named `Moveck`, using the condition name. 
In this example, the resulting file will be: `Moveck/Report_IOR01_2025-05-20.h5`

### Cleanse Processing

Upon opening the project in **Cleanse**, you will see that your dynamic and static trials are listed in the central **Trial Selection** area.

1. Select your dynamic trials.
2. Drag and drop the selected trials into the **Drag here** area of an analysis block in the **Analyses** section.
3. Click **"Start"** on the top bar to begin the data visualization.

### Additional Features in Cleanse:

- You can **select specific events** within the trial.  
- It is possible to **exclude inconsistent cycles** from the analysis.  
- The cleaned data can be **exported directly to Excel** for further processing or reporting.

## Resources for using the Qualisys Project Automation Framework (PAF)

The purpose of the ***Project Automation Framework*** (PAF) is to streamline the motion capture process from data collection to the final report. This repository contains an example project that illustrate how PAF can be used to implement custom automated data collection in [Qualisys Track Manager (QTM)](http://www.qualisys.com/software/qualisys-track-manager/), and how QTM can be connected to a processing engine. 

### PAF Documentation

The full documentation for PAF development is available here: [PAF Documentation](https://github.com/qualisys/paf-documentation).

### PAF Examples

Our official examples for various processing engines:

- [AnyBody](https://github.com/qualisys/paf-anybody-example)
- [Cleanse](https://github.com/qualisys/paf-cleanse-example)
- [ENABLE](https://github.com/qualisys/paf-enable-markerless-example)
- [Excel](https://github.com/qualisys/paf-excel-example)
- [Matlab](https://github.com/qualisys/paf-matlab-example)
- [OpenSim](https://github.com/qualisys/paf-opensim-example)
- [Python](https://github.com/qualisys/paf-python-example)
- [Theia Markerless](https://github.com/qualisys/paf-theia-markerless-example)
- [Theia Markerless Comparison](https://github.com/qualisys/paf-theia-markerless-comparison-example)
- [Theia Markerless True Hybrid](https://github.com/qualisys/paf-theia-markerless-true-hybrid-example)
- [Visual3D](https://github.com/qualisys/paf-visual3d-example)

_As of QTM version 2.17, the official Qualisys PAF examples can be used without any additional license. Note that some more advanced analysis types require a license for the "PAF Framework Developer kit" (Article number 150300)._
