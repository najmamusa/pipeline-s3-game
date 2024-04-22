# Building a Game with Continious Deployment via AWS CodePipeline and S3 hosting.

## Description
In this project, we go through the steps of uploading code for a meme game onto a github repository of your own, hosting this meme game through an S3 bucket which enables static website hosting. We then create a continuous deployment mechanism through the employment of AWS Code Pipeline which enables automatic deployments of any changes made to the code in the GitHub repo.

## The Game
# Overview
The game is a memory matching game where players click on cards to reveal images. The objective is to find pairs of matching meme images. Successful matches result in the cards disappearing, while unmatched cards are flipped back, challenging the player to remember the locations of different memes.

## Features
- HTML, CSS, and JavaScript: Utilizes basic web technologies.
- Extendable: Easy to add features like scoring, timers, additional cards, and multiplayer capabilities.

# The Deployment Environment
The game's code is deployed and hosted in an AWS S3 bucket configured for static website hosting. This setup allows the game to be accessed from anywhere and ensures fast load times.

# The Deployment Pipeline
Setup
The continuous deployment pipeline is managed by AWS CodePipeline, which automates the steps required to get the latest version of the game from the GitHub repository to the S3 bucket.

# Cost
This project uses AWS services that are eligible for the [AWS Free Tier](https://aws.amazon.com/free/). However, if the usage exceeds the Free Tier limits, charges may apply. It is recommended to monitor usage and shut down resources when not in use to avoid unnecessary costs.

# Step 1: Pushing Code onto GitHub
To get the code for this project, you can easily fork this repo or:
- Download the code files attached to this repository.
- Make a repository dedicated to this project, ensuring it is public.
- You can drag and drop the code files into the repository or push the code to GitHub via Visual Studio Code/Terminal for example.

# Step 2: Create and configure the S3 Bucket
Steps for this step can be found in my previous project repository [here](https://github.com/najmamusa/AWS-S3StaticWebsite/blob/main/README.md). Follow the steps in the readME up until the 'Edit Bucket Policy' section, where you should have your endpoint address ready. **Name your Bucket meme-pipeline for this project**.

# Step 3: Set up the Code Pipeline
- Navigate to the Code Pipeline page by search in the main console.
- Select 'Create Pipeline'.
- For the name, insert 'meme-pipeline'. Choose the V1 option. Choose the Superseded option for the execution mode. Leave the rest of the options as default and navigate to the next page.
- For source, choose 'GitHub Version 2' and select Connect to GitHub.
 ![pipeline 1](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/d2fe754f-f900-43bf-bd97-82bfffe92f0c)
- For the source name, insert 'meme-github-pipeline' and select 'install a new app'.
![pipeline 2](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/ca7d0bbe-ea36-4638-a95e-35f9a9fba553)
- Here, scroll down to repository section and select 'Only selected repositories', choosing the repository you made earlier for this project.
- Back to the source page, for the dropdown titled 'Connection', select our source 'meme-github-pipeline'.
- Below this, under the 'repository name', choose the repository you made earlier.
- Under this section, select the option to 'push in a branch'.
- Select the branch name 'Main'.
- Choose the CodePipeline default option and select Next.
- **Ignore the build page as we will not be using any build like Jenkins**
![pipeline 4](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/5211bd21-c76a-466b-b1f3-49f25de58acd)

# Step 4: Deploy
![pipeline 3](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/26f7084c-8bc0-4897-bd09-78282cbb8d9c)
- From the dropdown select Amazon S3.
- Complete the rest of the page as in the image above.
- Review the options and scroll to the 'Create pipeline' option.
- Well Done! You have now created and deployed your pipeline.
![pipeline 5](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/6fcecc69-2920-4675-8070-769d89b80fd7)
- Navigate to the endpoint address from the properties section of the S3 Bucket, you should now see the meme game site has been deployed WITHOUT needing to upload the code files to the bucket manually!
![pipeline 8](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/c2c6ea00-fc08-41c3-a7e6-9b86105d9477)

# Step 5: Test the Pipeline
- Navigate to your GitHub repository and make a small change in your index.html file, like this example below:
![pipeline 6](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/9f990fb6-01b8-4477-a6d5-51aafc0554e6)
- Commit these changes and return to the deployment page, where we should see an immediate update:
![pipeline 7](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/f6b05565-deed-4620-97a8-1215c946b199)
- Checking the webpage again, you should see the change automatically added:
![pipeline 9](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/bbb82a42-b76f-4f0b-aa81-0625c27c28e1)

You have now successfully created and configured an S3 Bucket, pushed/uploaded code into a GitHub repository, created a Code Pipeline and tested it! 

**Ensure to delete everything you have created so far once you are done with them so you do not accumulate charges on them later on!**
![pipeline 10](https://github.com/najmamusa/pipeline-s3-game/assets/110435863/d5aa5003-fcad-47bc-a474-db7cdd1e5f05)

If you enjoyed this tutorial, give this repo a star!

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
