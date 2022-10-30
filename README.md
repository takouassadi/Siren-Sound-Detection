# Siren-Sound-Detection
Compare Various Techniques for Emergency Vehicle Detection using Audio Processing.


Pitch Detection : 

To do so, we have used the time delay for which the likelihood of the signal and a
retarded copy of it, is maximized which can be found using an MDF,To avoid the falling tendency of MDF, We have chosen to work with CAMDF which stands
for Circular Average Magnitude Difference Function, After looking for the pitch of the sound we searched for the Probability of the presence
of a siren so if pitch matches the pattern of the emergency signal, then indicates the
presence of an emergency signal.

![image](https://user-images.githubusercontent.com/91010908/198860046-b892cad2-6644-4546-b3c0-87f38ad731bb.png)


-----------------------------------
Knn method :

We have tested different values of n for this we chose a range from
1 to 100.Here's a plot of the Auc score for different values of n, as you can see the test curve shows
an increasing trend until between 15 and 20 where the accuracy can attain 80% and at this
point the curve decreases which is due to overfitting.

![image](https://user-images.githubusercontent.com/91010908/198860034-9d71e2e4-47d7-451b-838b-b42a5397c79f.png)

Since the most suitable value of n is in the range of 15 and 20, i did a manual test to know
exactly which value of n can give as the best results which means the biggest number of
roc_auc_score which is equal to 75.5% as you can in the figure downhere , so the value of n
we should work with is 20.

----------------------------------------

Ann model :

In order to create the classification model, the neural network input consists of 12 values
that correspond to the number of MFCC.
As you can see in the diagram down below, the accuracy increases rapidly in the first two
epochs, but afterward compared to the training data which plot keeps on increasing the
validation data plot starts to flatten and the gap between the two datasets gets bigger which
indicates that this is a case of overfitting, a,d since the gap is pretty large the overfitting
we're experiencing is a strong one, And that's due to the size of the training dataset
comparing to the validation one.

![image](https://user-images.githubusercontent.com/91010908/198860092-821fcb63-d4b1-4497-ac5a-33c6958dcae0.png)


Since our project is mainly a classification problem, we used as loss function the binary
cross-entropy which Computes the cross-entropy loss between true labels and predicted
labels.
As you can see in the figure down below, the plot of training loss continues to decrease with
experience. from another side, the plot of validation loss increases to a point and remain to
flatten which is an explanation that we are experiencing overfitting.


![image](https://user-images.githubusercontent.com/91010908/198860131-623f4701-232d-48ba-a920-991e0ff8e0b1.png)



