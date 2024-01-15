---
title: "PROJECT 2: Tenancy Wide monitoring setup"
datePublished: Mon Jan 15 2024 17:37:07 GMT+0000 (Coordinated Universal Time)
cuid: clrf7jgrw000408l88pkq20z5
slug: project-2-tenancy-wide-monitoring-setup
tags: oci

---

PROJECT : Project require a daily comprehensive report detailing all modifications made within the Oracle Cloud Infrastructure (OCI) tenancy on the preceding day. Please suggest an optimal and cost effective approach for accomplishing this task. At this juncture, our focus is solely on obtaining information about any changes, creations, or deletions, without delving into access-related details.

Starting from the previous day task, planning to do the monitoring tenancy wide but need to look more into into tenancy explorer.

Reference link : [https://www.ateam-oracle.com/post/demystifying-logging-and-monitoring-agent-types-in-oci-observability-and-management](https://www.ateam-oracle.com/post/demystifying-logging-and-monitoring-agent-types-in-oci-observability-and-management)

But the optimal solution so far:

To achieve a daily comprehensive report detailing all modifications made within the Oracle Cloud Infrastructure (OCI) tenancy, you can leverage OCI services such as the Audit service and combine it with a serverless architecture using Oracle Functions. Here's an optimal approach:

**OCI Audit Service:** Enable the OCI Audit service to capture all the changes within your tenancy. Audit service provides detailed logs of activities related to resources and configurations. Configure the Audit service to send audit events to an Oracle Cloud Storage bucket.

**Oracle Cloud Storage:** Create an Oracle Cloud Storage bucket to store the daily audit logs. Ensure that the bucket is properly configured for security and access control.

**Oracle Functions:** Create an Oracle Function to process the daily audit logs stored in the Cloud Storage bucket. Oracle Functions allows you to run serverless functions in response to events, making it suitable for this periodic task.

**Daily Trigger:** Set up a daily trigger mechanism using OCI Scheduled Jobs or any external scheduler to invoke the Oracle Function at a specific time every day.

F**unction Logic:** Inside the Oracle Function, use the Oracle Cloud SDK or REST APIs to fetch the audit logs from the Cloud Storage bucket for the preceding day. Extract relevant information from the audit logs, such as resource modifications, creations, or deletions. Filter out any access-related details if not required.

**Report Generation:** Aggregate the extracted information and generate a comprehensive report in a desired format (e.g., CSV, JSON, or HTML).

**Notification (Optional):** Optionally, configure the Oracle Function to send a notification (e.g., email) with the generated report to specified recipients.

**Logging and Monitoring:** Implement proper logging within the Oracle Function for troubleshooting and monitoring purposes.

**Security Considerations:** Ensure that the Oracle Function has the necessary IAM (Identity and Access Management) permissions to access the Cloud Storage bucket and other required services. Apply the principle of least privilege when configuring IAM roles. By implementing this solution, you can automate the process of gathering information about modifications made within the OCI tenancy on a daily basis, providing a comprehensive and structured report without exposing access-related details.

**More about Oracle Functions :**

In Oracle Cloud Infrastructure (OCI), Oracle Functions is a serverless compute service that enables you to run code without provisioning or managing servers. It allows you to execute functions in response to events, making it suitable for event-driven architectures. Here's how you can use Oracle Functions to send events and combine it with another Oracle Function:

Create an Event Source:

Identify the event source that will trigger the Oracle Function. This could be an event from an OCI service (e.g., Object Storage events, Audit Service events) or an external event source (e.g., HTTP requests). Create the First Oracle Function (Event Producer):

Develop an Oracle Function that acts as the event producer. This function is responsible for generating an event and triggering the subsequent actions. Inside this function, you can use the Oracle Cloud SDK or REST APIs to publish an event to the Oracle Cloud Events service. Define the Event Payload:

Define the payload of the event that contains relevant information. This payload might include details about the modifications made within the OCI tenancy. Create an Event Rule:

Set up an event rule to associate the event source with the Oracle Function (Event Producer). The event rule specifies the conditions that must be met for the function to be triggered. Configure the Oracle Function (Event Consumer):

Develop a second Oracle Function that will act as the event consumer. This function is responsible for processing the event when triggered. Inside this function, you can include logic to fetch the required information, generate a report, and send it to specified recipients. Subscribe the Event Consumer Function to the Event:

Subscribe the Oracle Function (Event Consumer) to the event created in the Event Producer function. This establishes the link between the event producer and the consumer. Define Function Dependencies and Permissions:

Ensure that both functions have the necessary dependencies and permissions to interact with other OCI services, such as Object Storage, Audit Service, or any other services involved in the workflow. Testing and Monitoring:

Test the end-to-end workflow to ensure that events are generated, propagated, and processed correctly. Implement proper logging within both functions for monitoring, troubleshooting, and auditing purposes. By using Oracle Functions in this way, you can build a scalable and event-driven architecture. The first function triggers an event based on certain conditions (e.g., daily modifications within the OCI tenancy), and the second function processes that event, generating a report or performing other actions. This approach is particularly useful for scenarios where you want to decouple different parts of your application, making it more modular and easier to maintain.

### **BEST Approach :**

To achieve a daily comprehensive report detailing all modifications made within the Oracle Cloud Infrastructure (OCI) tenancy, you can use OCI's native services and tools. Below is an optimal and cost-effective approach to accomplish this task:

### **Solution Overview:**

1. **OCI Audit Service:**
    
    * Leverage OCI Audit service to capture all changes made within your OCI tenancy.
        
    * OCI Audit records changes to resources, configurations, and relationships, providing a detailed log of activities.
        
2. **OCI Object Storage:**
    
    * Store the generated audit logs in an OCI Object Storage bucket for archival and easy access.
        
3. **OCI Notifications:**
    
    * Set up OCI Notifications to trigger an event whenever a new audit log is generated.
        
4. **OCI Cloud Shell:**
    
    * Utilize OCI Cloud Shell to automate the process of extracting and formatting the required information from the audit logs.
        

### **Step-by-Step Implementation:**

1. **Enable OCI Audit:**
    
    * Enable OCI Audit for your tenancy. This can be done through the OCI Console or using the OCI CLI.
        
    * Define the audit policy to capture the necessary events (e.g., create, update, delete) without including access-related details.
        
2. **Create an Object Storage Bucket:**
    
    * Set up an OCI Object Storage bucket to store the daily audit logs.
        
    * Define the necessary retention policies based on your compliance requirements.
        
3. **Configure OCI Notifications:**
    
    * Create an OCI Notification topic to send alerts when a new audit log is generated.
        
    * Configure the notification to trigger an event when a new audit record is written.
        
4. **Develop a Cloud Shell Script:**
    
    * Use OCI Cloud Shell to develop a simple script that fetches the daily audit logs from the Object Storage bucket.
        
    * Format the information as required for the daily comprehensive report.
        
5. **Schedule Execution:**
    
    * Set up a cron job within OCI Cloud Shell to automatically run the script at a specific time each day.
        
    * Ensure that the script generates the report for the preceding day's modifications.
        
6. **(Optional) Implement Additional Security Measures:**
    
    * Apply security best practices, such as encryption of stored audit logs, to ensure the confidentiality and integrity of the data.
        

### **Benefits:**

* **Cost-Effective:** This solution uses native OCI services, minimizing the need for external tools or third-party services.
    
* **Automation:** The process is automated, reducing manual effort and ensuring consistency in report generation.
    
* **Scalability:** The solution can scale with your OCI tenancy as it grows, handling an increasing volume of audit logs.
    
* **Audit Trail:** Provides a comprehensive audit trail of all modifications made within the OCI tenancy.
    
* **Retain Historical Data:** Utilizing Object Storage allows for easy retention and retrieval of historical audit logs for compliance purposes.
    

By implementing this solution, you'll have a streamlined and cost-effective approach to obtain detailed daily reports of modifications made within your OCI tenancy.

For cloud events : [https://docs.oracle.com/en-us/iaas/Content/Audit/Reference/logeventreference.htm](https://docs.oracle.com/en-us/iaas/Content/Audit/Reference/logeventreference.htm)

GIT : [https://github.com/ds-kamran/spec](https://github.com/ds-kamran/spec)