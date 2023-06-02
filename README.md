# CharacterIdentificationUsingDL
Identifying characters in fiction from dialogue using Deep Learning
All models were generated using the two notebooks: 
  1. Model_Friends.ipynb
  2. Model_SouthPark.ipynb
Instructions to reproduce results (same for both the scripts):
  1. Load the necessary libraries
  2. Load the dataset from the csv files (changing path to file if necessary)
  3. Create the optimizer (‘adamw’ optimizer is default)
  4. There’re 2 paths from this point: BERT & FastText word embeddings
  5. For using BERT:
    a. The urls to BERT models in TF Hub are defined in a dictionary. Choose the model & it’s preprocessing pipeline. Create the word embedding model.
    b. There are 3 architectures to try out: Vanilla DNN, CNN based & RNN based
    c. 3 different functions have the configurations for each of the 3 architectures
    d. Calling the function creates the model & fit the model to the data
    e. After each architecture, the model evaluation metrics are calculated.
These are the Matthew’s Correlation Coefficient and F1 scores (along with
the confusion matrix)
6. For using FastText:
  a. Load the pre-trained 300D model
  b. Create the Keras Text Vectorizer
  c. Create the embedding matrix for the current input & pass it to the Keras Embedding layer
  d. After step 3, the same flow as described in the ‘using BERT’ section follows. One 
  difference being, the Embedding layer & Text vectorizer are passed to the model creation
  instead of the BERT word embedding layers. 
  e. Finally, the same model evaluation metrics are calculated

Initially, the raw datasets were cleaned using these two notebooks: 
  1. FriendsDatasetPrep.ipynb
  2. SouthParkDatasetPrep.ipynb
Both scripts, take in the entire dialogue data, for all characters across seasons. 
Then filter out the main characters. Finally, encoding them into integers.
