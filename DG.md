# Developer Guide

-----

## Content Page
1. [Introduction](#1-introduction)
2. [Setting up](#2-setting-up)
3. [Design](#3-design)
    1. [High Level Architecture](#31-high-level-architecture)
4. [Implementation](#4-implementation)
    1. [Project Info](#41-project-info)
    2. [Architecture](#42-architecture)
    3. [Operational Profile](#43-operational-profile)
    4. [Component Selection](#44-component-selection)
    5. [Cost and Sizing](#45-cost-and-sizing)
    6. [Simulate](#46-simulate)
    7. [Results](#47-results)
    8. [Performance](#48-performance)
    9. [Optimize](#49-optimize)
    10. [Menu](#410-menu)
    11. [Ready Map](#411-ready-map)
    12. [General Functions](#412-general-functions)

-----

## 1. Introduction
IPSOMEDT_Marine is a tool for marine engine development.
This developer guide provides information on the architecture and design of the application. 
It aims to provide a fast and efficient reference for code understanding, testing, debugging, and maintenance.
It will not only help you get started as a IPSOMEDT_Marine contributor, but that you will find useful to refer to even if you are already a contributor of this project.

## 2. Setting up
As a developer, this program requires the installation of MATLAB.

## 3. Design
### 3.1 High Level Architecture

## 4. Implementation
### 4.1 Project Info
* `AuthorEditFieldValueChanged`:
  * Updates variable based on user inputs for **Author**
* `DateEditFieldValueChanged`:
  * Update variable based on user inputs for **Date**
* `ProjectEditFieldValueChanged`:
  * Update variable based on user inputs for **Project**

### 4.2 Architecture
* `updateSingleLineDiagram`:
  * Initialises variables for **Number of Components per Busbar**
  * Initialises components and display style for **Single Line Diagram**
  * Plots **Single Line Diagram** on both positive and negative sides
* `updateArchitecture`:
  * Updates variables based on user inputs for **Architecture Parameters**
  * Updates variables based on user inputs for **Busbar Type**
  * Updates variables based on user inputs for **Number of Components per Busbar**
  * Adds selection options for **Plot selection** in **Simulate**
  * Adds selection options for **Left plot** and **Right plot** in **Results**
  * Toggles visibility for **Component Selection**
  * Enables **Run GT-Suite checkbox** in **Results**
  * Enables editability for **Component Selection**
  * Calls `ClearTableButtonPushed`, `updateOperationalProfile`, `updateSingleLineDiagram`, and `updateSfcResultsTable`
* `BusbartypeButtonGroupSelectionChanged`:
  * Enables **Frequency (Hz)** based on user selected busbar type
* `ShoreConnectionAvailDropDownValueChanged`, `BoostAlloweDropDownValueChanged`, `nDgDropDownValueChanged`, `nTdDropDownValueChanged`,
  `nAuxLoadDropDownValueChanged`, `nEssDropDownValueChanged`, `nHsgDropDownValueChanged`, `nFCDropDownValueChanged`:
  * Calls `updateArchitecture`
  
### 4.3 Operational Profile
* `updateOperationalProfile`:
  * Enables and initialises entry fields for **Average Load**
  * Populates column names on **Table**
  * Initialises table variables
* `PropellermModeDropDownValueChanged`:
  * Updates and initialises **HSG prop. speed (rpm)** based on user selection for **HSG propeller mode**
* `AutogeneratepeopellerrpmCheckBoxValueChanged`:
  * Enables **HSG prop. speed (rpm)** based on user selection for **Auto-generate propeller rpm** 
  * Calls `HSGproploadkWEditFieldValueChanged`
* `HSGproploadkWEditFieldValueChanged`:
  * Computes and updates column 1 of **HSG prop. speed (rpm)**
* `HSGproploadkWEditField2ValueChanged`:
  * Computes and updates column 2 of **HSG prop. speed (rpm)**

### 4.4 Component Selection
* `updateComponentSelectionTable`:
  * Obtains variables values based on user inputs for **Component Selection**
  * Computes and outputs **List of Components** in **Simulate**
  * Outputs **Display of Component Parameters**
* `InitializeComponentTable`:
  * Initialises variables
  * Initialises column formats and column names
  * Adds selection options 

### 4.5 Cost and Sizing

### 4.6 Simulate
* `updateDataSimVar`:
  * Clear and read data from the library, **User-defined Parameters**, and **Operational Profile**
  * Initialises simulation variables

### 4.7 Results
* `updateSfcResultsTable`:
  * Populates column names on **Fuel Consumption Table**
  * Initialises table variables
* `updateResultsTable`:
  * Computes, appends, and updates **Fuel Consumption Table**
  * Computes and updates **Summary**
* `updateResultsPlot`:
  * Sets display style and plots results on **Simulation Plots** based on user selection
  * Plots GT results on **Simulation Plots** if selected

### 4.8 Performance
* `updatePerformancePlot`:
  * Plots computed results on **Performance Plots** based on user selection of **Performance plot to display**

### 4.9 Optimize
* `checkOptConstraints`:
  * Checks optimisation constraints

### 4.10 Menu
* `LoadSessionMenuSelected`:
  * Fills all sections based on data from loaded .mat file
  * Loads data from .mat file and fills up **Project Info**, **Architecture**, **Simulate**, **Performance**
  * Populates **Table** in **Operational Profiles**
  * Selects components in **Component Selection**
  * Clears all figures and results tables
  * Selects plotting options for **Plot selection** in **Simulate**, **Left plot** and **Right plot** in **Results** if needed
  * Selects **include GT results** checkbox in **Results** if needed
  * Calls `ClearTableButtonPushed`, `BusbarTypeButtonGroupSelectionChanged`,
`PropellerModeDropDownValueChanged`, `updateComponentSelectionTable`, `ESSnParEditFieldValueChanged`, `updateDataSimVar`, 
`LoadPlotselctionDropDownValueChanged`, `ComputePerformanceButtonPushed`, `ResultsLeftaxisDropDownValueChanged`, 
`ResultsRightaxisDropDownValueChanged`, `updateResultsTable`
* `SaveSessionMenuSelected`:
  * Saves variables values and exports to .mat file
* `RefresheddisplaymessageMenuSelected`:
  * Displays 'ready' in green as the **Ready Map**

### 4.11 Ready Map
* `displayErrorMessage`:
  * Displays current error messages

### 4.12 General Functions
* `clearEditField`:
  * Clears and resets all user inputs to the default value of 0
* `save_close_excelfile`:
  * Saves the results to an Excel file
* `startUpFcn`:
  * Imports component libraries, functions, and testing files
  * Calls `initializeComponentTable`, `updateArchitecture`, `BusbarTypeButtonGroupSelectionChanged`, and `updateComponentSelectionTable`
  * Updates variables based on user inputs for **Project Info**
  * Adds date for user selection
  * Initialises **Ship Resistance** Table in **Performance**
  * Formats alignment for **Fuel Consumption Table** in **Results** and **Ship Resistance Table** in **Performance**

