# MLOPS TASK -2
![This is the Flow of Pipeline]()

# Introduction

In this task we have to integrate Jenkins, Github, Machine Learning, Deep Learning  and Docker.
This project will help in auto tweaking of the model for finding the best accuracy of the model by changing the hyper-parameters such as adding layers, changing pool size, changing filter size, number of epochs, etc.

In this Jenkins will help us do our job easy. We don’t need to run the model again and again Jenkins will do for us.
In this we have use our own docker image for the python environment.
 
# Task description

1.	Create container image that’s has Python3 and Keras or numpy  installed  using dockerfile 

2.	When we launch this image, it should automatically starts train the model in the container.

3.	Create a job chain of job1, job2, job3, job4 and job5 using build pipeline plugin in Jenkins .

4.	 Job1 : Pull  the Github repo automatically when some developers push repo to Github.

5.	 Job2 : By looking at the code or program file, Jenkins should automatically start the respective machine learning software installed interpreter install image container to deploy code  and start training( eg. If code uses CNN, then Jenkins should start the container that has already installed all the softwares required for the cnn processing).

6.	Job3 : Train your model and predict accuracy or metrics.

7.	Job4 : if metrics accuracy is less than 80%  , then tweak the machine learning model architecture.

8.	Job5: Retrain the model or notify that the best model is being created.

9.	Create One extra job job6 for monitor : If container where app is running. fails due to any reason then this job should    automatically start the container again from where the last trained model left.


# Detailed view of the Task

Step-1: Creating the image
First  step is to create the image which will help us launching the environment for running our code.
We have to install all the dependencies and Libraries required for the model.
The DockerFile will look like this:
And finally our image is ready to use.

Step-2: Creating the python code
We have to write the python code for CNN model or any model you want to predict the accuracy.
The model will predict the accuracy and the accuracy will be stored in a file and the model also saved in a file.
With the help of the accuracy we will decide whether to tweak and retrain the model or not.
The code you can get from Github URL:

Step-3: Creating the Job 1
In first job we will configure it with the github repository URL.
And set the next job with job 2 also set the poll scm for checking for the code and if some changes occur in code it will download the code and save it the workspace of Jenkins.
And will trigger the job 2 after downloading the code.

Step-4: Creating the Job 2
In Job 2 we will copy the downloaded code into the local directory where we store our code inside redhat.
The code will be deployed using the image we created and will start training.
And will trigger the job 3 after training  the code.

Step-5: Creating the Job 3
In job 3 the model will be trained and will predict the accuracy of the model.
And will trigger the job 4 after successful prediction.

Step-6: Creating the Job 4
In job 4 we will check for the accuracy and if the accuracy will be less than the required accuracy then tweak the model and save it and launch again.
And trigger the job 5 after tweaking.

Step-7: Creating the Job 5
In job 5 we will retrain the updated  model and notify the developer using the email when the best accuracy has been found .

Step-8: Creating the Job 6 
Job 6 will be triggered if the job 3 or job 5 fails due to any reason and this job will relaunch the container and  deploy the code and start training the model from where it left.

After completing all the steps we will get the perfect accuracy without any delay and running the code again and again manually.

This will help in the creation of more efficient  machine learning model in less time with perfect accuracy .

I would like to Thank my mentor Vimal Daga Sir for giving us such challenging tasks and helping us getting the right knowledge and and use of the technology in this ever changing world. 
