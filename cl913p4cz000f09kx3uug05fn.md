# An alternative method to view your Heroku Database tables

In this article, I will tell you about an alternative method to view your database from the Heroku platform. Check the tables of your Heroku Postgres Database used by your website or an application.

When I deployed my application on Heroku, I was curious about checking tables created by Django and Models. But was unable to check it as Heroku provides no specific functionality to view what's inside a database. After exploring, I found this application that helped me go through my database tables. 

Following are the quick steps to get started,

## Download a small application
Firstly download the application file respective to your machine from [this link](https://github.com/sosedoff/pgweb/releases/tag/v0.11.12) and extract the zip file.

## Run the application 
Run this application and this will start one localhost session at ```https://localhost:8081``` or any other port.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665299072771/0pQoLCRboo.png align="left")

## Visit localhost
After visiting the respective localhost link, you will see the following page.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665299440355/cw3roJc3i.png align="left")
You will get an option to connect with your database using a standard URI, Database credentials or SSH.

## Get Database credentials
Visit your application dashboard on Heroku, go to the Resources tab and click on Heroku Postgres.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665299843338/wio-gVlF2.png align="left")
On the Datastores page, go to the Settings tab and click on View Credentials.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665300006493/XI-fW0Tlc.png align="left")
You will get the Hostname, Database, User, Port, Password, URI and Heroku CLI information.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665300312234/v3heOvwTB.png align="left")


## Connect to Database
You can use these credentials to connect to your database. For this article, I will be using the URI method. Copy the URI from the Heroku dashboard, paste it into the **Scheme** tab and click on connect button.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665300653393/HOVZgq9hX.png align="left")
This will open your database and the tables in it.
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1665300861531/I39TN74_D.png align="left")
You can get a lot of information about your databases such as tables, rows and table structure. Find out now yourself by following the steps above.

Thank you for reading this article. You can also subscribe to my newsletter to receive my articles straight to your inbox.

> Be better than Yesterday's you!







