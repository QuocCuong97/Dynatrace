# Dump 00 <img src=https://i.imgur.com/sgGY6XJ.png align=right width=20%>
### **Question 1)**
- In the list of user actions, you can see a lot of user actions which have only a few calls, and the name of the user actions look almost the same. The only difference is the ID value in the user action name. Low load anomaly detection is not working. How can you enable anomaly detection for these user actions?
    - [ ] Anomaly detection will not work for this scenario.
    - [ ] Create a User action naming rule that replaces or cuts out the ID from the action name. This will merge these similar user actions into one user action.
    - [ ] View key user actions and then sort to group the similar actions together. Then use the 'Group for analysis' function to enable anomaly detection for the group.
    - [ ] Change the 'Action duration degradation setting, and overwrite over-alerting to use a lower 'Actions per second' threshold.
### **Question 2)**
- Which of the following are problem impact levels? Select all that apply.
    - [ ] ENTITY
    - [x] APPLICATION
    - [ ] LIFECYCLE
    - [x] ENVIRONMENT
    - [x] INFRASTRUCTURE
    - [x] SERVICE
### **Question 3)**
- What are the different types of Conversion Goals?
    - [x] Number of User Actions
    - [x] Destination
    - [x] User Action
    - [ ] User Action Time
    - [ ] Page Response Time
    - [x] Session Duration
### **Question 4)**
- How can you transfer a Synthetic monitor from one Dynatrace environment to another?
    - [x] Use the Synthetic monitor API in both environments to get the details of a synthetic monitor, then create a new monitor in the other environment.
    - [ ] With the Dynatrace Synthetic conversion tool command line interface, connect to one environment and execute the command to copy monitors from one environment to the other.
    - [ ] You must manually recreate the synthetic monitor in the other environment.
    - [ ] Manually export the script (JSON) from the monitor and then import the script into a new monitor in the other environment.
### **Question 5)**
- How is the Dynatrace API authenticated?
    - [x] A valid token with the proper permissions passed in the Authorization HTTP header or the api-token query parameter.
    - [ ] A valid license with the correct API modules enabled needs to be in place in your environment. This provides the authentication for any API calls.
    - [ ] A user name and password with the proper permissions is needed to establish a session for the API calls.
    - [ ] Once an API endpoint is unlocked with a token in the API explorer, that endpoint remains open for any API calls, even from external systems, and no further authentication is needed.
### **Question 6)**
- Some log files may not be auto-discovered by Dynatrace. How do you add a new log source to include those logs in Log Monitoring?
    - [ ] Add the log path in process group settings.
    - [ ] New log sources cannot be added.
    - [ ] Select the new logs to include from the Hosts or Process Groups perspective log sources lists.
    - [ ] Add a log path to the OneAgent Log Monitoring configuration file.
### **Question 7)**
- What do you need in order to create a custom coded OneAgent extension?Select all that apply.
    - [x] The Extension SDK
    - [ ] ActiveGate SDK
    - [ ] Dynatrace OneAgent
    - [x] Python
### **Question 8)**
- In Dynatrace Managed, which user repository options are available for managing users and groups? Select all that apply.
    - [ ] Integration with an SSO ldP
    - [ ] An NT LAN Manager
    - [ ] 3rd party OpenlD service
    - [ ] SAML
    - [ ] External LDAP server
### **Question 9)**
- How long is data stored for timeseries metrics for key requests?
    - [ ] 90 days
    - [ ] 10 days
    - [ ] 5 years
    - [x] 35 days
### **Question 10)**
- During the page load process, what does the request measure refer to?
    - [ ] Time spent waiting for the first byte of the document response.
    - [ ] Time between the response being delivered and the OnLoad event.
    - [ ] Time spent downloading the document response.
    - [ ] Time spent establishing a socket connection from the browser to the web server
### **Question 11)**
- Which of the following commands can be used to start the OneAgent service on a Linux distribution with SystemV or systemd? (Where oneagent is the init.d script for OneAgent.) Select all that apply.
    - [x] systemctl start oneagent
    - [ ] systemctl oneagent
    - [x] service oneagent start
    - [ ] oneagent service start
### **Question 12)**
- What happens when you set the cost and traffic control feature for a mobile app to 30%? Select all that apply
    - [ ] Reduced cost without reduction in visibility in how the app is used.
    - [ ] Lower cost, but also reduced visibility in how the app is used.
    - [ ] 30% of user sessions (evenly distributed) will be captured and analyzed.
    - [ ] The first 30% of user sessions will be captured and analyzed.
### **Question 13)**
- What is the difference between problems and events? Select all that apply.
    - [ ] Events represent different types of individual incidents
    - [ ] Problems contain root cause and impact
    - [ ] Problems contain correlated events
    - [ ] Events contain correlated problems
    - [ ]Problems are identical to events and alerts
### **Question 14)**
- The network connectivity metric measure is:
    - [x] The percentage of properly established TCP connections compared to TCP connections that were refused or timed out
    - [x] The bit-rate of available or consumed information capacity expressed in metric multiples of bits per second
    - [ ] The amount of time it takes for data to travel from one location to another across a network
    - [ ] Calculated by routing algorithms when determining the optimal route for sending network traffic
### **Question 15)**
- For the three dimensions of an identified problem, which statements are true? Select all that apply.
    - [ ] The Visual Resolution Path shows all monitored entities related to a problem.
    - [ ] Impact shows only the services that have been affected by the problem.
    - [ ] The Visual Resolution Path shows the dependencies between your application and the underlying services and infrastructure components that support it.
    - [ ] The Root Cause may identify more than one component.
    - [ ] The Root Cause always identifies a single infrastructure component
    - [ ] Impact shows applications or components that have been affected by the problem.
### **Question 16)**
- What options are available for configuring anomaly detection for a service? Select all that apply.
    - [x] Response time degradations
    - [ ] CPU saturation
    - [ ] Action duration degradation
    - [x] Service load drops or spikes
    - [ ] Java out of memory problem
    - [x] Increases in failure rate
### **Question 17)**
- Which time frames are used to learn frequent issues within your environments? Select all that apply.
    - [ ] Yearly
    - [ ] Daily
    - [x] Weekly
    - [ ] Hourly
### **Question 18)**
- What benefits do you gain from marking an action as a Key user action? Select all that apply.
    - [ ] They can be pinned to the dashboard for quick access
    - [ ] Anomaly detection will automatically detect performance degradations
    - [ ] Extends historical data retention time
    - [ ] Definition of specific Apdex thresholds for high-priority actions
### **Question 19)**
- Where is user session data stored for Dynatrace Managed?
    - [ ] Couchbase
    - [ ] Elasticsearch
    - [ ] DynamoDB
    - [ ] Cassandra
### **Question 20)**
- What are the different problem severity levels with which Dynatrace automatically identifies problems?
    - [ ] Regions, Areas, Sites
    - [ ] Application, Service, Process, Infrastructure
    - [ ] Low, Medium, High, Severe, Critical
    - [x] Availability, Error, Slowdown, Resource
### **Question 21)**
- Which problem filters can be applied by configuring an alerting profile? Select all that apply.
    - [ ] Tags
    - [ ] Problem duration
    - [x] Event severities
    - [x] Problem severity
    - [ ] Number of service requests
### **Question 22)**
- Why would you want to manually tag any important low-volume requests as Key requests?
    - [ ] To ensure standard alerts will be raised for all of your important requests, even if they are low volume
    - [ ] So you can pin them to your Dashboard for easy access
    - [ ] To ensure Apdex calculations include all requests, even if they are low volume
    - [ ] Low volume requests are not otherwise monitored
### **Question 23)**
- When applied to web request analysis, how is the detection and analysis affected by creating a custom service versus a request attribute?
    - [ ] A custom service creates new entry points (PurePaths). A request attribute adds data to an existing PurePath (entry point).
    - [ ] A custom service will not have an affect on PurePaths until custom request attributes are created for it.
    - [ ] There is no difference they both affect PurePaths the same way and provide more information about transactions.
    - [ ] A request attribute creates new entry points (PurePaths). A custom service adds data to an existing PurePath (entry point).
### **Question 24)**
- How do you assign permissions to users in Dynatrace SaaS?
    - [ ] Users inherit the permissions assigned to the groups they belong to, but the Account Manager permission is assigned directly to each user.
    - [ ] You can assign permissions directly to users.
    - [ ] Environment permissions are inherited from groups users belong to, and Account permissions are assigned directly to users.
    - [ ] Users inherit the permissions assigned to the groups they belong to.
### **Question 25)**
- When configuring problem notification emails, how do you filter the problem feed to ensure you only receive the notification for a set group of problems?
    - [x] By selecting an alerting profile
    - [ ] By setting up the problem filter on the notification
    - [ ] By selecting placeholders that match values found in the problems you want
    - [ ] By selecting a management zone
### **Question 26)**
- If your host typically runs with high CPU load, how can you prevent excessive Problem Notifications?
    - [ ] Edit the Process settings for each process on the host, and set the Disable Anomaly Detection switch to On.
    - [ ] Modify the ruxitagent.confon the host and disable CPU_ProbIem_Detection.
    - [ ] From the Process details, edit the Problem Detection settings and set the CPU Problem Detection switch to Off.
    - [x] From the Host details, edit Anomaly Detection and set up custom settings for CPU saturation.
### **Question 27)**
- Which of the following statements about Automatic baselines is true?
    - [ ] They are available immediately after the application or service has been detected.
    - [ ] They are available 7 days after the application or service has been detected.
    - [ ] They are available 1 hour after an application, service, or infrastructure component has been detected.
    - [x] They are available 2 hours after the application or service has been detected.
### **Question 28)**
- Monitoring candidates can be described as:
    - [ ] Hosts which communicate over TCP/IP and belong to the same network as instrumented hosts
    - [ ] Hosts with OneAgent running in cloud infrastructure mode
    - [x] Non-instrumented hosts that communicate with instrumented hosts
    - [ ] Hosts without OneAgent installed that are qualified for monitoring due to high resource consumption
### **Question 29)**
- You've configured your application's key performance metric for satisfactory performance to be from 0 to 5 seconds. However, there is a new client sign-up action which should take only 3 seconds. What can you do to monitor that the sign-up action is not frustrating users by taking longer than 3 seconds, while still allowing other actions to take up to 5 seconds?
    - [ ] The application's key performance metric settings must be changed to 3 seconds.
    - [ ] Create a second application with different key performance metric settings and associate the action with the new application.
    - [ ] Mark the action as a key request and set the key performance metric settings for the action to 3 seconds.
    - [ ] Mark the action as a key user action and set the key performance metric settings for the action to 3 seconds.
### **Question 30)**
- Which of the following are the components provided in the Dynatrace Managed installer? Select all that apply
    - [x] Embedded ActiveGate
    - [ ] Kinesis Module
    - [ ] Application Load Balancer
    - [x] Elasticsearch
    - [x] NGINX
    - [x] Cassandra
    - [ ] Cluster ActiveGate
