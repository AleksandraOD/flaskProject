# Predicting price of realty

The steps of this project are:
* EDA and vizualization of data
* Creating a price prediction model
* Creating web service that predict realty price with our model
* Run service using docker container

## Data
For this project I use data from logs of Yandex.Realty
Our raw dataset contains **429187 records**, but it will be limited by location. For this project we will only use data about realty in ST.Petersburg. There are **156054 records** about realty in St.Petersburg.

The data has following information: 
![alt text](https://github.com/AleksandraOD/flaskProjectFinal/blob/main/Снимок%20экрана%202023-06-10%20в%2007.30.42.png)
The correlation betwee some of the parameters:
![alt text](https://github.com/AleksandraOD/flaskProjectFinal/blob/main/heatmap.png)
Categorical parameters:
![alt text](https://github.com/AleksandraOD/flaskProjectFinal/blob/main/Categorical%20data.png)

For further steps I preprocessed data by removing non-valid values and dropped irrelevant parameters.

## Model

In this project i tried several models (Random forest, Linear regression and LTSM). LSTM works best, but web service service random forest, because I didn't have time to replace model file))))))

The parameters are rooms, area, open plan and renovation.
	
* How to install instructions and run your app with virtual environment
	
## Information about Dockerfile
This Dockerfile is used to build a Docker image for a price predictor application. Here is a breakdown of the instructions:

* Specifies the base image as Ubuntu 20.04.
* Sets the author/maintainer information for the image.
* Updates the package repository within the image.
* Copies the contents of the current directory into the /opt/price_predictor directory of the image.
* Sets the working directory to /opt/price_predictor within the image.
* Installs Python 3 and pip package manager.
* Installs the dependencies listed in the requirements.txt file.
* Specifies the command to be executed when a container based on this image is run. In this case, it runs the app.py file using Python 3

To build the Docker image, navigate to the directory containing the Dockerfile and run the docker build command. For example:

```docker build -t price-predictor```

This will create a Docker image with the tag price-predictor. To run a container based on this image, use the docker run command:
```docker run --network host -d <container name>```


	
* How to open the port in your remote VM
	
## How to run app using docker and which port it uses


