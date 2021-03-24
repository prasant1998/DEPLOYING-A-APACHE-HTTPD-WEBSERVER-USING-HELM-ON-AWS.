# DEPLOYING-A-APACHE-HTTPD-WEBSERVER-USING-HELM-ON-AWS.

![1](https://user-images.githubusercontent.com/67523396/112361263-37739880-8cf9-11eb-98c2-7f8c30f991d3.jpeg)



Let’s begin by understanding ,




What is Helm and its uses ?

In simple terms, Helm is a package manager for Kubernetes. Helm is the K8s equivalent of yum or apt. Helm deploys charts, which you can think of as a packaged application.

Charts is a collection of all your versioned, pre-configured application resources which can be deployed as one unit.

Templates are Kubernetes manifest files that describe the resources you want to have on the cluster. Helm uses the Go templating engine by default. Most charts include a file called values.

![2](https://user-images.githubusercontent.com/67523396/112361266-38a4c580-8cf9-11eb-99dd-1a857ebf741d.jpeg)



In this practical ,I have used the values file and would be explaining at last.

Now by a short and crisp description, We know helm is like a package manager for Kubernetes , So I need a cluster to perform helm in action .

So here I used a cluster of Kubernetes with 1 master node and 2 slave node which I launched on top of the AWS .

![3](https://user-images.githubusercontent.com/67523396/112361269-38a4c580-8cf9-11eb-83a9-effcfc371fb2.jpeg)


Let’s get started now …

Firstly I installed helm .

In a helm deployed application, list provides the detail of an application current releases .

As I have not deployed any application yet :

Command Used :

helm list

![4](https://user-images.githubusercontent.com/67523396/112361274-393d5c00-8cf9-11eb-969d-eb8ab43de562.jpeg)


Second, created a directory named my-chart1 in which I stored Chart yaml file , templates directory and also if required values yaml file, So that it could be easier to make changes if required .

Commands Used :

mkdir /my-chart1

Now, I created Chart.yaml file . Always remember Chart “C” should be in captial as helm only reads the directory which has Chart.yaml file .

![5](https://user-images.githubusercontent.com/67523396/112361280-39d5f280-8cf9-11eb-8906-44a884be3c32.jpeg)




There are many options We can use in Chart yaml file below are some of them or Click here .

![6](https://user-images.githubusercontent.com/67523396/112361284-39d5f280-8cf9-11eb-9713-bd2110dd068a.jpeg)


To make it easier to understand. Think about folder I created is like a package folder in which Charts.yaml file is compulsory .

![7](https://user-images.githubusercontent.com/67523396/112361285-3a6e8900-8cf9-11eb-8e65-702918ab74b5.jpeg)


Now in my Templates directory … As it is a Kubernetes manifest files that describe the resources we want to have on the cluster .As my requirement is to launch a pod with httpd webserver and then expose the pod which has been launched .I created two yaml file one for launching httpd server and another for exposing that server.

One more requirement which comes to my mind is ,We can launch a pod with wordpress then expose the pod and one more pod for the sql database to run at backend .So ,We can create three yaml file one for launching wordpress server second for exposing that server and the third one for sql to launch .

Like this we can make out many used cases very easily .

![8](https://user-images.githubusercontent.com/67523396/112361287-3a6e8900-8cf9-11eb-88c0-d08d49453f27.jpeg)
![9](https://user-images.githubusercontent.com/67523396/112361291-3b071f80-8cf9-11eb-908e-dbd084caeb65.jpeg)
![10](https://user-images.githubusercontent.com/67523396/112361293-3b9fb600-8cf9-11eb-9953-723075e782ec.jpeg)
![11](https://user-images.githubusercontent.com/67523396/112361294-3b9fb600-8cf9-11eb-9a2d-46efe3841819.jpeg)





We can see by one command the entire environment has been launched like, we click a package manager and the whole thing is launched .

Command Used :

helm install <name of the app> <name of the workspace>
  
 ![12](https://user-images.githubusercontent.com/67523396/112361295-3c384c80-8cf9-11eb-92b1-f7d7066dcd5d.jpeg)


Installing the env in one go

I can confirm that my service is exposed by looking below:

Commands Used :

kubectl get services

kubectl get nodes

![13](https://user-images.githubusercontent.com/67523396/112361297-3c384c80-8cf9-11eb-8028-e22e7c431101.jpeg)




![14](https://user-images.githubusercontent.com/67523396/112361299-3cd0e300-8cf9-11eb-9619-804b3079cfbe.jpeg)

![20](https://user-images.githubusercontent.com/67523396/112361309-3f333d00-8cf9-11eb-8d70-345b8815f7e6.jpeg)


Helm is a very important and beneficial tool which now top industries also use . It reduces time of setup the same environment again and again .

Command Used :

helm list

![15](https://user-images.githubusercontent.com/67523396/112361302-3d697980-8cf9-11eb-86c0-0d156037d686.jpeg)


I can confirm my httpd web Server is exposed .

![16](https://user-images.githubusercontent.com/67523396/112361304-3d697980-8cf9-11eb-86ba-5c2c1669e360.png)


In the world of automation ,We always need to change the values every now and then .

What can we do to overcome this problem ?

I can create a values.yaml file in which I stored all the values like we do in programming language , create a variable and a value to it . Now this process makes more simpler for the non technical guy to manage rather than do changes on the main yaml file .

![17](https://user-images.githubusercontent.com/67523396/112361305-3e021000-8cf9-11eb-911a-39bbcffd68ad.jpeg)
![18](https://user-images.githubusercontent.com/67523396/112361307-3e021000-8cf9-11eb-98c6-df0afd869d97.jpeg)
![19](https://user-images.githubusercontent.com/67523396/112361308-3e9aa680-8cf9-11eb-8393-b32b48d97db1.jpeg)


The simplest way to manage things .

Open for any query and Suggestions

Thankyou




