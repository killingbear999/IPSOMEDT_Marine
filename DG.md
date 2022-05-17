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

## 2. Setting up

## 3. Design
### 3.1 High Level Architecture

## 4. Implementation
### 4.1 Project Info

### 4.2 Architecture
* `updateSingleLineDiagram`:
  * Initialises variables for **Number of Components per Busbar**
  * Initialises components and display style for **Single Line Diagram**
  * Plots **Single Line Diagram** on both positive and negative sides
* `updateArchitecture`:
  * Updates variables based on user inputs for **Architecture Parameters**
  * Updates variables based on user inputs for **Busbar Type**
  * Updates variables based on user inputs for **Number of Components per Busbar**
  * Calls `ClearTableButtonPushed`, `updateOperationalProfile`, `updateSingleLineDiagram`, and `updateSfcResultsTable`
  * Adds selection options for **Plot selection** in **Simulate**
  * Adds selection options for **Left plot** and **Right plot** in **Results**
  * Toggles visibility for **Component Selection**
  * Enables **Run GT-Suite checkbox** in **Results**
  * Enables editability for **Component Selection**
  
### 4.3 Operational Profile
* `updateOperationalProfile`:
  * Enables and initialises entry fields for **Average Load**
  * Populates column names on **Table**
  * Initialises table variables

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
  * Calls `initializeComponentTable`, `updateArchitecture`, and `updateComponentSelectionTable`
  * Updates variables based on user inputs for **Project Info**
  * Adds date for user selection
  * Initialises **Ship Resistance** Table in **Performance**
  * Formats alignment for **Fuel Consumption Table** in **Results** and **Ship Resistance Table** in **Performance**

