---
title: "Day 04"
datePublished: Mon Jan 15 2024 02:10:42 GMT+0000 (Coordinated Universal Time)
cuid: clreag3ce000109kuedslbao9
slug: day-04

---

Started my day with the requirement to generate a daily report for OCI resource utilization.

**Requirement:** Project require a daily comprehensive report detailing all modifications made within the Oracle Cloud Infrastructure (OCI) tenancy on the preceding day. Please suggest an optimal approach for accomplishing this task. At this juncture, our focus is solely on obtaining information about any changes, creations, or deletions, without delving into access-related details. 

Proposed Solutions :

**Solution 1:**

Certainly, capturing a daily report of all changes made within the Oracle Cloud Infrastructure (OCI) tenancy is crucial for monitoring and auditing purposes. To achieve this, I recommend leveraging the OCI Audit service, which provides detailed logs of all activities within the tenancy. Below is a step-by-step solution:

Solution: OCI Audit Service for Daily Change Reports

1\. Enable the OCI Audit Service:

Go to the OCI Console.

Navigate to "Identity" -&gt; "Audit" -&gt; "Audit Configuration."

Create a new audit configuration or use the default configuration.

Enable auditing for the desired compartments and services.

2\. Define Audit Policies:

Specify the types of events you want to capture (e.g., Create, Update, Delete) and the target resources (e.g., Compute, Networking).

Define rules based on relevant attributes (e.g., resource type, user, compartment).

3\. Set Up Object Storage for Audit Logs:

Create an Object Storage bucket to store the generated audit logs.

Configure the audit configuration to send logs to this Object Storage bucket.

4\. Configure Notifications (Optional):

Optionally, set up notifications to be alerted when new logs are generated.

This step is helpful for immediate awareness of critical changes.

5\. Generate Daily Reports:

Use OCI CLI, SDKs, or the Console to query the audit logs stored in Object Storage.

Extract the relevant information, such as timestamp, user, action, and resource details.

6\. Automate the Reporting Process:

Develop a script or use existing automation tools to automate the process of querying and generating daily reports.

Schedule the script to run daily, extracting the necessary information from the audit logs.

7\. Store and Distribute Reports:

Store the generated reports in a secure location.

Depending on the preferred format, distribute reports via email, messaging systems, or a designated storage location.

8\. Retention and Compliance:

Define a retention policy for audit logs to comply with data retention requirements.

Regularly review and update audit policies based on changing business needs and compliance standards.

By following these steps, you will establish a comprehensive solution for capturing, storing, and reporting on all changes made within your OCI tenancy. This approach not only meets your requirement for daily change reports but also enhances your tenancy's security and compliance posture.

**Also Multiple Options:**

Certainly! To achieve a daily report of all changes made in the Oracle Cloud Infrastructure (OCI) tenancy, we can explore multiple cost-effective solutions leveraging OCI native services. Here are three viable options:

Option 1: OCI Audit Service with Object Storage

OCI Audit Service:

Leverage the Oracle Cloud Infrastructure Audit service to capture all changes made in the tenancy.

Configure audit policies to monitor the desired resource types and operations (create, update, delete).

Audit events will be generated and stored in the Audit service.

Object Storage:

Create an Oracle Cloud Object Storage bucket to store the audit logs.

Set up a retention policy on the bucket to manage log retention.

Scheduled Job/Script:

Develop a script or use OCI CLI commands to fetch audit logs from the OCI Audit service.

Schedule a daily job (using tools like cron on Linux or Task Scheduler on Windows) to run the script and download the logs.

Upload the logs to the Object Storage bucket.

Reporting:

Implement a reporting mechanism (e.g., using Python, PowerShell, or OCI SDK) to process the downloaded logs and generate a concise daily report.

Store the generated report in the Object Storage bucket.

Option 2: OCI Event Service with Streaming and Functions

OCI Event Service:

Utilize OCI Event service to capture real-time changes within the tenancy.

Create rules to filter events based on resource type and operations.

Streaming Service:

Set up an OCI Streaming service to stream the filtered events in real-time.

Define a stream to store the streaming data.

Serverless Function:

Deploy an OCI Functions (serverless) function triggered by the streaming data.

Write the function logic to process the events and generate a summary of changes.

Object Storage or Notification:

Store the summary of changes in an Object Storage bucket.

Alternatively, trigger a notification (email, webhook) with the summary.

Option 3: Custom Solution with OCI APIs and Functions

OCI APIs:

Utilize OCI APIs (e.g., Identity and Access Management, Resource Manager) to query for changes in the tenancy.

Implement logic to identify new, updated, or deleted resources.

Serverless Function:

Deploy an OCI Functions function to execute the logic for querying and summarizing changes.

Schedule the function to run daily.

Logging and Notification:

Log the summary of changes to a centralized logging solution or write to an Object Storage bucket.

Optionally, send a notification (e.g., email) with the summary.

Cost Considerations:

Option 1 and 2 may incur costs associated with the usage of OCI Audit, Object Storage, Streaming, and Functions.

Option 3, being more custom, may involve lower operational costs but requires development effort.

Evaluate the specific requirements, scale, and cost constraints to choose the most suitable option for your use case.