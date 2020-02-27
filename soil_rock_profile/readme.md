Predicting the rock properties based on borehole chainages and depth of the rock layer using machine learning algorithm
----

### Abstract

Geotechnical Investigation includes laboratory test of samples and field test. However these test are very expensive and time taking, hence investigation is done at some preferred locations based on the criticality and region of interest at a particular site. Based on these handful of data, geotechnical design parameters are summarized for the entire constrution site and further used for design of foundations, underground structures etc. However there is no clear way of summarizing these design parameters. A rational appoarch is proposed to predict the engineering properties of rock materials using machine learning algorithm. The results are found to be consistent and more reliable.


### 1. Objective

The aim of this experiment is to predict the rock properties like RQD, UCS and RMR at different locations/chainages and depth based on given borehole dataset using machine learning algorithms like [Random Forest Algorithm](https://en.wikipedia.org/wiki/Random_forest)

### 2. Dataset

10 Borehole data | each borhole is of 30m depth and consisting of factual data like UCS (Compressive Strength) and RQD (Rock Quality)
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

### 3. Brief introduction on RQD, UCS and RMR: (You can skip this section, if you already know these terms)

This section explains a brief introduction 
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

![RMR rating table](https://github.com/kavyajeetbora/civil_engineering/blob/master/soil_rock_profile/images/RMR%20rating.JPG)
[more information on RMR](http://www.rockmass.net/files/short_on_RMR-system.pdf)

Based on this rating, we find out the class of rock from very strong/good to highly weathered rocks

More information please go to the link specified for both the properties.

### 4. Results

Based on the chainage of the borehole and depth, The RQD, UCS and RMR property of the rock is predicted using random forest algorithm. 

[Here is the code in jupyter notebook format](https://github.com/kavyajeetbora/civil_engineering/blob/master/soil_rock_profile/geo_profile_rev_3.ipynb)

#### 4.1 RQD
![Prediction of RQD](https://github.com/kavyajeetbora/civil_engineering/blob/master/soil_rock_profile/images/profile.JPG)
This becomes very handy in plotting as well as accurate than previous methods like free hand drawing of the profile using CAD software. 
#### 4.2 UCS
![Prediction of UCS](https://github.com/kavyajeetbora/civil_engineering/blob/master/soil_rock_profile/images/UCS.JPG)

#### 4.3 RMR
![Prediction of RMR](https://github.com/kavyajeetbora/civil_engineering/blob/master/soil_rock_profile/images/RMR.JPG)

### 5. Features and application of this model - 
- Automates the taks of plotting the geotechnical profile 
- Better results than conventional method of drawing a profile i.e. manual plotting using CAD software.
- This can be a handy tool to quickly plot the profile by directly feeding the borehole data in csv format
- Can be used to predict any egineering properties like compressive strenth and RQD based on its chainage and depth.
- This can further help in design of foundations, like for example  determining the shaft capacity of piles in rocks (which depends upon the UCS value of rock)

### 6. *Evaluation of the model (optional)*

To Evaluate the model, metric [mean square error (MSE)](https://en.wikipedia.org/wiki/Mean_squared_error) was used. The model with lowest MSE was chosen for prediction. 
Since the data we are having is very less, [K-fold cross validation method](https://machinelearningmastery.com/k-fold-cross-validation/) was used for hyperparameter tunining of the model.
