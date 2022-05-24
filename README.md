# Mars-spectrometry-14th-place-solution
## This is my final solution to the Mars-spectrometry challenge by NASA hosted on drivendata.
[check out this competetion here](https://www.drivendata.org/competitions/93/nasa-mars-spectrometry/)


**Why this challenge ?**

TLDR:

NASA's rover sends back data after conducting evolutionary gas analysis on the soil samples it collected. We need to model if given 10 compounds are present
in the sample.

The story so far:

We all are curious about our neighbouring red planet.
So NASA's been sending rovers to the surface of Mars, These rovers move on the surface of the mars and collect various soil samples.
These rovers are also equipped with gas evoultionary analysis(EGA) instruments.
The collected soil samples are heated at different temperatures and the evolved gaseous ions are observed. Based on the abundance of evolved ions we can tell what kind of chemical compostion the soil sample is made of. This is called EGA

The data generated from the whole EGA is sent back to the earth. Now Scientists need to model this data to find clues about presence of any life on the martian soil.

The data is available at competition website (You have to login to datadriven).
We as Data scientists or Machine Learning practioners have to model this data to find out the best possible model and to make the best predictions.


**About the Problem:**
- The very domain/nature of the problem is unique.
- The data has less samples and lots of features.
- The problem requires us to classify the prescence of 10 targets ( carbonate, iron_oxide, sulfate etc...)
- The metric used is aggregated_log_loss.


**My solution:**
- My final soulution is simple average of caliberated predictions of ensemble models.
- I used logistic regression to find out the most relevant features (feature selection) [selected 10s of features from more than 10k features].
- Added other features like total_abundance for each sample, relative abundance, changes in abundance of ions etc... (feature engineering).
- Generated 8 different types of training sets based on various temperature and time bins (feature engineering).
- used 20 fold cross validation.
- used 10 Catboost classifiers to predict 10 targets (Binary classification fashion) on each dataset.
- Caliberated every models predictions to better match the targets.
- Stacked the predictions in simple average fashion.

**Other things I have tried**
- Nerual networks --> not very great for this competition
- Autoencoders and denoising autoencoders and they too didn't workout
- upsampling the minority class
- Automated feature Engineering (feature tools) didn't workout due to huge data and low compute resources.



Thank you 

Have a nice day😊
