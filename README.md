# AWS Project Build a Full End-to-End Web Application with 7 Services


AWS services used in this project:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/c31eea7a-4e2d-4cfb-b764-8e639b97de60)


Architecture:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/3c205241-984c-44dd-9da5-51d7b2591ada)


I created an empty repository in CodeCommit:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/52357000-aab7-4dce-ab24-a30fe248c207)


I added a policy to my IMA user so I can access CodeCommit.
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/9fa4e531-ee5b-4309-bc6c-07f42e043fa5)

I created Git credentials for my IAM user to allow HTTPS connections to CodeCommit: 

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/0dcf381d-b452-4a55-96f5-d40c0be6821b)

I cloned the repository (create an empty folder for future code):

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/59be9298-9b52-45ec-afc0-8446d25503bd)

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/9ff7b4f2-139b-456f-ac4b-1afa9645958b)

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/022a3b9f-742f-4fc8-9735-772fd132b3da)

I used Amplify for hosting:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/ff0faba8-9eb4-493f-8363-c70edc6bd110)

The site deployed:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/edf0f5b8-c787-479f-ac4f-00d6027b0a2f)


I used Cognito for authentication:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/9eb13fe5-b861-4435-aa71-6416575d23b0)


![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/1f96e285-6359-40ba-8eb3-9da6877178d6)


![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/1e970bfb-8af0-4ffb-a061-2d3119e83474)
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/1ee21a7d-e4fd-4151-a154-58e3f93fc3a9)

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/827a87f4-e462-4e0d-b63b-59c65ecaf258)

The Cognito send us an email:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/45910da6-fb64-4fd5-8bbf-b7d257f2cbfa)

The user is gonna reqeuest a ride that will invoke the Lambda function, that will select a unicorn from the fleet and then record that request in the DynamoDB table and then respond to the front end with details about the Unicorn that's being dispatched. 

I setup the DynamoDB table:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/f421223e-d9e3-4362-a0d9-321321aca3d4)


I copy the ARN code and save it for later:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/054b3eb4-e64d-4691-ad5f-714a98d75974)

I create a role for Lambda:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/9cd7afaa-9433-4025-bac2-4272a0f84e42)

choose the policy:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/dedb4642-c0ac-4827-81fb-4f8873f50d2b)


name the role:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/74444df8-dc7a-48b2-a65d-8a420d5524dd)

add additional permissions to write to DynamoDB table:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/ece1e46b-d35e-45f6-9dac-eccd3d9162cb)
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/fc54ae97-1bd8-46a1-a877-76d21f4d6faa)
add ARN:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/46fdeff2-bb95-43a3-b851-e3447a259c7a)

name the policy:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/44152ee3-997b-4b35-9451-8f04a6e5f103)


Create new Lambda function:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/04613c47-2475-41d9-93c6-c8a2c14f63dc)
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/e682219a-4fcc-4e2d-9a59-add5aacf248b)


I put the code from the attachment:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/7384c60d-7e66-4496-bd3c-833e6adc8c74)

Deploy the code and test it:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/5b96eb0e-f5b6-4bc6-bf39-2ef0410765dd)
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/e82ea9d0-2709-40d6-aa0a-25e21daabeae)

we have 1 item in DynamoDB, the unicorn
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/a78fc0d6-99ad-4bed-9648-62a749a3dbfd)
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/bfc473f0-6d73-4f35-a644-ba23788f835c)


To invoke the Lambda function, I use API Gateway. I create  REST API with API endpoint edge-optimized:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/45e4473b-372f-4bd9-aed5-59b20a097736)

We use the Authorizer service to use it along with Cognito:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/7495de81-0415-456f-8a82-5d884f2292a8)

I use Test Authorizer:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/089047b6-5833-4f66-a96c-e0669f0b7abc)


I create a Resource in API Gateway with CORS:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/7ad84248-eb7d-4faf-9ecf-0577028b74ce)

I create a Method POST:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/008cbf6c-f3f1-4700-ac76-4a5ec127204d)

and Deploy the API:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/17acffdc-46d8-42d0-b1eb-874b5f96afe0)

I copy the Invoke URL for later:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/ea28881e-02a3-4367-a9fd-b4905873ac27)

Back in CodeCommit config.js we paste the Invoke URL:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/8d687a5e-8754-4095-a25c-d9a8376bf03e)

and commit the change.

we go to Amplify to deploy:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/e5dac3d1-8813-4807-a278-6f7d0f23acbe)

and now we see a map:

![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/32ff344c-3154-4ab6-94c8-ea6ccbafa9e4)


we can click a location and request a unicorn:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/e6c87ebb-9381-45df-801d-426b9da2ec9a)


a white unicorn is on its way:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/86ac1eb1-8ac4-4bfb-be24-888dbf0d7f1c)


There is a second item in DynamoDB:
![image](https://github.com/redjules/AWS-Project---Build-a-Full-End-to-End-Web-Application-with-7-Services/assets/106017493/d5fa4a26-13fb-487f-aaa4-2ce8be28b68a)






