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
* 
### 4.3 Operational Profile
* `updateOperationalProfile`:
  * Enables and initialises entry fields for **Average Load**
  * Populates column names on **Table**
  * Initialises variables for **Table**
* 
### 4.4 Component Selection
### 4.5 Cost and Sizing
### 4.6 Simulate
* `updateDataSimVar`:
  * Clear and read data from the library, **User-defined Parameters**, and **Operational Profile**
### 4.7 Results
* `updateSfcResultsTable`:
  * Populates column names on **Fuel Consumption Table**
  * Initialises variables for **Fuel Consumption Table**
* `updateResultsTable`:
  * Computes, appends, and updates **Fuel Consumption Table**
  * Computes and updates **Summary**
* `updateResultsPlot`:
  * Sets display style and plots results on **Simulation Plots**
  * Plots GT results on **Simulation Plots** if selected
### 4.8 Performance
* testing
### 4.9 Optimize
### 4.10 Menu
### 4.11 Ready Map
* `displayErrorMessage`:
  * Displays current error messages
### 4.12 General Functions
