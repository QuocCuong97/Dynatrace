# Dump 01 <img src=https://i.imgur.com/sgGY6XJ.png align=right width=20%>
### **Question 1)**
- Which of the following is the correct structure of Dynatrace Real User Monitoring? Select all that apply.
    - [x] An Application consists of User sessions which are made up of user actions.
    - [ ] Applications consist of User events which call services.
    - [ ] User sessions consist of User actions which span multiple Applications.
    - [x] Applications consist of User Actions, while both are contained within a User Session.
### **Question 2)**
- To define specific settings for a performance metric for a user action, what do you need to do?
    - [x] Edit the Application settings, select the actions to customize, and set the performance metric values you want to apply to the selected actions.
    - [ ] This can only be set for Applications, not for individual user actions.
    - [ ] Mark the action as a key request and edit the performance metric settings.
    - [ ] Mark the action as a key user action and edit the key performance metric settings.
### **Question 3)**
- What is the data retention period for DEM for Dynatrace Managed RUM, including Session Replay data?
    - [ ] Fixed at 35 days
    - [x] It is configurable up to 35 days
    - [ ] It is configurable up to 10 days
    - [ ] Fixed at 1 week
### **Question 4)**
- Which of the following is NOT a function of an ActiveGate?
    - [ ] Authentication of OneAgent requests.
    - [ ] Act as entry points for sealed networks.
    - [ ] Buffering and compression of OneAgent messages and delivery to the Dynatrace cluster.
    - [x] Detection of external services, such as database services, for collection of performance data.
### **Question 5)**
- What type of thresholds does Dynatrace use for problem detection? Select all that apply.
    - [ ] User experience score
    - [ ] Synthetic performance thresholds
    - [x] Static thresholds
    - [x] Automated baselines
### **Question 6)**
- Why might there be an 'Opaque service' in your environment? Select all that apply.
    - [ ] Services have been aggregated because they are of the same process group and perform identical functions across separate cluster nodes.
    - [x] The service technology is supported by Dynatrace but code-level visibility isn't available.
    - [ ] Code-level visibility isn't possible because the services have external dependencies.
    - [x] The service technology is unrecognized or unsupported.
### **Question 7)**
- How does OneAgent provide Real User Monitoring?
    - [ ] It monitors the processes running on each host and collects performance metrics about user traffic.
    - [x] It injects a JavaScript tag into the HTML of each application page that is rendered by your web servers.
    - [ ] It injects parameters into the URLs which track user traffic.
    - [ ] It traces the user's PurePath.
### **Question 8)**
- Why is it a good idea to perform all detailed problem analysis and triage within 14 days of problem detection?
    - [ ] The timeframe selector for analysis only allows for 14 days of problem history
    - [ ] Drill-down within the problem context is only available for 14 days
    - [ ] The problem is automatically closed after 14 days
    - [x] Timeseries data is available at full granularity for 14 days
### **Question 9)**
- In the highlighted portion of the image, what can you tell from dashed lines between the EasytravelService and the two other services?
    <p align=center><img src=https://i.imgur.com/nGSQrie.png width=30%></p>

    - [ ] The services should be communicating, but due to a network problem, communication between the services is unstable.
    - [ ] There is currently increased traffic between the EasytravelService and the other two services. 
    - [x] There has been communication between EasytravelService and the other two services in the past, but not recently.
    - [ ] The Easytravel service is experiencing a problem which is caused by the two services connected with dashed lines.
### **Question 10)**
- If you see an Unexpected low traffic or an Unexpected high traffic problem, what has Dynatrace detected?
    - [ ] The predicted future traffic appears to be less than the current application traffic.
    - [ ] A drop in the number of unique application users from the previous time frame.
    - [x] A deviation between the actual and what the predicted application traffic was.
    - [ ] A global application outage.
### **Question 11)**
- You only want to monitor PHP on a single host, how can you do this?
    - [x] Disable PHP Global monitoring, then edit the host settings to enable PHP monitoring on that host.
    - [ ] Disable PHP Global monitoring, and then modify the OneAgentRuntime.config and add "PHP" to the NoMonitor line.
    - [ ] On the PHP Technology page, deselect any hosts where you do not want to monitor PHP.
    - [ ] Disable PHP Global monitoring, then edit the PHP Process group settings to add the Host to the Host group list.
### **Question 12)**
- How can you show the locations of users with private IP addresses on the world map?
    - [ ] By mapping IP addresses to locations in the Web & Mobile monitoring settings.
    - [ ] By configuring the Geolocation Breakdown table
    - [ ] You can manually place the user locations on the world map.
    - [x] By reordering the detection rules on the IP detection page.
### **Question 13)**
- Which dimensions are used for Application baselining? Select all that apply.
    - [x] Operating system
    - [ ] Service method
    - [x] Geolocation
    - [ ] Conversions
    - [ ] Tags
    - [x] User action
    - [x] Browser
### **Question 14)**
- What are considered to be "Top database statements"?
    - [ ] The slowest requests in the selected timeframe
    - [ ] The statements with the lowest error rates
    - [x] The most frequent and expensive database statements
    - [ ] The most optimized database statements by time
### **Question 15)**
- How can you track which users in an application have successfully completed a checkout?
    - [x] By setting a conversion goal
    - [ ] By setting a user tagging rule
    - [ ] By editing your content capture settings
    - [ ] By uploading a source map file
### **Question 16)**
- What is pictured in the image shown?
    <p align=center><img src=https://i.imgur.com/NUV4Q4g.png width=30%></p>

    - [x] Service flow
    - [ ] Service backtrace
    - [ ] Smartscape
    - [ ] A custom chart showing the distribution of web requests for a service
### **Question 17)**
- What do Response time hotspots on the Services page indicate? Select all that apply.
    - [ ] The services making the most database requests
    - [ ] The services making the most requests
    - [ ] The activities utilizing the most resources for each service
    - [x] The activities consuming the most time for each service
### **Question 18)**
- What is the default reference period of performance baselines for database services?
    - [x] 2 hours
    - [ ] 7 days
    - [ ] 35 days
    - [ ] 72 hours
### **Question 19)**
- How does Dynatrace determine the root cause of a problem?
    - [x] An Al engine analyzes dependencies between components, and builds a model which is used to determine the components most likely causing a problem.
    - [ ] If an alert has been raised in the last 24 hours, the alert's component is considered the root cause.
    - [ ] Using all alerts in the last 2 hours, an Al engine uses the causation model to determine which infrastructure component raised the most alerts, and sets that component as the root cause.
    - [ ] The component that raised the first alert in a series of alerts is considered the root cause. Alerts are considered to be in a series when each alert occurs within a 5-minute time frame of the last alert.
### **Question 20)**
- Which of the following statements about user session properties is true? Select all that apply.
    - [x] User session properties can be used in USQL queries.
    - [x] You can use a single user session property across multiple applications.
    - [ ] User session properties are retrospective.
    - [x] User session properties are available for web and mobile applications.
### **Question 21)**
- When viewing a host page, how can you tell which tags were created manually and which were created via the oneagentctl?
    - [ ] The tags are displayed in different sections on the page.
    - [x] Tags created via oneagentctl are prefixed with the [Environment] string.
    - [ ] Manually created tags are prefixed with the [Manual] string.
    - [ ] You cannot tell the difference between the tags.
### **Question 22)**
- Which options are available for disabling auto-update of OneAgent? Select all that apply.
    - [x] Globally for all OneAgent installations.
    - [x] On individual hosts.
    - [ ] You cannot disable automatic updating of OneAgent.
    - [ ] Only in installations where an ActiveGate is installed.
### **Question 23)**
- When you merge services, what happens with the service data?
    - [ ] Both historical data and new data is now aggregated and associated with the merged service.
    - [x] Historical data remains for the services which were merged, and any new aggregated data is now associated with the merged service.
    - [ ] Any new or historical data is associated with the individual services, but is also aggregated for the new merged service.
    - [ ] Historical data is merged and associated with the new service, new data is associated with the individual services, but merged when it is older than 14 days.
### **Question 24)**
- How long does an application need to run before traffic spike and drop alerts are raised?
    - [ ] For at least 20% in the last day
    - [x] For at least 50% in the last 2 days
    - [ ] For at least 20% in the past week
    - [ ] For a full week
### **Question 25)**
- How can Real User Monitoring be configured if you have no access to the host? Select all that apply.
    - [ ] Monitoring would not be possible
    - [x] Agentless monitoring
    - [ ] OneAgent plugin
    - [ ] Browser Extension
### **Question 26)**
- By default, how often does Dynatrace auto-discover, analyze, and store log files?
    - [x] Every 60 seconds
    - [ ] Every 15 minutes
    - [ ] Every 24 hours
    - [ ] Every 2 hours
### **Question 27)**
- In which of the following cases is an ActiveGate needed? Select all that apply.
    - [x] To store memory dumps
    - [x] To monitor virtualized infrastructure
    - [ ] To monitor database services
    - [ ] To store and access log files
    - [x] To access sealed networks
### **Question 28)**
- Which of the following are considered by Dynatrace when identifying and naming Web request services? Select all that apply.
    - [ ] IP address
    - [x] Web application ID
    - [ ] Database requests
    - [x] Web server name
    - [x] Context root
### **Question 29)**
- What are the default metrics featured for a mobile application in the application overview?
    - [ ] User behavior - Active sessions, Actions per session, Entry/Exit actions, Bounce rate, Conversion goals
    - [ ] Properties - Screen size, Manufacturer, App version, IP Address, Operating system, Device, Geolocation
    - [ ] Performance analysis - Actions/min, Action duration, Apdex rating, JavaScript errors, 3rd party providers, Services
    - [x] App usage - User experience, Network performance, Crashes, Called services
### **Question 30)**
- What can you do to check the availability of internal applications or resources that are inaccessible from outside your network? Select all that apply.
    - [ ] Create a Browser Monitor on a Cluster ActiveGate with a private synthetic location.
    - [x] Create an HTTP Monitor on an Environment ActiveGate with a private synthetic location.
    - [ ] Create a Browser Monitor to simulate an internal user session which is executed by Synthetic Control.
    - [x] Create a Browser clickpath on a Dynatrace managed node that can communicate with Mission Control.
### **Question 31)**
- How does Dynatrace detect external services like unmonitored hosts?
    - [ ] External services are not detected.
    - [ ] They are detected when they send or receive requests from your monitored services and applications.
    - [ ] Dynatrace sees the performance data from the external services.
    - [x] They are detected when your monitored services or applications make unknown requests.
### **Question 32)**
- When would you need to use the RUM browser extension?
    - [x] When you want Real User Monitoring but don't have access to the underlying application servers or the HTML page source.
    - [ ] When you want Real User Monitoring and have access to the application server, but don't have access to the HTML page source.
    - [ ] Any time you want to track Real User Monitoring data.
    - [ ] It is required to record a browser clickpath.
### **Question 33)**
- When Dynatrace detects an application running on a host, what is used to capture and group the application monitoring data?
    - [x] You must first define an application for the data to be captured and grouped.
    - [ ] A new dashboard focused on your application.
    - [ ] The application name is detected and used to define an application.
    - [ ] A default application used as a "catch all."
### **Question 34)**
- How does Dynatrace perform evaluations for slowly degrading response-time degradations?   
    - [ ] Evaluations are based on the slowest 10% of all requests during the degradation.
    - [x] Evaluations are performed based on 15-minute time intervals.
    - [ ] Evaluations are performed based on sliding 5-minute time intervals.
    - [ ] Evaluations are based on the number of users impacted by the response-time degradation. The sliding time-frame for evaluation is increased by 5 minutes for every 500 users affected.
### **Question 35)**
- What can you configure in Dynatrace to automatically name new or existing services?
    - [ ] Service Detection Rules
    - [x] Service Naming Rules
    - [ ] Services Merging Rules
    - [ ] Process Group Naming Rules