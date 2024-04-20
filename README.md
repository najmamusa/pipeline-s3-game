# Building a Game with Continious Deployment via AWS CodePipeline and S3 hosting.

The content of this repo and the following project takes inspiration from the following [YouTube video](https://youtu.be/biYVW1TMYAU).

## Description
In this project, we go through the steps of uploading code for a meme game onto a github repository of your own, hosting this meme game through an S3 bucket which enables static website hosting. We then create a continuous deployment mechanism through the employment of AWS Code Pipeline which enables automatic deployments of any changes made to the code in the GitHub repo.

## The Game
A simple memory matching game.  The user clicks two cards (images of memes) to try to match them.  If there's a match, the cards disappear from the board.  If there's no match, the cards are flipped back to their blank side so the user can try again.

The game consists of HTML, CSS and JavaScript.

Ideas for additional features:
- A scoring mechanism
- A timer
- Add additional cards
- Multi-player capabilities so you can compare scores 

## The Deployment Environment
The code will be deployed and hosted in S3.

## The Deployment Pipeline
The pipeline is created using AWS Code Pipeline.  The pipeline pulls the code from GitHub, and deploys it to S3 whenever a change is detected in the code.

## Cost
All services used are eligible for the [AWS Free Tier](https://aws.amazon.com/free/).  However, charges will incur at some point so it's recommended that you shut down resources after completing this tutorial.
