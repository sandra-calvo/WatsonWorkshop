## Overview

The purpose of this lab is to guide the user in the data science life cycle from raw data to an application with a machine learning model. All this using IBM Cloud tools.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/Tools.png "New flow Text 1")

## Introduction

**IBM Cloud** is a suite of cloud computing services from IBM that offers both platform as a service (PaaS) and infrastructure as a service (IaaS).


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/IBMCloud.png "New flow Text 2")

# Part 1
## Create an application that uses custom ML model


**Attention! The first phase is based to lab made in section lab5 ML. If you have done the Dementia lab earlier, you have to deploy your model to do this lab.**

To deploy your model open your Dementia lab flow from Watson Studio.

You should have these nodes in your canvas.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/userinput.png "New flow Text 60")

To save your model press three dots in Prediction table node and press **Save branch as a model**

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/deployment.png "New flow Text 61")

Name your model and choose your Machine Learning instance. and press **Save**

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/modelname.png "New flow Text 62")

Go to your project asset page and check that your saved model is under Models section.

Open the model by clicking its name and go to deployments page. Press Add Deployment and Name your deployment. Then press save.

Now you can create application for this model.


### Step 10. Create a Node-RED application

**Node-RED** is a visual tool for wiring the internet of things - connecting hardware devices, APIs and online services in a new and interesting way. Node-RED provides a browser-based flow editor that makes it easy to wire together flows using the wide range nodes in the palette. Flows can be then deployed to the runtime in a single-click.

1. In a browser navigate to https://bluemix.net
2.	Select 'LOG IN' then enter your log in information and press 'SIGN IN'.  You should see your dashboard.
3.	Select the 'CATALOG' view.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App1.png "New flow Text 34")

4.	Locate the Node-RED started service and click on it.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App2.png "New flow Text 3")

5.	Enter a name for your application, as shown below (host will automatically be completed). The host name must be unique on IBM Cloud, so please choose a name with your company name or initials to try to make a unique name.  Press 'CREATE'.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App3.png "New flow Text 4")

6.	Your application is now staging and will be up and running in a short while. Click 'OVERVIEW' to see information about your application.
The application will be ready in a couple of minutes. If you want to check the progeress click on the _LOGS_ icon on the left side menu.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App3b.png "New flow Text 5")

*Note: If you are using Lite accounts your application will be in an awake mode. That means that if after 10 days your application has not been used IBM will stop it.*

7.	When fully staged, click on the _Visit app link_, next to the green or half green circle, this launches the Node-RED main page.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App4.png "New flow Text 6")

8.	Configure your Node-RED editor. In this section, you will set up a username and password to protect your flow.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App5.png "New flow Text 7")

9.	Write an username and a password of your choice and click 'Next'. Remember that it does not have to be related to your IBM Cloud ID.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App6.png "New flow Text 8")

#### Your Node-RED flow is all set! Enter your credentials to access the editor.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App8.png "New flow Text 9")

Now click Go to your Node-RED flow editor to open the flow editor.

10.	When using Node-RED we build our apps using this graphical editor interface to wire together the blocks we need. We can simply drag and drop the blocks from the left menu into the workspace in the center of the screen and connect them to create a new flow.

### Step 11: Add new nodes to the Node-RED palette
We are going to add new nodes to the Node-RED palette directly from the Node-RED window. For this lab we need the following nodes:

      - node-red-dashboard
      - node-red-contrib-watson-machine-learning

In the Node-RED window click on the three lines on the top right corner and in the menu, click on the "Manage palette". This will open the node menu where you can add new nodes to your application.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App23.png "New flow Text 10")

You will see the nodes that are installed by default and if you go to the 'install' tab you can search for any node package and add it directly to your app.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App24.png "New flow Text 11")

Search for the dashboard nodes by writing 'dashboard'. This will return multiple node packages, you need to install the package 'node-red-dashboard'. Find it in the search results and click on install.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App25.png "New flow Text 12")

This will prompt a window to confirm the installation. Click on install and wait few minutes, the application may require a restart. Click "Done" to close the left side menu.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App26.png "New flow Text 13")

After few seconds you will see the new nodes in your Node-RED palette.

**Remember** to repeat this process for the Machine Learning nodes: node-red-contrib-watson-machine-learning.

### Step 12: Import the Node-RED application flow
In this section we will build a simple flow to represent the user interface that will interact with our ML model created in Watson Studio.

First we are importing Form node to the canvas. Form represents the user input fields. To import node to canvas find it under from left hand side list under dashboard title.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/formnode.png "New flow Text 35")

Now we have to configure function node. Open the node by double clicking it. Then add following informations to form elements

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/formnodecon.png "New flow Text 39")

You can give what ever names you want to label part, but type must be numeric. and inputs must be input1, input2 and input3. Remember check the required tab.

Then press pencil button next to group dropdown menu.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/groupedit.png "New flow Text 40")

Give name to your group, "Ennuste" is good for this one.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/formgroupname.png "New flow Text 40")

Then press add and done.

Next you must add function node to the canvas. Find node from same list and drag it to canvas and connect that to form node as shown below.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/funktionode.png "New flow Text 36")

Next we have to edit the function node. Open it by clicking and name it to "MLinput" the add code below to code section.

```
msg.payload = {
  "fields":["Ssleepinghours","awakenings","RHR"],
  "values":[[msg.payload.input1,msg.payload.input2,msg.payload.input3]]
}; 

return msg;
```

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/mlinput.png "New flow Text 37")

After we have configured the function node let's add debug node, so we can debug system.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/debugnode.png "New flow Text 38")

Remember to deploy flow time to time to save your work.


Now we have to import the actual Watson Machine Learning Node, you can find this under IBM Watson category. The right on is purple and it is called **WML**. Drag that one to the canvas and connect that to function node.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/wml.png "New flow Text 42")

We are going to configure WML node later in this tutorial.

Next we are adding new function node and new debug node to the flow. Drag those to canvas and connect those to WML node. 


Afterwards your flow should look like this.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/debug2.png "New flow Text 43")

Next we have to configure the new function node. Open it by clicking and name it as MLoutput. Then add code below to the code section.

```
msg.payload = msg.payload.values[0][3]; 

return msg;
```

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/funktio2b.png "New flow Text 44")

Now your flow should look like this. 

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/flow2.png "New flow Text 45")

Now the prediction is done and we have to visualize the results. We are doing it with text and graphical gauge. Since the model don't give the probability, we have only the actual prediction.

Let's first add the text output node. You can find that under Dashboard section.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/textnode.png "New flow Text 46")

Before editing it bring gauge node from same section.

Now your flow should look like this.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/flow3.png "New flow Text 47")

Now let's edit the text node. Make the settings shown below.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/textnodecon.png "New flow Text 48")

Now let's edit Gauge node. Make the settings shown below.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/gaugecon.png "New flow Text 49")

Finaly let's add reset button, so we can reset the dashboard. From dashboard section let's drag button node to the canvas. Then open it and configure as shown below.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/resetcon.png "New flow Text 50")

Now your flow is finished and should look like this.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/flow4.png "New flow Text 51")

Now you have to config the WML node still. To do that follow instructions below.

This flow reads input data from the user and calls the ML model to give a prediction in the UI.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App29.png "New flow Text 16")

You will need to do some editing on the Watson Machine Learning Node.
Go to IBM Cloud, (www.bluemix.net) click on your dashboard and open the Watson Machine Learning service.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App33.png "New flow Text 17")

Click on _Service Credentials_ and _View credentials_. Copy the credentials.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App34.png "New flow Text 18")

Back in Node-REd, double click on the purple node, Watson machine learning node, and click on the pencil to add your credentials.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/App32.png "New flow Text 19")

Add your Username, Password, Host, Instance ID and Access key.

Note that it is also possible to change the looks of your user interface in the dashboard tab.

Deploy your application changes from the **Deploy** button on the top right side of the screeen.

### Step 13. Check your webapp UI!
The dashboard nodes added an UI to our Node-RED application. It also possible to change the looks of your user interface in the dashboard tab.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/webui.png "New flow Text 20")

To access the UI go to:
http://yourAppName.eu-gb.mybluemix.net/ui - UK

Remember that if you are in US, Germany Sydney the addredd will look slightly different:
http://yourAppName.mybluemix.net/ui - US South

http://yourAppName.eu-de.mybluemix.net/ui - Germany

http://yourAppName.au-syd.mybluemix.net/ui - Sydney

**Fantastic! Your web app is ready.**
Now you can interact with the machine learning model you created from the webapp. :+1:

# PART 2
## Connect Watson Assistant with your ML model

### Step 14. Create Watson Assistant service on IBM Cloud
With IBM Watson™ Assistant service you can build a solution that understands natural-language input and uses machine learning to respond to customers in a way that simulates a conversation between humans.

Go to your IBM Cloud account and open the catalog. Look for Watson Assistant service and click on it.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA1.png "New flow Text 21")

Choose the region and space where you want the service to be created. Your organization will be filled by default.
You don't need to change the name if you don't want to, just click on 'Create'.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA2.png "New flow Text 22")

Once the service is created click on 'Launch tool' to access it.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA3.png "New flow Text 23")

Click on Log in with IBM ID and you will automatically access the service. It uses your IBM Cloud ID and password.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA4.png "New flow Text 24")

In the home tab you have videos and tutorials on how to get started building dialoges. Feel free to explore them.
Let's move to the Workspaces tab.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA5.png "New flow Text 25")

### Step 15. Import a workspace
The natural-language processing happens inside a workspace, which is a container for all of the artifacts that define the conversation flow for an application.

You can create a workspace and start from scratch or import an existing conversation.
Let's start by importing a conversation. Download the **bot_conversation.json** file located in the Box folder.

Click on the import icon shown in the image below.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA6.png "New flow Text 26")

When you import a workspace, you can choose to import only the intents and entities, which can be useful if you want to build a new dialog using the same training data. In this case we will import everything.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA7.png "New flow Text 27")

### Step 16. Test your dialog
As you make changes to your dialog, you can test it at any time to see how it responds to input.
1.	From the Dialog tab, click the conversation buble icon.
2.	In the chat panel, type some text and then press Enter.
3.	Check the response to see if the dialog correctly interpreted your input and chose the right response.

The chat window indicates what intents and entities were recognized in the input. In the dialog editor pane, the currently active node is highlighted
Feel free to create new intents for your bot.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA8.png "New flow Text 28")

### Step 17. Get Watson Assistant credentials
Since we will need your Watson Assistant credentials and your workspace ID in the next step, this is a good moment to save them.Go to the deploy tab in the Assistant window. There you will find your workspace ID, username and password. Copy the credentials and save them for later.

![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA9.png "New flow Text 29")

### Step 18. Build a Node-RED flow to connect with Watson Assistant
**Back to Node-RED window**

Copy the content of **ML_bot_UI.json** and import the flow to Node-RED, same way you did in Step 15.
The file is located in the Box folder.

This is the flow we are importing:


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA10.png "New flow Text 30")

Connect the output of the orange node called "ML input" to the input of the purple node from the previous flow.
Once you do connect the dots your flow should look like this:


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA11.png "New flow Text 31")

Double click on the conversation node to edit the node with your own credentials saved in the previous step.
Add your username, passworkd and workspace id and click Done.


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA12.png "New flow Text 32")

Click on the _Deploy_ button to save the changes in your application.

### Step 19. Check the final result!
Go back to the UI and talk with your bot!
You can ask to connect/start the model and the prediction result will be shown in the gauge graph.

Remember, to go back to your web app (in UK region)
http://yourAppName.eu-gb.mybluemix.net/ui - UK


![alt text](https://github.com/LasseHuotari/WatsonWorkshop/blob/master/WatStudLabs/Lab%208%20-%20Application-development/images/WA15.png "New flow Text 33")

At this moment the bot is very basic. It can tell you about IBM Cloud and Watson Studio and can connect with the ML model created in Lab 1.
To connec with the model write: "Start the model".

**Congrats!** You finished the lab. :clap:
Here, take a :lollipop: and enjoy your awesomeness!
