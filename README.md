<h2>Tools of the trade: Linux and SQL </h2>

In the course, I gained foundational knowledge about operating systems, Linux communication through commands, and Structured Query Language (SQL) for database querying. The curriculum introduced Linux's role in cybersecurity, delving into its architecture and prevalent distributions. We emphasized proficiency in the Linux shell as a means of interacting with the system. My focus included understanding Linux's security application, architecture, common distributions, shell-based interaction, and navigating and managing the file system through Bash commands. Authentication, authorization, and file permission management were central themes.

Moreover, the course equipped me with SQL proficiency for effective database communication. I gained expertise in querying databases, filtering results, and utilizing SQL to combine tables. The emphasis was on SQL's security applications, relational database structure, query formulation, filtering, and utilizing joins for table combinations. This comprehensive curriculum significantly improved my skills as a cybersecurity analyst.
 

<h4>Project Description:</h4>

The research team at an organisation is required to update the file permissions for specific files and directories within the `projects` directory. The current permissions do not align with the appropriate level of authorization that should be granted. Verifying and updating these permissions will contribute to maintaining the security of their system. To successfully accomplish this task, I executed the following actions:

Check file and directory details:

The provided code exemplifies the utilisation of Linux commands to ascertain the current permissions assigned to a particular directory within the file system.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/9883ccdc-a9af-4fa5-a82b-5c0f9558576f)

The screenshot depicts the command inputted in the first line, while the subsequent lines exhibit the corresponding output. The provided code retrieves and displays the complete list of contents within the projects directory. I utilised the `ls` command with the `-la` option to generate a comprehensive listing of the file contents, including hidden files. The command output reveals the presence of a single directory named `"draughts,"` a hidden file named `".project_x.txt"` and a total of five additional project files. The 10-character string displayed in the first column denotes the permissions assigned to each file or directory.

Describe the permissions string

The 10-character string can be analysed to ascertain the authorised individuals who have access to the file and the precise permissions granted to them. The following is a list of the characters and their corresponding representations:

- The 1st character: The character in question serves as a file type indicator and can be either a lowercase letter `"d"` or a hyphen `(-)`. If the letter is `"d,"` it indicates that it represents a directory. If the character is a hyphen `(-)`, it indicates that the file is a regular file.

- The 2nd to 4th characters in the file permissions indicate the user's read `(r)`, write `(w)`, and execute `(x)` permissions. If one of the characters in question is a hyphen `(-)`, it signifies that the user does not have permission for that particular action.

- The characters in the 5th-7th positions represent the permissions assigned to the group, specifically the read `(r)`, write `(w)`, and execute `(x)` permissions. If one of the characters in question is a hyphen `(-)`, it signifies that the permission in question is not granted for the group.

- The characters in positions 8 to 10 represent the permissions for other users, specifically the read `(r)`, write `(w)`, and execute `(x)` permissions. This owner type encompasses all users on the system, excluding the user and the group. If one of the characters in question is a hyphen `(-)`, it signifies that this permission is not granted for others.

An instance of file permissions can be observed in `project_t.txt`, where the permissions are denoted as `-rw-rw-r--`. The presence of a hyphen `(-)` as the first character in the file name `project_t.txt` signifies that it is a file rather than a directory. The presence of the character `'r'` in the second, fifth, and eighth positions denotes that the permissions for `user`, `group`, and `other` allow for read access. The third and sixth characters in the permission string correspond to the write permissions for the user and group, respectively. The `project_t.txt` file does not have any users with execute permissions.

Change file permissions

The organisation has made the decision to restrict write access to their files from others. In order to adhere to the requirements, I consulted the file permissions that I had previously provided. Based on my assessment, it is necessary to revoke the write access for other users on `project_k.txt`.

The subsequent code exemplifies the utilisation of Linux commands to accomplish this task.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/029d96df-08af-424a-9338-1d77171bc6f7)

The screenshot depicts the input commands in the initial two lines, while the subsequent lines showcase the output generated by the second command. The `"chmod"` command is used to modify the permissions of files and directories. The initial parameter specifies the desired permissions to be modified, while the subsequent parameter designates the specific file or directory. In this example, the write permissions for the `"project_k.txt"` file were revoked from the `"other"` user. Subsequently, I utilised the command `"ls -la"` to assess the modifications I had implemented.

Chnage file permission on a hidden file

The research team at our organisation has recently archived `project_x.txt`. The project administrators have specified that write access should not be granted to any individuals. However, read access is to be provided to both the user and the group. 

The code provided below illustrates the utilisation of Linux commands to modify permissions:

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/a9b4845b-c124-435d-94cb-837b03402f5a)

The screenshot depicts the input commands entered in the first two lines, while the subsequent lines exhibit the output generated by the second command. I am aware.The file named `"project_x.txt"` is considered hidden due to its file name convention, as it begins with a period `(.)`. In this particular instance, I have revoked the write permissions from both the user and the group, while simultaneously granting read permissions to the group. I have revoked the write permissions from the user by utilising the u-w command. I proceeded to revoke the write permissions from the group using the command `g-w`, and subsequently granted read permissions to the group using the command `g+r`. 

Change directory permissons

Our organization's access permissions dictate that only the user `researcher2` should be granted access to the draughts directory and its associated contents. This implies that only `researcher2` should possess the authority to execute permissions.

The code provided below showcases the utilisation of Linux commands to modify permissions:

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/84252159-a933-441b-95f8-9ffeb404eacb)

The screenshot depicts the commands I inputted in the first two lines, while the subsequent lines showcase the output of the second command. Based on my earlier findings, it was determined that the group possessed execute permissions. Consequently, the chmod command was employed to eliminate said permissions. The user `researcher2` already possessed the necessary execute permissions, thus there was no requirement to include them.

Summary: I have modified various permissions in order to align the level of authorization with the desired standards set by my organisation for files and directories within the projects directory. To begin, the initial step involved utilising the command `"ls -la"` to examine the permissions assigned to the directory. This information influenced my decision-making process in the subsequent stages. I proceeded to utilise the chmod command on multiple occasions in order to modify the permissions of both files and directories.

<h3>Applying Filters to SQL queries</h3>

<h4>Project description:</h4>

Our organisation is currently engaged in efforts to enhance the security of our system. My responsibility entails ensuring the safety of the system, conducting thorough investigations into potential security issues, and promptly updating employee computers as necessary. The subsequent steps illustrate the utilisation of SQL with filters to execute security-related tasks.

Retrieving after hours login attempts

A security incident of potential nature transpired outside of regular business hours, specifically after 18:00. It is imperative to conduct an investigation into all unsuccessful login attempts made outside of regular business hours.

The provided code exemplifies the implementation of a SQL query designed to filter for unsuccessful login attempts that took place outside of regular business hours.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/e4c30745-254f-40e9-9687-3640b1425a3c)

The initial section of the screenshot depicts the query I have executed, while the subsequent section showcases a partial excerpt of the resulting output. This query is designed to filter and retrieve records of failed login attempts that took place after 18:00. To begin, I initiated the process by retrieving all data from the `log_in_attempts` table. I utilised a `WHERE` clause in conjunction with an `AND` operator to apply filtering criteria to my results. Specifically, I restricted the output to include only login attempts that took place after 18:00 and were deemed unsuccessful. The initial condition is `login_time > '18:00'`, which serves to filter the login attempts that took place after 18:00. The second condition is `success = FALSE`, which is used to filter and identify the failed login attempts. 

Retrieve login attempts on specific dates

An incident of a suspicious nature took place on May 9, 2022. Please conduct an investigation into any login activity that occurred on May 9, 2022, or the preceding day.

The provided code exemplifies the implementation of a SQL query designed to filter login attempts based on specific dates.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/30f158b6-2b81-4b43-a99b-f391ad0e745e)

The initial section of the screenshot displays the query I executed, while the subsequent section showcases a partial excerpt of the resulting output. The following query retrieves all login attempts that took place on either May 9th, 2022 or May 8th, 2022. To begin, I initiated the process by executing a query to retrieve all data from the `log_in_attempts` table. Subsequently, I applied a `WHERE` clause utilising an `OR` operator to refine the output of my results, exclusively displaying login attempts that transpired on either May 9th, 2022 or May 8th, 2022. The initial criterion is `login_date = '2022-05-09'`, which serves to filter logins that occurred on May 9, 2022. The second condition pertains to the login_date field, specifically filtering for logins that occurred on May 8, 2022.

Retrive login attempts outside of Mexico

Upon conducting an analysis of the organization's login attempt data, it has come to my attention that there may be a concern regarding the login attempts originating from locations outside of Mexico. These login attempts warrant further investigation.

The provided code exemplifies the implementation of a SQL query designed to filter login attempts that have taken place outside the geographical location of Mexico. 

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/035bde15-7e99-4f4e-b2c8-a855a5f3d4ea)

The initial section of the screenshot displays the query I have executed, while the subsequent section showcases a partial excerpt of the resulting output. This query retrieves all login attempts that have taken place in countries other than Mexico. To begin, I initiated the process by executing a query to retrieve all data from the `log_in_attempts` table. Subsequently, a `WHERE` clause was employed, utilising the `NOT` operator to selectively filter out countries excluding Mexico. I utilised the `LIKE` operator with the pattern `MEX%` to perform the matching operation, as the dataset contains representations of Mexico as both `MEX` and `MEXICO`. When the percentage sign `(%)` is used in conjunction with the `LIKE` operator, it serves as a wildcard character that can represent any number of unspecified characters. 

Retrieve employees in Marketing 

The initial section of the screenshot displays the query I have executed, while the subsequent section showcases a partial excerpt of the resulting output. This query retrieves all login attempts that have taken place in countries other than Mexico. To begin, I initiated the process by executing a query to retrieve all data from the log_in_attempts table. Subsequently, a WHERE clause was employed, utilising the NOT operator to selectively filter out countries excluding Mexico. I utilised the LIKE operator with the pattern MEX% to perform the matching operation, as the dataset contains representations of Mexico as both MEX and MEXICO. When the percentage sign (%) is used in conjunction with the LIKE operator, it serves as a wildcard character that can represent any number of unspecified characters. 

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/4931d881-f904-4149-bdfe-e92f098412d6)

The initial section of the screenshot displays the query I executed, while the subsequent section showcases a partial excerpt of the resulting output. This query retrieves a list of all employees who are currently assigned to the Marketing department located in the East building. Initially, I began by retrieving all the data from the `employees` table. Subsequently, a `WHERE` clause was employed, utilising the logical operator `AND`, to effectively filter employees based on their affiliation with the Marketing department and their location within the East building. I utilised the `LIKE` operator with the pattern `"East%"` to perform a matching operation. This was done in order to identify data in the `office` column that corresponds to the East building, along with its specific office number. The initial criterion involves the `department = 'Marketing'` segment, which serves to narrow down the selection to employees belonging to the Marketing department. The second condition pertains to the `office` field, specifically using the `LIKE` operator with the `'East%'` pattern. This condition serves to filter employees who are located in the East building.

Retrieve employees in Finance or Sales

The machines utilised by employees in the Finance and Sales departments are also in need of updating. Due to the requirement for an alternative security update, it is necessary to obtain employee information exclusively from the following two departments.

The provided code showcases the implementation of a SQL query designed to filter employee machines based on their department affiliation, specifically targeting employees in the Finance or Sales departments.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/9772dd69-9ae4-402a-9be6-3ae5626c1ea3)

The initial section of the screenshot displays the query I have executed, while the subsequent section showcases a partial excerpt of the resulting output. This query retrieves a list of all employees who are currently assigned to the Finance and Sales departments. Initially, I began by retrieving all data from the `employees` table. Subsequently, a `WHERE` clause was employed, utilising the `OR` operator, to selectively filter employees belonging to the Finance and Sales departments. I utilised the `OR` operator instead of the `AND` operator in order to include all employees who are affiliated with either department. The initial condition is `department = 'Finance'`, which serves to filter employees belonging to the Finance department. The second condition is `department = 'Sales'`, which filters for employees from the Sales department.


Retrieve all employees not in IT

Our team is required to implement an additional security update for employees who are not part of the Information Technology department. In order to proceed with the update, it is necessary to gather relevant information pertaining to the employees in question.

I would like to present the process I followed to develop a SQL query that effectively filters employee machines based on employees who are not part of the Information Technology department.

![image](https://github.com/clintonsenaye/ClintonSenaye/assets/57267374/9918f9de-54e4-44e1-9c61-5a7fe2508f46)


The initial section of the screenshot displays my query, while the subsequent section showcases a segment of the output. The query retrieves a list of employees who are not currently assigned to the Information Technology department. Initially, I began the process by executing a query to retrieve all the data from the `employees` table. Subsequently, a `WHERE` clause was employed, utilising the `NOT` operator, to effectively filter out employees who are not associated with the specified department.

Summary

I have implemented filters in SQL queries to retrieve targeted data regarding login attempts and employee machines. I utilised two distinct tables, namely `log_in_attempts` and `employees`. I employed the `AND`, `OR`, and `NOT` operators to selectively filter the requisite information for each task. I utilised the `LIKE` operator along with the percentage sign `(%)` wildcard to effectively filter and identify patterns.
