This program is a simple task scheduler with the ability to execute various actions at specified times, such as running a program, sending an email, or displaying a message. Let's break down the classes and their functionalities:

-------------------------------------------------------------
1-get_email_data Class:
-------------------------------------------------------------

This class is responsible for collecting email-related information from the user.
It has private member variables for storing the user's email address, password, recipient address, email subject, and email body.
The member functions include:
ConvertToTCHAR: A private function for converting a string to _TCHAR* (a type often used in Windows programming).
App_Pass_Instructions: A private function that provides instructions on how to generate an "App Password" for a Gmail account.
set_user, get_user: Set and get functions for the user's email address.
set_pass, get_pass: Set and get functions for the user's email password.
set_recipient, get_recipient: Set and get functions for the recipient's email address.
set_subject, get_subject: Set and get functions for the email subject.
set_body, get_body: Set and get functions for the email body.

-------------------------------------------------------------
2-EmailSender Class:
-------------------------------------------------------------

This class is responsible for sending emails using the EASendMailObj library.
It has a private member variable of type IMailPtr (an interface pointer to the mail object).
The constructor initializes the mail object and sets a license code.
The member function SendEmail takes the sender's email address, password, recipient's email address, subject, and body as input parameters and sends an email using the configured SMTP settings for Gmail.

-------------------------------------------------------------
3-Task Class:
-------------------------------------------------------------

This class represents a task that can be scheduled in the task scheduler.
It has private member variables for the task name, user-specified execution time (hour, minute, second).
The constructor initializes the task with default values.
The member functions include:
setTaskName: Sets the task name based on user input.
setExecutionTime: Sets the execution time based on user input.
time_wait: Calculates the time difference between the current time and the specified execution time.
display: Displays information about the task.

-------------------------------------------------------------
4-Functions for Executing Actions:
-------------------------------------------------------------

openProgram: Uses the system function to run a specified application.
sendEmailTask: Creates an instance of EmailSender and sends an email using the specified parameters.

-------------------------------------------------------------
5-main Function:
-------------------------------------------------------------

The main function serves as the entry point for the program.
It presents a simple console-based menu for adding tasks, displaying tasks, and exiting the program.
Users can add tasks with various actions, such as starting a program, sending an email, or displaying a message.
The program runs in a loop until the user chooses to exit.
