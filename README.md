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
6.  Job3 : Test your app if it  is working or not.
7.  Job4 : if app is not working , then send email to developer with error messages and redeploy the application after code is being edited by the developer.

Solution:-

Step 1 :- Started minikube from command line by running "minikube start" command and then below is the screen we get

Step 2 :- Now the config file has been created in VM (RHEL8) below is the code of config file created so that we can access kubernetes by our linux system also.

•Now the work of CI/CD tool come into play , Jenkins is installed in my VM and it is running fine on port no. 8080

Job1:-Pulling the github repository , hence all the program files uploaded by Developers will get downloaded into workspace of the job1.

