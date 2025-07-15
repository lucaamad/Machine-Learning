# Machine-Learning-project

## Description of the files

   - ais_train.csv - training data       
   - ais_test.csv - test input data                 
   - Dataset definitions and explanation.docx - a documents that gives more details about the dataset and column names  
   - Machine learning task.docx - brief introduction to the task
   - ports.csv - data related to ports
   - Report.pdf
   - Short_notebook_1.jpynb - Jupiter notebook with the implementation of the first method
   - Short_notebook_2.jpynb - Jupiter notebook with the implementation of the second method
   - vessels.csv - data related to vessels      

## The project

The objective of the project is to predict latitude and longitude of a set of vessels at predetermined time instants, given the previous positions and some weather features. In order to evaluate the predictions we use a score, namely the weighted average of the mean geodetic distance in killometer (using geopy.distance.geodesic) between the prediction and the ground truth point for each vessel. The weights adopted for the sum are decreasing in time. The evaluation takes place in two stages: first, we compare the performance of different models on a validation set composed by approximatively 50% of the "ais_test.csv" data (the exact observations contained in this slice of dataset are unknown). The evaluation on this dataset produces a "public score" (as it is called in the report). The final performance of the chosen model is evaluated on the remaining 50% of "ais_test.csv" data, producing a "private score". Toghether with my colleagues Rodolfo Coppola and Andrea Meschieri, we develope two solutions to the task: the first one exploits a Random Forest model trained on the entire "ais_train.csv" dataset; the second one is a more refined model, based on the introduction of lagged latitude and longitude features and on the re-training of the Random Forest model according to a rolling window approach.
