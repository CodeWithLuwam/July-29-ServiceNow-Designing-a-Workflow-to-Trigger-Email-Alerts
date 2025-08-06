# Designing-a-Workflow-to-Trigger-Email-Alerts
#  Creating email notifications and workflows. The process of designing a flow to trigger email alerts for high-priority asset recovery requests.
All > Email > Notifications <br>
- Create New Notificatin. Even though the Name is not required, we'll still give it a name that relates to the object: "Notify Team Leaders" <br>
- Then we'll choose a Table, Asset Recovery
- Under 'What To Send' tab, we'll pick 'Triggered'
  ![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Notification%20Name%20and%20When%20to%20Send%20tab.png?raw=true)
- In this case, we were tasked to make sure Device manager groups recieve the notification so we will click Groups and search for the group <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Who%20will%20Recieve%20notification.png?raw=true)
- For 'What it will contain' tab, we will dynamically write in the subject and the body <br>
  ![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Dynamic%20Notification%20Email.png?raw=true)
  Recap: <br>
- We have the **table** we are working with, the notification will be sent when **triggered** to a **group** with adynamic **email**. <br>

