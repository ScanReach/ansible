# ansible
WARNING: DO NOT UNDER ANY CIRCUMSTANCES INCLUDE ANY CONFIDENTIAL INFORMATION IN THIS REPO. SINCE SSH IS NORMALLY NOT OPEN ON VESSELS, THE JOB RUNS TOWARDS THE HTTPS GIT REPO AND HAS TO BE PUBLIC

Contains a simple, but yet effective way to keep Edge computers updated using ansible pull. The main script local.yml includes pre_tasks to keep package repository and packages updated. To start using we have to run it first, but after this everything should work automatically. It runs every 15 minutes and only if there ha been changes in the repository. Since vessels often operate under low-bandwidth conditions, successful runs are not guranteed, more the opposite. Still strategy is that jobs will complete when conditions allow it.

Script are added in the tasks-folder:

- cron.yml controls the cron jobs
- logrotate.yml set the logrotate config for /var/log/ansible-pull.log
- packages.yml controls which packages will be installed
- users.yml creates an ansible user for running the cron job

More tasks can of course be added.
