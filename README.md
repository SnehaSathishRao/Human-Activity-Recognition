# Human-Activity-Recognition
# Business Problem:<br/>
This project is to build a model that predicts the human activities such as Walking, Walking_Upstairs, Walking_Downstairs, Sitting, Standing or Laying.  It is a Multi-class classification.<br/>
# Data : <br/>

  The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.<br/>

  The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.<br/>

# Feature Information :<br/>

For each record in the dataset it is provided: <br/>
- Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration. <br/>
- Triaxial Angular velocity from the gyroscope. <br/>
- A 561-feature vector with time and frequency domain variables. <br/>
- Its activity label. <br/>
- An identifier of the subject who carried out the experiment.<br/>

# Class Labels: <br/>

In the dataset, Y_labels are represented as numbers from 1 to 6 as their identifiers.<br/>
1. WALKING as 1<br/>
2. WALKING_UPSTAIRS as 2<br/>
3. WALKING_DOWNSTAIRS as 3<br/>
4. SITTING as 4<br/>
5. STANDING as 5<br/>
6. LAYING as 6<br/>

# Summary:<br/>

1. Data Pre-processing :For each window we have 561 features which on signal processed each window gives 128 time-steps.And at every time-step we have 9 time-series readings.Three gyroscope time-series data,three accelerometer time-series data for body and total accelerometer time-series data.<br/>
2. Load Data : taking all these values and get train and test to model.<br/>
3. Initialising : random seed,epochs,hidden Layer,drop-out<br/>
4. Import : Keras,Tensor Flow,Sequential,LSTM<br/>
5. Input data : (7352*128*9);128 time steps,at every time step we have 9 time-series reading and 7352 time-series data(overlapped windows).<br/>
6. Training a model : Since the data input is very less,it is easy for the model to overfit if our model is complexly built.Hence choosing a simple LSTM architecture.<br/>
7. I have trained 5 models with different hidden and drop out values.The summary of the output is shown below.<br/>

# Conclusion:<br/>


|       Model        | Nuerons | Drop-out rate |                   score                   |
|---|---|---|---|
| LSTM(Single Layer) |    32   |      0.6      | [0.48826993001486146, 0.8829317950458093] |
| LSTM(Double Layer) |    32   |      0.6      |  [0.520119141131976, 0.8880217170003394]  |
| LSTM(Double Layer) |    64   |      0.6      |  [0.3858033237633154, 0.9284017645062775] |
| LSTM(Double Layer) |    32   |      0.8      |  [0.6408101797361757, 0.7441465897522904] |
| LSTM(Double Layer) |    64   |      0.8      |  [0.5258364012132946, 0.9026128266033254] |

