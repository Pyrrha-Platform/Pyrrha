
## Setting up the IBM Watson IoT Platform
In order for the Pyrrha Device to communicate with the internet, you need to create a device in the IBM Watson IoT Platform. Creating a device allows you to connect your an IoT device (in this case, Pyrrha) to IBM Watson. You are telling IBM Watson to let the device connect to the internet and receive its data.

## Get started
- [Connect a Pyrrha device](#connect-a-pyrrha-device-to-ibm-watson-iot-platform)
- [Connect an application](#connect-an-application-to-ibm-watson-iot-platform)

## Connect a Pyrrha device to IBM Watson IoT Platform
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
<img width="1920" alt="step6" src="https://user-images.githubusercontent.com/84807697/125337488-0f965800-e31d-11eb-8ec9-b44fb48716e0.png">

7. Filling out anything in the `Device Information` tab is optional, click `Next`.
<img width="1920" alt="step7" src="https://user-images.githubusercontent.com/84807697/125334411-597d3f00-e319-11eb-960d-78a5fe0131a6.png">

8. Leave the field for `Authentication Token` blank, as one will be generated automatically. You can specify your own if you prefer. Click `Next`.
<img width="1920" alt="step8" src="https://user-images.githubusercontent.com/84807697/125334642-9c3f1700-e319-11eb-9f8f-73086e338a8f.png">

9. Ensure that the `Summary` page looks good, then click `Finish`.
<img width="1920" alt="step9" src="https://user-images.githubusercontent.com/84807697/125337417-f9889780-e31c-11eb-8376-e98671f693e2.png">

10. You'll see the authentication token listed, ensure that you do not misplace it, otherwise, you will have to regenerate a new token.
<img width="1920" alt="step10" src="https://user-images.githubusercontent.com/84807697/125337458-060cf000-e31d-11eb-8bce-0f306e0edbea.png">

## Connect an application to IBM Watson IoT Platform
Follow these steps to connect an application to IBM Watson IoT Platform. 

1. Create an IBM Cloud account through [this link](https://cloud.ibm.com/registration?cm_sp=Developer-_-cfc2021projects-_-ov78713&eventid=cfc2021projects&lang=en_US&target=https%3A%2F%2Fdeveloper.ibm.com%2Fdwwi%2Fjsp%2Fp%2Fpostregister.jsp%3Feventid%3Dcfc2021projects%26lang%3Den_US). Fill out all the required information and confirm your email address.

2. Follow this link to provision an instance of the [IBM Watson IoT Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform). Note: you can also find this by [browsing through the catalog](https://cloud.ibm.com/catalog#services).

3. Make sure the Lite plan is selected and click `Create`. You can change the `Service Name` if you want to, but it's not required.
<img width="1920" alt="step3" src="https://user-images.githubusercontent.com/84807697/125334090-f9869880-e318-11eb-8d94-db51fcf44dd8.png">

4. After the service provisions, click `Launch`.
<img width="1920" alt="step4" src="https://user-images.githubusercontent.com/84807697/125334223-1e7b0b80-e319-11eb-9181-20ad5e935690.png">

5. Click on `Apps` located on the left toolbar, and then select `Generate API Key`.
<img width="1920" alt="step5b" src="https://user-images.githubusercontent.com/84807697/125509112-5267993b-9230-4287-8b64-4af0ef7d5bcb.png">

6. Write a description and once you are done click `Next`, Keep `API Key Expires` off.
<img width="1920" alt="step6b" src="https://user-images.githubusercontent.com/84807697/125509147-218179ab-4fbb-4d47-9155-1e60ebd8218f.png">

7. The role should be `Visualization Application`, if not click on the toolbar and select it. Then click `Generate Key`.
<img width="1920" alt="step7b" src="https://user-images.githubusercontent.com/84807697/125509187-847f0b03-18aa-4a8a-bf46-1802d960aac6.png">

8. The `API Key` is your `IOT_USERNAME` and the `Authentication Token` is your `IOT_PASSWORD`.
<img width="1920" alt="step8b" src="https://user-images.githubusercontent.com/84807697/125511463-f425c7c5-c559-4a50-b334-2acc10ebdad1.png">

9. In the `.env` file , fill in the information of the `IOT_USERNAME` & `IOT_PASSWORD` from step 8^.
<img width="1920" alt="step9b" src="https://user-images.githubusercontent.com/84807697/125511516-26b5b4da-f825-41fa-bb24-f4cf330c380f.png">

10. In the terminal, under the application directory (for example : `/user/Pyrrha-MQTT-Client/`) run `npm start`.
