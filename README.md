Milestone 1: Set up

Fork and Clone this repo.  (Links to an external site.)This is an already working application that we will be translating into a cloud-based application. 
This application uses a database that we have to take into consideration. To facilitate deployment to Render with MongoDB, we'll be using MongoDB Atlas, (Links to an external site.) a cloud-hosted MongoDB service. Follow this short video tutorial (Links to an external site.) to set it up.
Once you've created a cluster and database user on MongoDB Atlas, update the _config.js file. Replace <USERNAME> and <PASSWORD> to have the username and password for the user you created.

Milestone 2: Basic pipeline. 

First, notice that the repository does not seem to have tests. No worries, let’s build our pipeline. Do make sure that you have a JenkinsFile with the required instructions:
Your pipeline should trigger automatically whenever you push a new change to your repository. 
It should make sure that all required software is available. This is on you to figure out what they are, but you are familiar with the project so we believe it won’t be too challenging. npm install is a useful feature here.
It should deploy to Render - recall that you can start the server using node server. 
Make a change to the landing page of the website, and add a big “MILESTONE 2” to the site. This should be clearly visible. Push all your changes, and make sure that the website you see through Render shows MILESTONE 2
 

Milestone 3: Tests.

Turns out the repository did have tests, just in a different branch named test. Switch to the test branch and see that tests are available. You can run them using npm test 
Test results should look like this locally: 
darkroom_test.png
Merge the test branch with your main branch, and update your JenkinsFile so that your pipeline executes the tests. As with the work-along project, you should send an email in your if the tests fail. 
Make a change to the landing page of the website, and add a big “MILESTONE 3” to the site. This should be clearly visible. Push all your changes, and make sure that the website you see through Render shows both MILESTONE 2 and MILESTONE 3

