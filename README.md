# CS-499 ePortfolio

## Enhancement One

For the software engineering category of my ePortfolio, I chose to focus on the Task and TaskService projects from the CS 320: Software Testing, Automation, and Quality Assurance course. Created in February of 2021, these projects aimed to provide create, update, and delete functions for a task program. At the same time, this project incorporated JUnit testing to ensure that the Task and TaskService programs functioned as required by project specifications.   

This project was selected due to the utilization of white box testing, specifically JUnit testing. White box testing allows me to demonstrate my ability to anticipate potential software design vulnerabilities and bugs to enhance the overall security of the software. In this project, JUnit testing is used to ensure that the program functions as anticipated when unexpected input like null, is used. Initially, this project was written in the Java programming language. For this enhancement, I wanted to rewrite this project in Python. This would showcase not only my ability to utilize white box testing to ensure program functionality but also my knowledge of Python. However, unlike the initial project, I incorporated a read function which would give the program complete CRUD functionality that was absent in the initial project. Aside from this, I created additional unit tests which tested against invalid input. Originally, the JUnit tests investigated null values and did not have any tests which tested against the character limits. This artifact was further improved through the inclusion of thorough testing which ensured that invalid inputs, null and those exceeding the character limits, would raise exceptions. 
 
Reflecting on the code review, I had stated that with this artifact I aimed to achieve two course objectives: “Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science” and “Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources”. Through this artifact, I was able to showcase my abilities of meeting these course objectives. Additionally, through this artifact, I was able to reach another course objective: “Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry specific goals”. In the enhancement process of this artifact, I had to utilize the unittest Python module which is a tool used to conduct white-box testing in software development. This ensures that the software meets expectations and project requirements. Simultaneously, the usage of the unittest module showcased my ability to anticipate potential software design vulnerabilities and flaws. The previous version of this project did not include comments that would encourage or influence collaborative environments. In this enhancement, I remedied this issue by incorporating comments which would promote better understanding of the project and further encourage collaboration. 

Through this enhancement, I was able to better my understanding of Python, the unittest module, and white-box testing. It was a challenging yet interesting project to tackle. For this enhancement, it required further research and investigation into Python’s testing modules such as unittest and PyTest. In this investigation, I acquired knowledge of the unittest assert methods and how and when to utilize them. It was also relatively helpful to learn how to interpret the test results and in determining flaws in the program. Aside from this, I had to revisit some Python concepts that were quite puzzling to me in the past. However, through this research process, I was able to better my comprehension of them.  
There were a couple of instances which posed an issue in the development of this project. In the Task Service module, there were if statements which compared the getTaskID values to the taskID:

	if task.getTaskID == taskID:
		#Do something
 
This determined that if the task.getTaskID was equivalent to the taskID variable that it would execute the code in the if statements. The functions that utilized this comparison (remove, display, and update) failed the unittests as it was comparing the task.getTaskID function to the taskID value instead of calling the getTaskID function. Further research determined that the function call was incomplete. I was able to resolve this issue by completing the function call:

	if task.getTaskID() == taskID:
		#Do something
 
In doing so, it allowed the Task Service module to pass its unittests. Another issue I encountered were with the unittests themselves. The following code block instructed the program to expect an exception to be thrown:
 
	with self.assertRaises(Exception):
		taskID = None
      		tk.removeTask(taskID)
      
It aimed to test against invalid input. In this instance, it is testing to ensure that an exception is called for the remove function if an invalid input is used. Further research determined that this was an incorrect usage of assert raises. I was able to remedy this issue like this:

	self.assertRaises(Exception, tk.removeTask(taskID))

This ensured that the exception was raised when the remove function is called. Since the taskID was invalid, the program raised the exception. However, in an instance that the taskID was valid, it would fail the test as the exception would not be raised. 

### Artifact Link:
[Enhancement One Repository](https://github.com/DIParham/Software-Engineering)

### ePortfolio Links:

[Code Review](https://www.screencast.com/t/xoiB2GQ8Jtb7)

[Professional Assessment](https://diparham.github.io/ePortfolio/)

[Enhancement Two](https://diparham.github.io/Data-Structures/)

[Enhancement Three](https://diparham.github.io/Databases/)
