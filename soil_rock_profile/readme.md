Predicting the rock properties based on random forest algorithm
----

### 1. Objective

The aim of this experiment is to predict the rock properties like RQD, UCS and RMR at different locations/chainages and depth based on given borehole dataset using machine learning algorithms like [Random Forest Algorithm](https://en.wikipedia.org/wiki/Random_forest)

### 2. Dataset

10 Borehole data | each borhole is of 30m depth and consisting of data
This is how the table looks like - 

| Borehole|Depth (m)|Chainage (m)|UCS (MPa)|RQD (%)|
|-----:|-----:| -----:|-----:|-----:|
|1|8.25|29.71|8.52|0.0|
|1|11.25|29.71|29.61|39.0|
|1|14.25|29.71|32.95|54.0|

Here we have to predict the UCS, RQD and the RMR value based on the chainage and depth.

1. UCS is uniaxial compressive strength in megapascal unit
2. RQD is rock quality designation in percentage
3. RMR is rock mass rating

### 3. Brief introduction on RQD, UCS and RMR:

#### 3.1 [Rock Quality Designation (RQD)](https://theconstructor.org/geotechnical/rqd-rock-quality-designation-calculation/20536/)

Rock Quality Designation (RQD) is a measure of quality of rock core taken from a borehole. RQD signifies the degree of jointing or fracture in a **rock mass** measured in percentage, where RQD of 75% or more shows good quality hard rock and less than 50% show low quality weathered rocks

**Note: RQD is a rock mass property.**

![How RQD is measured](https://theconstructor.org/wp-content/uploads/2017/12/rqd-core-samples.jpg)

#### 3.2 [Uniaxial Compressive Strength (UCS)](https://civilblog.org/2013/08/11/unconfined-compressive-strength-of-rock-sample-is-9143-1979/)
The objective of this test is to determine unconfined compressive strength of intact rock. This test is primarily done to classify the **intact rock** on the basis of strength. 

**Note: The UCS of rock is an intact rock property**

![alt text](https://www.911metallurgist.com/blog/wp-content/uploads/2016/09/Unconfined-Compressive-Strength-Test.gif)

#### 3.3 [The rock mass rating (RMR)](https://en.wikipedia.org/wiki/Rock_mass_rating)

RMR is a geomechanical classification system for rocks, developed by Z. T. Bieniawski [1] between 1972 and 1973.[1] It combines the most significant geologic parameters of influence and represents them with one overall comprehensive index of rock mass quality, which is used for the design and construction of excavations in rock, such as tunnels, mines, slopes and foundations

More information please go to the link specified for both the properties.
