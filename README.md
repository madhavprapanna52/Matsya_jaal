# Project : Matsya_Jaal
Aim : To prevent user from fraud/Jaal by giving them predictions of potential email sender's intentions to harm, An Machine learning sollution for Scam prevention
`
Structure 
|/Scam_detectiion_system
|--> /Dataset 
    |--> cleanned_dataset.csv
    |--> Phishing_Email.csv
|--> /Project_files
  |--> /_Pycache_
    |--> Data_preprocessing_unit.py
    |--> Development_documentation.txt
    |--> Feature_extraction_unit.py
    |--> Model_train.py
    |--> My_basic_tool.py
    |--> Pramukh_cli.py
    |--> logistic_model.pkl
    |--> logistic_vectorizer.pkl
  |--> Data_set.csv`
  
# Files basic discriptions 
1. Data_preprocessing_unit.py
    * Cleans the dataset, Makes tokens and stemming of words
    * Reduce computational load for model and removes irreleventsthus
    * Preventing errors in trainning and overall mathematical insights drawn from the model
2. Model_train.py
    > Here logistic regression model is trainned with simple bag of words vectorisation method
    insights
       - Using sklearn library auto optimisation techniques and default parameters, vectorisation of words takes place gets into fit function for trainning weights and bias, thus ge get straight the model through these simple steps , with its report tested on 20 percent of dataset we get 95 percent accuracy

3. Pramukh_cli.py
       - The command line interface of our program where it consists of an interface for user to know about email it want to check , simple and easy to use , here , user input gets into vectorisaiton process of converting words to numbers  (trained in dataaset) , Based on model the numbers fit scores are decleared leading to predictions as output ,

# Usage tips of project 
    1. Setup an python vertual environment with python version (3.9.10)
    2. install dependencies 
    2. Load these files and you have these options 
        > You can load the trained model and use the cli for using it. 
        > Load more dataset and them run files as these : My_basic_tool clean_dataset function -> Data_preprocessing_unit -> model_train --> CLI
  
# Known Issues and our TODO targets
  * Data loading and processing is time consumming
  * Training on new dataset needs refinement for more optimisation potentially tensorflow based logistic regression for fine grain control and training acceleration through CUDA and gpu services
  * BOW integrated with random forest and text structure based analysis would improve overall performence.

# potential Upgrades
    + We wish to integrate it with more vast dataset , and integrate tensorflow and stack models for improved precissions and performence
    + An preprocessing NLP text engine for advanced analysis of text to get sentiments based trainning and more deeper understanding 
    + Introducing Reinforcement learning where users would help us to improve our product after we deploy it in our own application, and customise it based on their prefrences 

For devdoc - development notes and issues : read dev_doc_library_sheet / development_documentation
Demo_vedio : https://drive.google.com/file/d/1EWvSmJXwTOj6pfpDGIA-dGOIBgHTFGPR/view?usp=sharing
