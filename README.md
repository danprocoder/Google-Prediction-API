# Google-Prediction-API
Implemented Google-prediction-api based model with python application client

The Dataset I used is from Car evaluation domain. This dataset has 6 features namely:
buying:   vhigh, high, med, low.
maint:    vhigh, high, med, low.
doors:    2, 3, 4, 5more.
persons:  2, 4, more.
lug_boot: small, med, big.
safety:   low, med, high.

and target values consists of 4 values,
unacc, acc, good, vgood

Steps I took to work on these model:

1) Created an account on Google Developers console, downloaded the dataset in .csv format, its a comma separated fileset.
2) Created a new project, project_id is datarobot-12345, project_name is DataRobot.
3) On cloud storage, we have storage browser where we can upload our dataset.
4) Create credentials in order to be secure, it will create client_id, email_id and a private_key.
5) In order to train our model, go to Google API's explorer, look for Google-prediction-api, and enable the API to get the trained model.
6) We have different functionalities under Prediction API V1.6, to train we will use predictions.trainmodels.insert() function.
7) It will ask for a model_id, project_id, instances, storagedatalocation, fill all the details appropriately.
8) Once you execute, it will start executing and You will get a message 200 OK if all is well, else you will get 404 bad requests error.
9) To see if our model is completely trained, use the prediction.trainedmodels.get function, it will show the current status, once it's trained, it will show a response with the classification accuracy and many other details.
10) Now, on our trained model, we can use prediction.trainedmodels.predict function to see the prediction for a given input instance.
11) For prediction, I have written a python script, first installing google-api-python-client library using 
pip install --upgrade google-api-python-client command.
12) If in case you get some proxy errors, follow steps below:
install pip 1.2.1 package,tar it, and then use python install setup.py. It will install package without any proxy issues.
13) Once we are setup with client libraries, we can write a script with project_id, client_id, Auth2client credentials , and using prediction fucntions from api.
14) Output will be probability of being classified in all class labels, and the target value will be class label with highest probability achieved.
