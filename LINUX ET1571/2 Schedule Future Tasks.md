## 2.1: Schedule a Deferred User Job

1. **Prepare the lab environment**

   ```bash
   lab start scheduling-at

2. **Open SSH session to servera as the student user**
   ```bash
   ssh student@servera

3. **Pass date >> /home/student/myjob.txt string as the input to at command, job runs two mins from now.**
   ```bash
   echo "date >> /home/student/myjob.txt" | at now +2min

4. **List scheduled job**
   ```bash
   atq

5. **Monitor the deferred jobs queue in real time**
   ```bash
   watch atq

6. **Verify that the contents of the /home/student/myjob.txt file match the output of the date command**
   ```bash
   cat myjob.txt

7. **Interactively schedule a job in the g queue that runs at teatime (16:00). The job should print It's teatime message to the /home/student/tea.txt file. Append the new messages to the /home/student/tea.txt file**
   ```bash
   at -q g teatime
   
   ```bash
   echo "It's teatime" >> /home/student/tea.txt

   ```bash
   Ctrl+d

2.2: Guided Exercise: Schedule a Deferred User Job

2.3: Schedule Recurring User Jobs

2.4: Guided Exercise: Schedule Recurring User Jobs

2.5: Schedule Recurring System Jobs

2.6: Guided Exercise: Schedule Recurring System Jobs

2.7: Manage Temporary Files

2.8: Guided Exercise: Manage Temporary Files

2.9: Quiz: Schedule Future Tasks

2.10: Summary
