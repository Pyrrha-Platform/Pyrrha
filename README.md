# Pyrrha

[![License](https://img.shields.io/badge/License-Apache2-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0) [![Slack](https://img.shields.io/static/v1?label=Slack&message=%23prometeo-pyrrha&color=blue)](https://callforcode.org/slack)

[Prometeo Solutions S.L.](https://prometeoplatform.com/) created **_Prometeo_** as a [Call for Code submission](https://developer.ibm.com/callforcode/solutions/prometeo/) that won the top prize in the Global Challenge. In 2021, **_Pyrrha_** was contributed to the Linux Foundation as the open source core of Prometeo in order share the technology and provide a way for others to improve it for the benefit of all.

[The Pyrrha mission](Pyrrha-Technical-Charter-July-2021.pdf) is to help protect firefighters from the immediate and long-term health impacts from the smoke and toxins they inhale by providing real-time information on exposure and by calculating longer-term averages. The project uses custom sensors, smartphone and smartwatch apps, data science, and a dashboard to provide decision-making insight and information.

Improved by field tests in the Catalonia region of Spain and through the support of IBM Service Corps volunteers, our hope is that Pyrrha can also provide a powerful solution to assist wildlands firefighting teams around the world in their battle against more frequent and more devastating wildfires and bushfires.

## Get started

- [Get started](#get-started)
- [Pyrrha v1 (Prometeo v4)](#pyrrha-v1-prometeo-v4)
- [The story](#the-story)
- [Solution at a glance](#solution-at-a-glance)
- [Pyrrha projects](#pyrrha-projects)
- [Built with](#built-with)
- [Quick start](#quick-start)
- [Get involved](#get-involved)
- [Original Prometeo team](#original-prometeo-team)
- [Prometeo Platform S.L. team](#prometeo-platform-sl-team)
- [IBM Call for Code team](#ibm-call-for-code-team)
- [IBM Service Corps team](#ibm-service-corps-team)
- [Technical Steering Committee](#technical-steering-committee)
  - [TSC meetings](#tsc-meetings)
  - [Townhall meeetings](#townhall-meeetings)
- [License](#license)

## Pyrrha v1 (Prometeo v4)

The first version of the Pyrrha project has been released as a [Call for Code® with The Linux Foundation](https://www.linuxfoundation.org/projects/call-for-code/) project. Pyrrha will carry on as a separate name distinct from the Prometeo Solutions trademark, the [flame-colored haired daughter-in-law of Prometheus in Greek mythology](https://www.greekmythology.com/Myths/Mortals/Pyrrha/pyrrha.html).

## The story

Watch this video to learn about the Pyrrha solution based on Prometeo's original Call for Code 2019 winning application:

[![Story-Video](https://user-images.githubusercontent.com/84807697/120705678-21671e80-c486-11eb-8e6c-888dc98fab23.png)](https://www.youtube.com/watch?v=vOgCOoy_Bx0)

## Solution at a glance

![prometeo:pyrrha diagram](https://user-images.githubusercontent.com/3187457/122242264-08903d00-ce78-11eb-944f-804ba4dc683d.png)

1. The firefighter logs into the ruggedized Samsung smartphone via IBM App ID. Devices are paired through Bluetooth.
2. The device sensors capture toxin levels. The device sends stored readings to the phone at regular intervals.
3. The mobile application relays data to the IBM IoT platform.
4. The MQTT client service listens for incoming messages from the IBM IoT platform.
5. The MQTT client stores the data in the MariaDB relational database.
6. The MQTT client sends the data to the WebSocket server.
7. The Rules-Decision service wakes up every minute to calculate the 10 mins, 30 mins, 60 mins, 4 hours, and 8 hours time-weighted averages for each gas.
8. The dashboard queries the database to show the historical data.
9. The dashboard connects to the WebSocket Server to show live data and alerts the user if the levels go above certain pre-determined thresholds.
10. The command center can view the dashboard using the web browser on a laptop or tablet.
11. The mobile application regularly requests status from the Rules-Decision service and emits the result via device LED and Samsung phone/watch vibrations.

## Pyrrha projects

| Name                                                                                             | What it does                                                                                       |
| ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------- |
| [Pyrrha](https://github.com/Call-for-Code/Pyrrha-Platform/Pyrrha)                                | This repository, the main landing page for learning project details.                               |
| [Dashboard](https://github.com/Pyrrha-Platform/Pyrrha-Dashboard)                                 | The Carbon and React based dashboard that shows real-time readings and long-term averages.         |
| [Database](https://github.com/Pyrrha-Platform/Pyrrha-Database)                                   | The MariaDB database where real-time readings are stored and along with calculated averages.       |
| [Deployment-Configurations](https://github.com/Pyrrha-Platform/Pyrrha-Deployment-Configurations) | Various GitHub Actions, Helm Charts, and other deployment assets and configuration files.          |
| [Firmware](https://github.com/Pyrrha-Platform/Pyrrha-Firmware)                                   | The Arduino based sketch that connects the device to Bluetooth and stores sensor data.             |
| [Hardware](https://github.com/Pyrrha-Platform/Pyrrha-Hardware)                                   | The Arduino microcontroller, battery, and sensor configurations. Moving towards PCB.               |
| [Mobile-App](https://github.com/Pyrrha-Platform/Pyrrha-Mobile-App)                               | The Android Java application that targets Samsung smartphones. Relays sensor data from the device. |
| [MQTT-Client](https://github.com/Pyrrha-Platform/Pyrrha-MQTT-Client)                             | Consumes MQTT messages and stores them in the database for persistence and relays over WebSocket.  |
| [Rules-Decision](https://github.com/Pyrrha-Platform/Pyrrha-Rules-Decision)                       | Analyzes the raw sensor readings and performs calculations to determine exposure over time.        |
| [Sensor-Simulator](https://github.com/Pyrrha-Platform/Pyrrha-Sensor-Simulator)                   | Generates sample data that can simulate readings in the absense of a physical device.              |
| [Watch-App](https://github.com/Pyrrha-Platform/Pyrrha-Watch-App)                                 | The Tizen Web App for Samsung Galaxy smartwatches that can display readings and vibrate alerts.    |
| [Website](https://github.com/Pyrrha-Platform/Pyrrha-Website)                                     | The Carbon and React based single page application for the pyrrha-platform.org site.               |
| [WebSocket-Server](https://github.com/Pyrrha-Platform/Pyrrha-WebSocket-Server)                   | Relays messages in real time to the dashboard which can be monitored by the control center.        |

## Built with

- [IBM IoT Platform](https://www.ibm.com/cloud/internet-of-things)
- [MariaDB](https://mariadb.org/)
- [Express.js](https://expressjs.com/)
- [React.js](https://reactjs.org/)
- [Flask](https://palletsprojects.com/p/flask/)
- [Pandas](https://pandas.pydata.org/)
- [IBM App ID](https://www.ibm.com/cloud/app-id?lnk=STW_US_STESCH&lnk2=learn_CloudAppID&pexp=DEF&psrc=NONE&mhsrc=ibmsearch_a&mhq=app%20id%20ibm%20cloud)
- [IBM Cloud Kubernetes Service](https://www.ibm.com/cloud/kubernetes-service)

## Quick start

The Pyrrha project consists of multiple microservices running in parallel. We have created a Docker Compose configuration to help you get started with a development environment. Docker Compose is a tool that enables running multiple containers on the same host using a lightweight configuration. The Compose file defines all the services along with the dependencies in the correct order. You can bring up the whole environment by using a single `docker-compose up` command. Follow the instructions in the [DOCKER_COMPOSE.md](https://github.com/Pyrrha-Platform/Pyrrha-Deployment-Configurations/blob/main/DOCKER_COMPOSE.md) file to develop Pyrrha.

## Get involved

Please read [GET_INVOLVED.md](GET_INVOLVED.md) to understand how you can contribute to the Pyrrha Project.

We use [Slack in the Call for Code workspace](https://callforcode.org/slack) #prometeo-pyrrha channel for discussion.

## Original Prometeo team

| Name                           | Title                | GitHub                                 | Slack                  |
| ------------------------------ | -------------------- | -------------------------------------- | ---------------------- |
| Marco Emilio Rodriguez Serrano | Data scientist       | [Marco](https://github.com/mrodrise)   | @marco.rodriguez.serra |
| Salome Valero Cumplido         | PhD engineer         | [Salome](https://github.com/svaleroc)  | @salome.valero         |
| Josep Ràfols                   | Full stack developer | [Josep](https://github.com/joraco-dev) | @joraco                |
| Joan Herrera                   | Firefighter          | ---                                    | ---                    |
| Vicenç Ferrés                  | Nurse/EMT            | ---                                    | ---                    |

## Prometeo Platform S.L. team

| Name                           | Title | Github                                | Slack                  |
| ------------------------------ | ----- | ------------------------------------- | ---------------------- |
| Salome Valero Cumplido         | CEO   | [Salome](https://github.com/svaleroc) | @salome.valero         |
| Marco Emilio Rodriguez Serrano | CTO   | [Marco](https://github.com/mrodrise)  | @marco.rodriguez.serra |
| Joan Herrera                   | COO   | ---                                   | ---                    |

## IBM Call for Code team

| Name              | Title                            | GitHub                                     | Slack              |
| ----------------- | -------------------------------- | ------------------------------------------ | ------------------ |
| Daniel Krook      | CTO                              | [Daniel](https://github.com/krook)         | @krook             |
| Upkar Lidder      | Technical Lead                   | [Upkar](https://github.com/upkarlidder)    | @upkarlidder       |
| Taeson Black      | Tech. Solution Specialist Intern | [Tae](https://github.com/TaeBlack)         | @tae.black         |
| Alejandro Quijada | Tech. Solution Specialist Intern | [Alejandro](https://github.com/Aquijada52) | @alejandro.quijada |

## IBM Service Corps team

| Name                        |
| --------------------------- |
| Brandi Boatner              |
| Dina Tawil                  |
| George Zacharakis-Jutz      |
| John Segrave-Daly           |
| Laura J Mokrzycki           |
| Laura Visochek              |
| Marisol Elizabeth Santillan |
| Nithya Renganathan          |
| Samantha Davis              |
| Upkar Lidder                |
| Vince Siu                   |

## Technical Steering Committee

Per the [The Pyrrha Technical Charter](Pyrrha-Technical-Charter-July-2021.pdf)

| Name                           | Organization           |
| ------------------------------ | ---------------------- |
| Salome Valero Cumplido         | Prometeo Platform S.L. |
| Marco Emilio Rodriguez Serrano | Prometeo Platform S.L. |
| Joan Herrera                   | Prometeo Platform S.L. |
| Daniel Krook                   | IBM                    |
| Upkar Lidder                   | IBM                    |

### Public meetings

Wednesdays at 2:30pm ET. [Join us on Webex](https://ibm.webex.com/ibm/j.php?MTID=mf85dc794549ef714e63c4d4983206a3e).

#### Minutes

- [Notes in the wiki](https://github.com/Pyrrha-Platform/Pyrrha/wiki)

#### Recordings

- [Wednesday, September 22, 2021](https://ibm.webex.com/webappng/sites/ibm/recording/bd9713f3fe021039b1fa0050568f2e04/playback) - `SmZKir43`
- [Wednesday, September 15, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/8c7689ccf8811039b5f60050568f9357/playback) - `RssuZpk4`
- [Wednesday, September 8, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/d1505e82f301103982fd0050568f6ebb) - `cMNMpkp8`
- [Wednesday, September 1, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/960cebd6ed811039bdbe0050568ffb55) - `eUr8t7tM`

## License

This project is licensed under the Apache 2 License - see the [LICENSE](https://github.com/Pyrrha-Platform/Pyrrha/blob/main/LICENSE) file for details.
