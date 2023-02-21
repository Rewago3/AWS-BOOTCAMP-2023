# Week 0 — Billing and Architecture
### Install and Verify AWS CLI
Installed AWS CLI using Gitpod.  By modifying .gitpod.yml we can launch AWS CLI whenever we open Github repository via Gitpod. Initially hadn't saved my AWS credentials in Gitpod so that they can persist whenever we open new Gitpod workspace. Rectified by using ex:gp env AWS_DEFAULT_REGION="ca-central-1".

### Create a Budget
Created a budget and budget alarm using AWS Management Console as well as AWS CLI.
Got an error when creating budget with following command 
aws budgets create-budget \
    --account-id $AWS_ACCOUNT_ID \
    --budget file://aws/json/budget.json \
    --notifications-with-subscribers file://aws/json/budget-notifications-with-subscribers.json
    
Succeeded in creating one by giving account id directly eg --account-id 011557190811

![image](https://user-images.githubusercontent.com/123596308/220265938-9d687eb0-8986-4dba-a170-c708a02e55d0.png)

### Recreate Logical Architectural Deisgn

