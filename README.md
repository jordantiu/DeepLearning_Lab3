# DeepLearning_Lab3

## I. Introduction

The purpose of this programming lab is to demonstrate the use and creation of different kinds of neural network models. These models are created from different datasets and can be used to make predictions on new sets of data.
 
 ## II. Objectives.
 
Provided were 6 questions that would allow one to understand the different neural network models in different situations. In the following examples we will be working with .csv datasets as well as image datasets. The questions are as follows:
 
![Questions](https://user-images.githubusercontent.com/47049525/57011101-9c81ea80-6bc5-11e9-840c-3052bfc2c8ad.PNG)

## III. Approaches/Methods / IV. Workflow
## 1.

Code:
![Q1 Code](https://user-images.githubusercontent.com/47049525/57013267-4a929200-6bd0-11e9-825a-330f01f31278.PNG)
![Q1 Code 2](https://user-images.githubusercontent.com/47049525/57013268-4a929200-6bd0-11e9-8b47-a9848616a808.PNG)

Part a:

![Loss Plot Q1](https://user-images.githubusercontent.com/47049525/57013141-b6c0c600-6bcf-11e9-99a2-07990aac821a.png)
![TensorBoard Q1](https://user-images.githubusercontent.com/47049525/57013143-b7595c80-6bcf-11e9-9761-a4310200a01b.png)

Part b:
Original:

model = Sequential() # create model
model.add(Dense(32, input_dim=n_cols, init='uniform', activation='sigmoid'))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(32, activation="relu", kernel_initializer="uniform"))
model.add(Dense(1, activation='tanh')) # output layer
model.add(Dropout(0.1))

model.compile(optimizer=Adam(lr=.001),loss='mean_squared_error', metrics=['accuracy'])
history = model.fit(X_train, Y_train, validation_data=(X_test, Y_test), epochs=50, batch_size=32, callbacks=[tbCallBack])

Trained:  0.88 , trained data loss 0.1153
Validation:  0.8824 , validation loss  0.1138
-------------------------------------------------------------------------------------------------------------------------------
LEARNING RATE CHANGE:

model = Sequential() # create model
model.add(Dense(32, input_dim=n_cols, init='uniform', activation='sigmoid'))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(32, activation="relu", kernel_initializer="uniform"))
model.add(Dense(1, activation='tanh')) # output layer
model.add(Dropout(0.1))

model.compile(optimizer=Adam(lr=.003),loss='mean_squared_error', metrics=['accuracy'])
history = model.fit(X_train, Y_train, validation_data=(X_test, Y_test), epochs=50, batch_size=32, callbacks=[tbCallBack])

Trained:  0.88 , trained data loss 0.111
Validation:  0.8824 , validation loss  0.1102
-------------------------------------------------------------------------------------------------------------------------------
BATCH SIZE CHANGE:

model = Sequential() # create model
model.add(Dense(32, input_dim=n_cols, init='uniform', activation='sigmoid'))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(32, activation="relu", kernel_initializer="uniform"))
model.add(Dense(1, activation='tanh')) # output layer
model.add(Dropout(0.001))

model.compile(optimizer=Adam(lr=.001),loss='mean_squared_error', metrics=['accuracy'])
history = model.fit(X_train, Y_train, validation_data=(X_test, Y_test), epochs=50, batch_size=16, callbacks=[tbCallBack])

Trained:  0.88 , trained data loss 0.1082
Validation:  0.8824 , validation loss  0.1067
-------------------------------------------------------------------------------------------------------------------------------
OPTIMIZER CHANGE:

model = Sequential() # create model
model.add(Dense(32, input_dim=n_cols, init='uniform', activation='sigmoid'))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(64, activation="relu", kernel_initializer="uniform"))
model.add(Dense(32, activation="relu", kernel_initializer="uniform"))
model.add(Dense(1, activation='tanh')) # output layer
model.add(Dropout(0.1))

model.compile(optimizer=SGD(lr=.001),loss='mean_squared_error', metrics=['accuracy'])
history = model.fit(X_train, Y_train, validation_data=(X_test, Y_test), epochs=50, batch_size=32, callbacks=[tbCallBack])

Trained:  0.12 , trained data loss 0.4843
Validation:  0.1176 , validation loss  0.4854

-------------------------------------------------------------------------------------------------------------------------------
ACTIVATION CHANGE:

model = Sequential() # create model
model.add(Dense(32, input_dim=n_cols, init='uniform', activation='sigmoid'))
model.add(Dense(64, activation="sigmoid", kernel_initializer="uniform"))
model.add(Dense(64, activation="sigmoid", kernel_initializer="uniform"))
model.add(Dense(64, activation="sigmoid", kernel_initializer="uniform"))
model.add(Dense(32, activation="sigmoid", kernel_initializer="uniform"))
model.add(Dense(1, activation='relu')) # output layer
model.add(Dropout(0.1))

model.compile(optimizer=Adam(lr=.001),loss='mean_squared_error', metrics=['accuracy'])
history = model.fit(X_train, Y_train, validation_data=(X_test, Y_test), epochs=50, batch_size=32, callbacks=[tbCallBack])
Trained:  0.88 , trained data loss 0.1124
Validation:  0.8824 , validation loss  0.111



## 2.
This question implements Logistic Regression on the heart disease uci dataset.
![Question 2 Code](https://user-images.githubusercontent.com/47049525/57012644-313c1680-6bcd-11e9-9f6d-ee8fa2b4cfb7.PNG)

Q2 Loss:
![Q2 loss](https://user-images.githubusercontent.com/47049525/57013118-91cc5300-6bcf-11e9-93b6-45e32c5ec3c8.png)


## 3.
This question implements the image classification with CNN (Convolutional Neural Network) on the natural-images dataset.

Code:
![Code1](https://user-images.githubusercontent.com/47049525/57012540-ae1ac080-6bcc-11e9-9556-2534ef210031.PNG)
![Code2](https://user-images.githubusercontent.com/47049525/57012542-ae1ac080-6bcc-11e9-8218-8a9e82be1da8.PNG)

Results:
![Question 3 CNN Result](https://user-images.githubusercontent.com/47049525/57012110-80347c80-6bca-11e9-90c0-17e365f10164.PNG)


## 4.
This question implements the text classification with CNN (Convolutional Neural Network) on the following movie reviews dataset.

Code:
![CNN_1st](https://user-images.githubusercontent.com/47049525/57012094-609d5400-6bca-11e9-8f75-bf3b9456f0f9.PNG)
![CNN_2nd](https://user-images.githubusercontent.com/47049525/57012095-609d5400-6bca-11e9-97af-0731240d04b4.PNG)

Output:
![CNN_Output_1](https://user-images.githubusercontent.com/47049525/57012096-609d5400-6bca-11e9-89d2-6e827085e607.PNG)
![CNN_Output_2](https://user-images.githubusercontent.com/47049525/57012097-6135ea80-6bca-11e9-84fe-2d0ed275f1e6.PNG)


## 5.

This question implements the text classification with LSTM (Long Short Term Memory) on the following movie reviews dataset.

Code:
![5th Question Code Part 1](https://user-images.githubusercontent.com/47049525/57012046-292ea780-6bca-11e9-9a41-4d8e6a5f64aa.PNG)
![5th Question Code Part 2](https://user-images.githubusercontent.com/47049525/57012047-292ea780-6bca-11e9-85ba-d1c3bccf8001.PNG)

Output:
![5h Question Output](https://user-images.githubusercontent.com/47049525/57012048-292ea780-6bca-11e9-8748-d65e3ee739c6.PNG)


## 6.
Using LSTM model, we got 62% accuracy over 50.48% with CNN model. Thus, for this case, LSTM is clearly a better way to go.

Holding other Hyperparameters constant:

1-When added more layers to CNN, accuracy increased from 50.48% to 50.55%.

2-When changed the Epoch from 2 to 5 in CNN model, accuracy increased from 50.48% to 50.81%.

3-When used “Sigmoid” instead of “Relu” in CNN model, accuracy remained unchanged at 50.48%.

4-When used “Tanh” instead of “Relu” in CNN model, accuracy increased from 50.48% to 50.91%.

5-When changed learning rate from 0.01 to 0.02 in CNN model, accuracy increased from 50.48% to 50.82%.

Changed Layer Number:
![CNN_Changed_Layer_Num](https://user-images.githubusercontent.com/47049525/57011637-46627680-6bc8-11e9-9c2a-de231ef18ee0.PNG)

Changed Epoch from 2 to 5:
![CNN_5Epochs](https://user-images.githubusercontent.com/47049525/57011576-f4215580-6bc7-11e9-82f6-64b92fc51116.PNG)

Used Sigmoid Function:
![CNN_Sigmoid](https://user-images.githubusercontent.com/47049525/57011639-46fb0d00-6bc8-11e9-91c7-f034e8f34c9f.PNG)

Used Tanh Function:
![CNN_Tanh](https://user-images.githubusercontent.com/47049525/57011635-46627680-6bc8-11e9-8caf-f308e69c0b98.PNG)

Changed Learning rate from 0.01-0.02:
![CNN_L_Rate_0 02](https://user-images.githubusercontent.com/47049525/57011638-46627680-6bc8-11e9-9f2a-8e684166fa44.PNG)




## V. Dataset

The only dataset used was the data table about the United States of America and its respective states.
![Screenshot](https://i.imgur.com/To2WFXe.png)

## VI. Parameters

There were no parameters as these were indivudual questions with no correlation to eachother.

## VII Evaluation and Discussion

The questions provided were quite challenging. Additional features could have been added to many of the programs above such as error handling, or bad input. Some of the questions were confusing to implement as the questions could have been clarified more. Such as in question 6 whether it was asking for the entire table or just the States and Capital. Question 5 did not have a clear goal in output other than just to implement classes.

## VIII Conclusion

Overall this lab was an excellent exercise to prepare for Deep Learning using python. It has gone over the basics of scraping the web, and using its basic functions. 
