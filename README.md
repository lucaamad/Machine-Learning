# Machine-Learning-project

## Description of the files

- `Dataset definitions and explanation.docx` – a document that gives more details about the dataset and column names  
- `Machine learning task.docx` – a brief introduction to the task
- `Report.pdf` - detailed report
- `Short_notebook_1.ipynb` – Jupyter notebook with the implementation of the first method  
- `Short_notebook_2.ipynb` – Jupyter notebook with the implementation of the second method  
- 'ais_train.csv' - training data       
- 'ais_test.csv' - test input data 
- 'schedules_to_may_2024.csv' - optional data that contains schedules for some vessels  
- 'ports.csv' - optional data related to ports           
- 'requirements.txt' - required Python packages and versions
- 'vessels.csv' - optional data related to vessels 

---

## The project

The objective of the project is to predict the latitude and longitude of a set of vessels at predetermined time instants, given the previous positions and some weather features. In order to evaluate the predictions, we use a score: the weighted average of the mean geodetic distance in kilometers (using `geopy.distance.geodesic`) between the prediction and the ground truth point for each vessel. The weights adopted for the sum decrease over time.

The evaluation takes place in two stages:  
First, we compare the performance of different models on a validation set composed of approximately 50% of the `ais_test.csv` data (the exact observations contained in this slice of the dataset are unknown). The evaluation on this dataset produces a *public score* (as it is called in the report).  
The final performance of the chosen model is evaluated on the remaining 50% of the `ais_test.csv` data, producing a *private score*.

Together with my colleagues **Rodolfo Coppola** and **Andrea Meschieri**, we developed two solutions to the task:

- The first one exploits a Random Forest model trained on the entire `ais_train.csv` dataset.  
- The second one is a more refined model, based on the introduction of lagged latitude and longitude features and on the re-training of the Random Forest model according to a rolling window approach.
