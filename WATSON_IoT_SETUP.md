## Setting up the IBM Watson IoT Platform

In order for the Pyrrha Device to communicate with the internet, you need to create a device in the IBM Watson IoT Platform. Creating a device allows you to connect your an IoT device (in this case, Pyrrha) to IBM Watson. You are telling IBM Watson to let the device connect to the internet and receive its data.

## Get started

- [Setting up the IBM Watson IoT Platform](#setting-up-the-ibm-watson-iot-platform)
- [Get started](#get-started)
- [Create IBM IoT Service](#create-ibm-iot-service)
- [Connect a Pyrrha device to IBM Watson IoT Platform](#connect-a-pyrrha-device-to-ibm-watson-iot-platform)
- [Connect an application to IBM Watson IoT Platform](#connect-an-application-to-ibm-watson-iot-platform)
- [Obtain organization ID from the IoT platform](#obtain-organization-id-from-the-iot-platform)

## Create IBM IoT Service

Follow these steps to create an IBM IoT service

1. Create an IBM Cloud account through [this link](https://cloud.ibm.com/registration?cm_sp=Developer-_-cfc2021projects-_-ov78713&eventid=cfc2021projects&lang=en_US&target=https%3A%2F%2Fdeveloper.ibm.com%2Fdwwi%2Fjsp%2Fp%2Fpostregister.jsp%3Feventid%3Dcfc2021projects%26lang%3Den_US). Fill out all the required information and confirm your email address.

2. Follow this link to provision an instance of the [IBM Watson IoT Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform). Note: you can also find this by [browsing through the catalog](https://cloud.ibm.com/catalog#services).

3. Make sure the Lite plan is selected and click `Create`. You can change the `Service Name` if you want to, but it's not required.
   <img width="1920" alt="step3" src="https://user-images.githubusercontent.com/84807697/125334090-f9869880-e318-11eb-8d94-db51fcf44dd8.png">

4. After the service provisions, click `Launch`.
   <img width="1920" alt="step4" src="https://user-images.githubusercontent.com/84807697/125334223-1e7b0b80-e319-11eb-9181-20ad5e935690.png">

---
## Connect a Pyrrha device to IBM Watson IoT Platform

Follow these steps to connect a device to IBM Watson IoT Platform

1. Click on `Devices` located on the left toolbar, and then select `Add Device`.
   <img width="1920" alt="step5" src="https://user-images.githubusercontent.com/84807697/125334343-45394200-e319-11eb-9c5e-b916cad4a017.png">

2. Enter your `Device Type` and `Device ID`, then click `Next`.
   <img width="1920" alt="step6" src="https://user-images.githubusercontent.com/84807697/125337488-0f965800-e31d-11eb-8ec9-b44fb48716e0.png">

3. Filling out anything in the `Device Information` tab is optional, click `Next`.
   <img width="1920" alt="step7" src="https://user-images.githubusercontent.com/84807697/125334411-597d3f00-e319-11eb-960d-78a5fe0131a6.png">

4. Leave the field for `Authentication Token` blank, as one will be generated automatically. You can specify your own if you prefer. Click `Next`.
   <img width="1920" alt="step8" src="https://user-images.githubusercontent.com/84807697/125334642-9c3f1700-e319-11eb-9f8f-73086e338a8f.png">

5. Ensure that the `Summary` page looks good, then click `Finish`.
   <img width="1920" alt="step9" src="https://user-images.githubusercontent.com/84807697/125337417-f9889780-e31c-11eb-8376-e98671f693e2.png">

6. You'll see the authentication token listed, ensure that you do not misplace it, otherwise, you will have to regenerate a new token.
   <img width="1920" alt="step10" src="https://user-images.githubusercontent.com/84807697/125337458-060cf000-e31d-11eb-8bce-0f306e0edbea.png">

---
## Connect an application to IBM Watson IoT Platform

Follow these steps to connect an application to IBM Watson IoT Platform.

1. Click on `Apps` located on the left toolbar, and then select `Generate API Key`.
   <img width="1920" alt="step5b" src="https://user-images.githubusercontent.com/84807697/125509112-5267993b-9230-4287-8b64-4af0ef7d5bcb.png">

2. Write a description and once you are done click `Next`, Keep `API Key Expires` off.
   <img width="1920" alt="step6b" src="https://user-images.githubusercontent.com/84807697/125509147-218179ab-4fbb-4d47-9155-1e60ebd8218f.png">

3. The role should be `Visualization Application`, if not click on the toolbar and select it. Then click `Generate Key`.
   <img width="1920" alt="step7b" src="https://user-images.githubusercontent.com/84807697/125509187-847f0b03-18aa-4a8a-bf46-1802d960aac6.png">

4. The `API Key` is your `IOT_USERNAME` and the `Authentication Token` is your `IOT_PASSWORD`.
   <img width="1920" alt="step8b" src="https://user-images.githubusercontent.com/84807697/125515096-648cb1f7-e09d-414d-aa1e-8a3b990a8b74.png">

5. In the `.env` file , fill in the information of the `IOT_USERNAME` & `IOT_PASSWORD` from step 8^.
   <img width="1920" alt="step9b" src="https://user-images.githubusercontent.com/84807697/125515127-520c9d85-ef19-41f1-b790-be169ec39319.png">

---
## Obtain organization ID from the IoT platform

Follow these steps to obtain your organization ID to use in environment files:
1. Log into your IBM Cloud account.
2. Look for the IoT service under resources and launch the IoT platform.
   ![](img/iot-orgid-launch.png)
3. Hover over the left menu to open it and then open `Settings`
    ![](img/iot-orgid-settings.png)
4. You can find your organization ID under `Identity`
   ![](img/iot-orgid-orgid.png)
