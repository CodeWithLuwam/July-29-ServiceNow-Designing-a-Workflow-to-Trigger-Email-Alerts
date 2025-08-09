# Designing-a-Workflow-to-Trigger-Email-Alerts
# Creating email notifications and workflows. The process of designing a flow to trigger email alerts for high-priority asset recovery requests.

Scenario: <br>
You've been working on the ITSM team at DXC Technology for a couple of months. Your manager, Erika, has noticed that critical Asset Recovery Requests aren't being seen quickly enough. The team leads, specifically the Device Managers group, are missing high-priority tasks that need immediate attention.
She sends you this request: <br>

"Can you make it so that whenever someone creates a new high-urgency Asset Recovery Request, an automatic email gets sent to the Device Managers? The email should include: <br>
- Employee <br>
- Asset Type <br>
- Asset Tag <br>
- Urgency" <br>

Your task is to configure this process using ServiceNow's Flow Studio and **Notification** system, so that the message only goes out when it meets those urgency conditions. <br>

---
**Steps:** <br>
1. **Create a Notification** <br>
  a. Navigate to: **All > Email > Notifications** <br>
  b. Click **New** to crate a new Notificatin. <br>
  c. Eneter a descriptive name Even though the **Name** (e.g., `"Notify Team Leaders"`) <br>
  d. Select the **Table**: `Asset Recovery`.
  ---
2. **Configure "When To Send"** <br>
  a. In the **When To Send** tab, select **Triggered** (this will get triggered by the workflow we’ll create in a later step). <br>
  ![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Notification%20Name%20and%20When%20to%20Send%20tab.png?raw=true)
  b. Under **Who will receive**, choose **Groups**. <br>
  c. Search for and select the **Device Managers** group. (Since the requirement is to notify the Device Managers group) <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Who%20will%20Recieve%20notification.png?raw=true) <br>
---
3. **Configure What it will contain** <br>
  a. Write a **dynamic subject** and **body** to include: <br>
     - Employee
     - Asset Type
     - Asset Tag
     - Urgency
  ![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Dynamic%20Notification%20Email.png?raw=true)

**Recap so far**: <br>
- We have identified the **table** we’re working with.
- The notification will be sent when **triggered** to the correct **group**.
- The **email** will have dynamically generated content. <br>

-----
**Next Steps**:<br>
4. **Create a Flow in Flow Designer** <br>
    a. Navigate to **Flow Designer** <br>
    b. Click **New Flow**  <br>
    c. Name the flow and click **Build Flow** <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Name%20New%20Flow%20in%20Workflow%20Studio.png?raw=true)<br>
    d. Hold **Shift** and select the options needed for this flow. <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Condition%20Urgency%20High%20or%20Medium.png?raw=true) <br>

----
5. Add the Action <br>
  a. Choose **Send Notification** (Not Send Email, since we already created an email earlier).
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Action%20Send%20Notification.png?raw=true)
  b. Select the record. <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Drag%20Asset%20Recovery%20Record.png?raw=true)
  c. The **Table** field will auto-fill with `Asset Recovery Request`. <br>
  d. In **Notification**, select and link it with "Notify team lead" <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Table%20Automatically%20Linked.png?raw=true) <br>
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Finished%20Workflow.png?raw=true) <br>

-----
6. **Test the Flow**
   a. Go to **Asset Recovery Request** table and create a **new record** with **high urgency**.
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/New%20Asset%20Recovery%20Record%20to%20Test.png?raw=true)

---
7. **Verify Email Delivery** <br>
  a. Navigate to: **System Mailbox > Outbound > Outbox**. <br>
  b. Confirm the email has been sent. <br>
  c. Preview to ensure the email ontains the required details.
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Email%20Outbound.png?raw=true)
![](https://github.com/CodeWithLuwam/Designing-a-Workflow-to-Trigger-Email-Alerts/blob/main/Images/Preview%20Email%20Notification%20Sent.png?raw=true)
