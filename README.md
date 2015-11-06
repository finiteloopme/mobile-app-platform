---
layout: post
title: Overview of Mobile Application Platform
categories:
    - technical
tags:
    - how-to
    - mobile
---
# Overview of Mobile Application Platform
As the adoption of mobile and smart devices keeps increasing, Enterprises have started exploring avenues to effectively engage the device owners by maximising the benefits offered by these devices.  

These device owners could be categorised into two groups:

1. Internal workforce: use of personal handheld devices would increase productivity by streamlining service operations and reducing manual elements like paperwork and travel.
2. End customers are increasingly using their smartphones to:
    - Research and even troubleshoot products and services
    - Expressing their opinions via social media

While considering mobile application development across these two groups, there are three basic themes:

1. Multiple platforms: users would be using iPhones, iPads, Android phones and tablets, Windows phones and tablets
2. Multiple applications: different applications to serve different concerns
3. Multiple developers (collaboration)
4. Consistent back-end services (and re-use of existing assets and services)

## Special considerations for Mobile development

Web                                       | Mobile
------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Performant network connection             | Lossy edge network
No restrictions on making server requests | Need to make fewer requests
Payload size is not a big concern         | Payload must be small
Deployment is well controlled             | Deployment process really depends on user.  In enterprise setup (private app store), updates can be forced.  But users of public app stores may never update the application.

## Common functions
<<<<<<< HEAD


=======
>>>>>>> 3dfa6ba2bf0e896e26a72e2f88ce2804085c9056
## Tools we will use
1. [Red Hat Mobile Application Platform](https://www.redhat.com/en/technologies/mobile/application-platform) (RH-MAP)
2. [Grunt](http://gruntjs.com/)
3. [git](https://git-scm.com/)
4. [node.js](https://nodejs.org/en/)

## What is project in RH-MAP?
Project in RH-MAP is a combination of one or more of the following applications.
- Mobile client application
- Cloud microservice application
- MBaaS services

<<<<<<< HEAD

## Getting started:

- Register for an account [here](https://openshift.feedhenry.com/)
- Login to Red Hat Mobile Application Platform Dev Studio
- Create project of type *Hello World Project* in RH-MAP studio
- 
=======
## Further Reading
1. [Using Cordova plugins for Client App](https://apbg-apac.redhat.feedhenry.com/docs/guides/using_cordova_plugins.html)
2. [RH-MAP API reference](https://apbg-apac.redhat.feedhenry.com/docs/api.html)


## Getting started:
- Create project of type *Welcome Project* in RH-MAP studio
>>>>>>> 3dfa6ba2bf0e896e26a72e2f88ce2804085c9056

### [Working locally](https://apbg-apac.redhat.feedhenry.com/docs/dev_tools/local.html):

1. Install the <kbd>fhc</kbd> command line utility:

    ``` bash
    npm install -g fh-fhc
    fhc target https://[your-studio-domain].feedhenry.com
    fhc login [email address] [password]
    # List the projects
    fhc projects
    ```

2. Add an SSH public key to the platform

    ``` bash
    fhc keys ssh add myKey ~/.ssh/id_rsa.pub
    ```

3. Clone the project repository (git) locally

    ``` bash
    # Get the project id
    fhc projects
    # Note the id of the project to be cloned
    fhc projects clone vafq7bwedcbzogabeqiycxau # last part is project id
    ls # list all the applications within the project
    cd <application-name> # changes the directory to a specific application
    ```

4. Get meta-data for applications within the main project:

    ``` bash
    fhc apps vafq7bwedcbzogabeqiycxau # last argument is the project-id
    ```

5. To run cloud server locally:

    ``` bash
    cd <PROJECT-DIR>/<cloud-app> # Go to the Cloud App directory
    npm install # Install all the dependencies for running the Cloud App
    grunt serve
    ```

6. By default the client application is configured to use backend services (cloud application & MBaaS services) on *localhost*.  To point client app to cloud services, we need the URL for cloud services.

    ``` bash
    # env argument can have following value:
    # dev
    # test
    fhc app hosts --app=<cloud-app-name> --env=dev
    # Copy the URL returned by the above command. And update the 'default_local_server_url' variable in Gruntfile.js
    ```

<<<<<<< HEAD
## Further Reading

1. [Using Cordova plugins for Client App](https://apbg-apac.redhat.feedhenry.com/docs/guides/using_cordova_plugins.html)
2. [RH-MAP API reference](https://apbg-apac.redhat.feedhenry.com/docs/api.html)


=======
>>>>>>> 3dfa6ba2bf0e896e26a72e2f88ce2804085c9056
## TO-DO

### Use-case
    - [ ] Create a MBaaS application with authentication with Google
    - [ ] Create a MBaaS application to navigate/browse Google Drive
    - [ ] Create a client and cloud application to display MD file
