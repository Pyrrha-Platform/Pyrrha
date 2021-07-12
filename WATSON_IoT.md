
## Setting up the IBM Watson IoT Platform
In order for the Pyrrha Device to communicate with the internet, you need to create a device in the IBM Watson IoT Platform. Creating a device allows you to connect your an IoT device (in this case, Pyrrha) to IBM Watson. You are telling IBM Watson to let the device connect to the internet and receive its data.

Follow these steps to connect a device to IBM Watson IoT Platform

1. Create an IBM Cloud account through [this link](https://cloud.ibm.com/registration?cm_sp=Developer-_-cfc2021projects-_-ov78713&eventid=cfc2021projects&lang=en_US&target=https%3A%2F%2Fdeveloper.ibm.com%2Fdwwi%2Fjsp%2Fp%2Fpostregister.jsp%3Feventid%3Dcfc2021projects%26lang%3Den_US). Fill out all the required information and confirm your email address.

2. Follow this link to provision an instance of the [IBM Watson IoT Platform](https://cloud.ibm.com/catalog/services/internet-of-things-platform). Note: you can also find this by [browsing through the catalog](https://cloud.ibm.com/catalog#services).

3. Make sure the Lite plan is selected and click `Create`. You can change the `Service Name` if you want to, but it's not required.

4. After the service provisions, click `Launch`.

5. Click `Add Device`.

6. Enter your `Device Type` and `Device ID`, then click `Next`.

7. Filling out anything in the `Device Information` tab is optional, click `Next`.

8. Leave the field for `Authentication Token` blank, as one will be generated automatically. You can specify your own if you prefer. Click `Next`.

9. Ensure that the `Summary` page looks good, then click Finish.

10. You'll see the authentication token listed, ensure that you do not misplace it, otherwise, you will have to regenerate a new token.

11. Open `PapaDuckExample.ino` and replace `ORG`, `DEVICE_ID`, `DEVICE_TYPE`, and `TOKEN` with the information from the summary screen. Make sure you also have the correct WiFi SSID and password filled out in that file as well. After you flash the duck with this information, you'll see data flowing through the IBM Watson IoT Platform.
