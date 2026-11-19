## 2.1: Schedule a Deferred User Job

**Prepare the lab environment**

   ```bash
   lab start scheduling-at

1. **Open SSH session to servera as the student user**
   ```bash
   ssh student@servera

2. Schedule job to run 2mins from now. Save output to /home/student/myjob.txt

   2.1. **Pass date >> /home/student/myjob.txt string as the input to at command, job runs two mins from now.**
   ```bash
   echo "date >> /home/student/myjob.txt" | at now +2min

   2.2. **List scheduled job**
   ```bash
   atq

   2.3. **Monitor the deferred jobs queue in real time. After atd daemon executes, job removed from queue. atq updates every 2 sec**
   ```bash
   watch atq

   2.4. **Verify that the contents of the /home/student/myjob.txt file match the output of the date command**
   ```bash
   cat myjob.txt

3. **Interactively schedule a job in g queue that runs at teatime (16:00). The job should print "It's teatime" message to the /home/student/tea.txt file. Append the new messages to the /home/student/tea.txt file**
   ```bash
   at -q g teatime
   
   ```bash
   echo "It's teatime" >> /home/student/tea.txt

   ```bash
   Ctrl+d

4. **Interactively schedule another job in b queue that runs at 16:05. The job should print "The cookies are good" message to /home/student/tea.txt file. Append the new messages to the /home/student/tea.txt file**
   ```bash
   at -q b 16:05
   
   ```bash
   echo "The cookies are good" >> /home/student/cookies.txt

   ```bash
   Ctrl+d

5. **Inspect commands in pending jobs

   5.1.**View job number of pending jobs**
   ```bash
   atq

   >> 2 Fri Feb 17 16:00:00 2023 g student
   >> 3 Fri Feb 17 16:05:00 2023 b student

   5.2. **View commands in pending jobs number 2**
       ```bash
       at -c 2

   5.3. **View commands in pending jobs number 3**
       ```bash
       at -c 3

6. **Remove using arm command and job number
   ```bash
   atrm 2

7. **Verify scheduled job number 2 no longer exists
   ```bash
   atq

   7.2. Return to workstation machine as the student user
   ```bash
   exit

2.2: Guided Exercise: Schedule a Deferred User Job

2.3: Schedule Recurring User Jobs

2.4: Guided Exercise: Schedule Recurring User Jobs

2.5: Schedule Recurring System Jobs

2.6: Guided Exercise: Schedule Recurring System Jobs

2.7: Manage Temporary Files

2.8: Guided Exercise: Manage Temporary Files

2.9: Quiz: Schedule Future Tasks

2.10: Summary
