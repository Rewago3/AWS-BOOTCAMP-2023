# Week 3 — Decentralized Authentication

#### Create User Pool and implement Custom Sign in Page.

Got stuck on this one. Created User pool in AWS Cognito and tried to implement the custom sign in Page. I tried so many times, but just could not connect to AWS Cognito from crudder app. 

First on opening the gitpod this is the error I got.

![image](https://user-images.githubusercontent.com/123596308/230803379-1ed269bb-aac2-4f81-9963-512c00fb42db.png)

On googling found -
The react-scripts: command not found error mainly occurs if the dependencies are not installed or if the package-lock.json is corrupted.

After many attempts, looks like I missed out the  pipe character | in gitpot.yml
 
- name: react-js
    command: |
      cd frontend-react-js
      npm i
      
On attempting to Sign in to crudder, would always get the error

![image](https://user-images.githubusercontent.com/123596308/230804255-167d43e6-6343-47a7-afc9-fcf8f814e18d.png)

Always got the authentication error. On inspecting would get

![image](https://user-images.githubusercontent.com/123596308/230804341-18588d17-f786-4be2-8443-0732c60bb700.png)

It was really hard to conclude what was really causing the authentication error. 
I tried and followed the instructions 2/3 times, just to see if i hadn't missed anything.

I went ahead and thought i will try to skip this and try week 4. Somewhere in week 4- RDS Postgres, i ran in to the same problem.
Finally, i gave it on more try.(From the begining try -https://www.youtube.com/watch?v=9obl7rVgzJw&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=40&ab_channel=ExamPro)

Found out this is the silly mistake I made-Cursing myself

In docker-compose.yml file all the REACT APP AWS COGNITO env variables
REACT_AWS_PROJECT_REGION:
REACT_APP_AWS_COGNITO_REGION:
REACT_APP_AWS_USER_POOLS_ID:
REACT_APP_CLIENT_ID:
were in the backend-flask:
    environment:
    
On changing and placing them in 

frontend-react-js:
    environment:
 I was able to authenticate and complete the rest of the week 3 assignments.
 Phew, happy to have completed at last.(Almost gave up on this)
 



