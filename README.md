# website_hosting_on_kubernetes

Hello reader!!

Here we are going to launch webserver on the top of kubernetes by creating deployment so that there will be zero downtime.
For doing this we gonna use minikube(for kubernetes) and RHEL8 virtual machine.

•Project Description 👉
1. Create Jenkins Server on RHEL 8/7.
3.  Create a job chain of job1, job2, job3 and  job4 using build pipeline plugin in Jenkins .
4.  Job1 : Pull  the Github repo automatically when some developers push repo to Github.
5. Job2 : 
    1. By looking at the code or program file, Jenkins should automatically start the respective language interpreter installed image container to deploy code on top of Kubernetes ( eg. If code is of  PHP, then Jenkins should start the container that has PHP already installed )
    2.  Expose your pod so that testing team could perform the testing on the pod
    3. Make the data to remain persistent ( If server collects some data like logs, other user information )
6.  Job3 : Test your app if it  is working or not.if app is not working , then send email to developer with error messages and redeploy the application after code is being edited by the developer.
7.  Job4 : Test your app again whether it is working or not.

» Solution:-

Step 1 :- Started minikube from command line by running "minikube start" command and then below is the screen we get

![IMG_20200719_235234](https://user-images.githubusercontent.com/60088271/87882116-991d8d80-ca1b-11ea-8be6-c49cfc0fc577.JPG)

Step 2 :- Now the config file has been created in VM (RHEL8) below is the code of config file created so that we can access kubernetes by our linux system also.

![IMG_20200719_234903](https://user-images.githubusercontent.com/60088271/87882138-bd796a00-ca1b-11ea-8dc0-d71f266618ba.JPG)

•Now the work of CI/CD tool come into play , Jenkins is installed in my VM and it is running fine on port no. 8080

![IMG_20200719_235117](https://user-images.githubusercontent.com/60088271/87882165-d2ee9400-ca1b-11ea-8e42-fce0e1ff75e5.JPG)

* Job1:- Pulling the github repository , hence all the program files uploaded by Developers will get downloaded into workspace of the job1.

![IMG_20200719_234747](https://user-images.githubusercontent.com/60088271/87882192-029d9c00-ca1c-11ea-95eb-ae36253505b2.JPG)

![IMG_20200719_234812](https://user-images.githubusercontent.com/60088271/87882195-121ce500-ca1c-11ea-8dff-452b0fd643ab.JPG)

![IMG_20200719_234833](https://user-images.githubusercontent.com/60088271/87882200-1f39d400-ca1c-11ea-8912-d7b6ebfd91f0.JPG)


* Job2 :-
    By looking at the code or program file, Jenkins should automatically start the respective language interpreter installed image container to deploy code on top of Kubernetes ( eg. If code is of  PHP, then Jenkins should start the container that has PHP already installed ), and in the same job I scaled the deployment by creating 3 replicas and then I exposed deployment.
    
   ![IMG_20200719_235102](https://user-images.githubusercontent.com/60088271/87882215-42fd1a00-ca1c-11ea-81ba-73f8fa19104d.JPG)
   
   Below is the code of "copy.py" It is used for getting the pod name from the command of "kubectl get pods".
   
   ![IMG_20200719_235021](https://user-images.githubusercontent.com/60088271/87882256-82c40180-ca1c-11ea-90c8-ffdf8b5d0bbe.JPG)

Below is the ouput of Job2 , here we can see the port no. where our deployment is exposed as here we can see the ouput of "kubectl get all" command.

   ![IMG_20200719_234936](https://user-images.githubusercontent.com/60088271/87882246-7344b880-ca1c-11ea-8b7a-229054bbecb8.JPG)

* Job3 :- Test your app if it  is working or not.if app is not working , then send email to developer with error messages and redeploy the application after code is being edited by the developer.


![IMG_20200719_234848](https://user-images.githubusercontent.com/60088271/87882287-bc950800-ca1c-11ea-85a8-5d05e56ad183.JPG)

* Job4 :- Test the app again.

![IMG_20200719_235041](https://user-images.githubusercontent.com/60088271/87882309-e3533e80-ca1c-11ea-8e32-4876bba30a66.JPG)

Below is the ScreenShot of the running website.

![IMG_20200719_234957](https://user-images.githubusercontent.com/60088271/87882328-fbc35900-ca1c-11ea-8a75-2857ece7563d.JPG)

•OUTPUT of Build Plugin 👉

![IMG_20200719_235139](https://user-images.githubusercontent.com/60088271/87882335-11388300-ca1d-11ea-87ad-3424d60ed744.JPG)

Hence our Task completed✨

  
    



