# SDG 13: Climate action (Argument Detection)

### Purpose
We studied the Sustainable Development Goals (SDGs), specifically Goal 13: “Take urgent action to combat climate change and its impacts”. The problem we had to deal with was that a large number of papers are published each year without any accurate content quality evaluation. As a result, many papers either do not propose or support any new propositions, or do not provide evidence to back up their claims. Thus, the primary goal of our analysis was to correctly predict as many arguments (i.e., evidence and claims) as possible in order to be able to quickly evaluate the content of each paper. The code development was performed in Python.

### Overview of Analysis
First, we started by creating our data. We gathered paper abstracts by using SDG search queries (primarily) on Scopus and Mendeley based on targets and indicators of SDG 13. We focused on the annotation of three components in each paper's abstract (Topic, Argument, Research Theme).
Following that, the data was transformed into a series of different excel files (i.e., one for each paper) and then the data pre-processing, cleansing and preparation was completed. Then we used neural networks (CNN, RNN) which were tested for various (hyper-) parameters and were evaluated with the performance measurements that we deemed as appropriate given the target of our analysis. After selecting the “best” model, we demonstrated its performance using plots, curves and matrices. Finally, we used this model to make predictions.

### Data
The data file contains: 
Filename | Content
--- | ---
"argument"  | Contains all the documents as input in the train dataset.
"argument_test" | Contains all the documents as input for the test dataset.
"Model_CNN365" | Contains all the files needed for someone in order to use the best trained CNN model and its weights. To do so, it is necessary to load the model through Keras as described in the code ipynb file (“Main_code.ipynb”). 

### Code
The code file contains:
Filename | Content
--- | ---
"Main_code.ipynb" | Includes all the main code from data import, preparation/cleansing, building and running RNN and CNN models as well as evaluation measurements .
"CNN_parameter_testing.ipynb" | It was created only for testing the different (hyper-)paremeter values of the CNN model. The first part of the code is the same with the main code file. The testing begins from the «Build Text CNN Model» section.
"ML_MASTER_TEST.ipynb" | Includes code for accessing the best trained CNN model across the entire dataset (without splitting in train and validation parts). The first part of the code is identical to that of the “Main_code” file. In addition to the "winning" model, the jupyter notebook includes code for the (unseen) test dataset. The code reads the testing files' folder and exports a new file with the same filename and the results of the CNN argument detection per row for each file.
