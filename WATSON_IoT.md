
## Setting up the IBM Watson IoT Platform
In order for the Pyrrha Device to communicate with the internet, you need to create a device in the IBM Watson IoT Platform. Creating a device allows you to connect your an IoT device (in this case, Pyrrha) to IBM Watson. You are telling IBM Watson to let the device connect to the internet and receive its data.

Follow these steps to connect a device to IBM Watson IoT Platform

1. Create an IBM Cloud account through [this link](https://cloud.ibm.com/registration?cm_sp=Developer-_-cfc2021projects-_-ov78713&eventid=cfc2021projects&lang=en_US&target=https%3A%2F%2Fdeveloper.ibm.com%2Fdwwi%2Fjsp%2Fp%2Fpostregister.jsp%3Feventid%3Dcfc2021projects%26lang%3Den_US). Fill out all the required information and confirm your email address.

2. Follow this link to provision an instance of the [IBM Watson IoT Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform). Note: you can also find this by [browsing through the catalog](https://cloud.ibm.com/catalog#services).

3. Make sure the Lite plan is selected and click `Create`. You can change the `Service Name` if you want to, but it's not required.
<img width="1920" alt="step3" src="https://user-images.githubusercontent.com/84807697/125334090-f9869880-e318-11eb-8d94-db51fcf44dd8.png">

4. After the service provisions, click `Launch`.
<img width="1920" alt="step4" src="https://user-images.githubusercontent.com/84807697/125334223-1e7b0b80-e319-11eb-9181-20ad5e935690.png">

5. Click `Add Device`.
<img width="1920" alt="step5" src="https://user-images.githubusercontent.com/84807697/125334343-45394200-e319-11eb-9c5e-b916cad4a017.png">

6. Enter your `Device Type` and `Device ID`, then click `Next`.

7. Filling out anything in the `Device Information` tab is optional, click `Next`.
<img width="1920" alt="step7" src="https://user-images.githubusercontent.com/84807697/125334411-597d3f00-e319-11eb-960d-78a5fe0131a6.png">

8. Leave the field for `Authentication Token` blank, as one will be generated automatically. You can specify your own if you prefer. Click `Next`.
<img width="1920" alt="step8" src="https://user-images.githubusercontent.com/84807697/125334642-9c3f1700-e319-11eb-9f8f-73086e338a8f.png">

9. Ensure that the `Summary` page looks good, then click Finish.

10. You'll see the authentication token listed, ensure that you do not misplace it, otherwise, you will have to regenerate a new token.

