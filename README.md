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
- [Public meetings](#public-meetings)
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
| Charlie Evans     | Software Engineer                | [Charlie](https://github.com/hawk4031)     | @Charlie Evans     |

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

## Public meetings

Wednesdays at 2:30pm US ET. [Join us on Webex](https://ibm.webex.com/ibm/j.php?MTID=m5743406c4328d840261b34ce5aeb0bf6).

### Minutes

- [Notes in the wiki](https://github.com/Pyrrha-Platform/Pyrrha/wiki)

### Recordings

- [Wednesday, May 25, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/4c841b4dbe87103a9ed600505681ab5a) - `Smb4Afyq`
- [Wednesday, May 18, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/c3c02f29b906103a887c005056819d82) - `5Xg5R4w9`
- [Wednesday, May 11, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/8268414db388103abe5d00505681d9e5) - `Jq8CcMdc`
- [Wednesday, May 4, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/b7da73a8ae06103abffe00505681593c) - `fXaf9xGR`
- [Wednesday, April 27, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/a4e59876a886103a9bfe005056813522) - `Pj6jRFqm`
- [Wednesday, April 13, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/581d4ef79d86103abf9c005056817f61) - `wCCGx8Rx`
- [Wednesday, April 6, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/32d8a4099806103ab8ed00505681cf8d) - `Bw2GJeJH`
- [Wednesday, March 30, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/3b72d4e39286103aaf7400505681ca92) - `Jiyk8Hht`
- [Wednesday, March 23, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/80b998898d06103a87ff0050568f7db2) - `eAu9n6ag`
- [Wednesday, March 16, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/cb439b7c8785103abfbb005056816d72) - `jUrnF3rM`
- [Wednesday, March 9, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/4fad12c4820e103a8def0050568f47af) - `uKMimkV6`
- Wednesday, March 2, 2022 - Not recorded
- [Wednesday, February 23, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/cdf02279770d103a97ba0050568f6ebb) - `JpBmTxm2`
- [Wednesday, February 16, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/40c4cee7718d103ab7ab005056815191) - `tUSwHk7X`
- [Wednesday, February 9, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/69a91a406c0d103a94ee0050568ffafd) - `sM7rKJCA`
- [Wednesday, February 2, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/0ad81709668d103a97ff005056815191) - `3Rk6q9FQ`
- [Wednesday, January 26, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/26b1f84c610d103a9ef20050568166c3) - `mZdfFeM6`
- [Wednesday, January 19, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/aee7ce635b8c103ab6ff0050568fca64) - `xAWFKFF5`
- [Wednesday, January 12, 2022](https://ibm.webex.com/recordingservice/sites/ibm/recording/777b5034560c103ab77d0050568fac24/playback) - `FmNhJ55F`
- [Wednesday, December 1, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/eb4313ec350b103ab7ff005056816d72) - `ThEGSPS5`
- [Wednesday, November 24, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/8fad443f2f8b103aac670050568f31a0) - `gNwaH8np`
- [Wednesday, November 10, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/494731d7248b103ab7fe0050568ff097/playback) - `nKHdxyB8`
- [Wednesday, November 3, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/4fb43b941f02103ab5bf0050568fa1a2/playback) - `JqNZJUY2`
- [Wednesday, October 20, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/417c7c931402103abff9005056815191/playback) - `vNjR39SB`
- [Wednesday, October 13, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/2224f3250e82103abfbd0050568f9357/playback) - `cFV3cYuX`
- [Wednesday, October 6, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/e492aa800901103abfd90050568ffafd/playback) - `DwbbdKy2`
- [Wednesday, September 29, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/902ff9920381103a9d770050568fca64/playback) - `NvpQ6v2C`
- [Wednesday, September 22, 2021](https://ibm.webex.com/webappng/sites/ibm/recording/bd9713f3fe021039b1fa0050568f2e04/playback) - `SmZKir43`
- [Wednesday, September 15, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/8c7689ccf8811039b5f60050568f9357/playback) - `RssuZpk4`
- [Wednesday, September 8, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/d1505e82f301103982fd0050568f6ebb) - `cMNMpkp8`
- [Wednesday, September 1, 2021](https://ibm.webex.com/recordingservice/sites/ibm/recording/playback/960cebd6ed811039bdbe0050568ffb55) - `eUr8t7tM`

## License

This project is licensed under the Apache 2 License - see the [LICENSE](https://github.com/Pyrrha-Platform/Pyrrha/blob/main/LICENSE) file for details.
