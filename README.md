# AWS Cloud Cost Optimization - Identifying Stale Resources

## Identifying Stale EBS Snapshots

 We'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

### Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

***Step 1***


Create an EC2 instance

![image](https://github.com/user-attachments/assets/9e5f70a6-872b-4fd5-bb8b-54b210124b7d)

***Step 2***

Create a snapshot for the volume which is stale and not used.


![image](https://github.com/user-attachments/assets/99c53b85-2708-4333-b3a9-4f1b2a765919)

***Step 3***

Create a lambda function and write the script accordingly that which delete the EBS snapshots if not in use, you can modify these scripts as you can.

***Step 4***

Once you create the lambda function, it will show an error because you haven't attatched the policies.

![image](https://github.com/user-attachments/assets/ca2fc1c0-4ae1-41e3-a714-27cac00e6b25)


***Step 5***

Attatch the policies accordingly to your need.

![image](https://github.com/user-attachments/assets/05e4d5fe-eb22-4a27-8314-c5eb8a0dafe8)


![image](https://github.com/user-attachments/assets/967409b3-d9c3-48d2-8724-73091c579c98)


***Step 5***

Once you attatch the policies, deploy and run the code in lambda function and you will get result as-

















