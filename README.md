Set up Jenkins to automatically build and test code changes from a GitHub repository using a Jenkinsfile. Ensure that the Git Flow branching model is applied to manage the development process.
Tools Needed:
Jenkins
GitHub account
Git installed on the Jenkins server
Task Items:
Prepare GitHub Repository:
1.1 Create a new GitHub repository or select an existing one.
1.2 Initialize the repository with a README.md, and ensure the repository contains at least two branches:
develop for ongoing development.
master (or main) for stable releases.
1.3 Apply the Git Flow model:
Install Git Flow tools if not already installed.
Initialize Git Flow in your repository with default branch names.
1.4 Add a Jenkinsfile to your repository in the root directory. Start with a simple pipeline
Configure Jenkins:
2.1 Install the necessary plugins in Jenkins if not already available, such as Git and Pipeline.
2.2 Configure Jenkins to connect to GitHub:
Go to "Manage Jenkins" > "Manage Plugins" > "Available" and install "GitHub Integration Plugin".
Set up credentials in Jenkins for GitHub (username and token).
2.3 Create a new pipeline job:
Select "New Item", name your pipeline (e.g., "GitHub Pipeline"), and choose "Pipeline" as the type.
In the pipeline configuration, select "Pipeline script from SCM" and choose "Git" as the SCM.
Enter the repository URL and credentials.
Specify the branch to build (e.g., */develop).
Implement Webhooks for Continuous Integration:
3.1 In GitHub, go to your repository settings and select "Webhooks".
3.2 Add a new webhook:
Payload URL: http://<your-jenkins-url>/github-webhook/
Content type: application/json
Select "Just the push event".
Ensure the webhook is active.
3.3 With the webhook, Jenkins will trigger a new build every time changes are pushed to the connected branch.
Testing and Validation:
4.1 Push a change to the develop branch of your GitHub repository.
4.2 Verify that Jenkins automatically triggers a build and processes according to the steps defined in the Jenkinsfile.
4.3 Check the output in Jenkins to ensure the build and test stages are executed successfully
