# abcd
Part I: Git & GitHub Collaboration (40 Marks)
Scenario: Your development team is building a web-based Apartment Management System to handle tenant registration, maintenance request tracking, visitor logging, and maintenance fee billing. A centralized remote repository named Apartment Management App has been set up on GitHub. Provide the exact Git commands for each scenario:
1.	Set up this codebase on your local machine. [2M]
2.	Verify the remote server connections configured for fetching and pushing code in your project workspace. [2M]
3.	You modified src/main/webapp/index.jsp and created src/main/webapp/complaints.jsp. Inspect the current status of all staged, unstaged, and untracked changes. [2M]
4.	Move your workspace directly into a new working context named feature/tenant-registration using a single operation. [2M]
5.	Determine all local and remote branches in the repository while confirming which branch you are actively on. [2M]
6.	You added src/main/java/com/apartment/servlet/TenantServlet.java. Save this specific file to the repository history with the log note "Add tenant registration servlet". [2M]
7.	You realized src/main/webapp/WEB-INF/web.xml was left out of your latest snapshot. Merge this file into that last snapshot without altering the original message. [2M]
8.	A teammate updated pom.xml on GitHub. Retrieve these remote updates without modifying your local working files. [2M]
9.	Incorporate the latest updates from the remote main branch into your currently active branch. [2M]
10.	Reorder your local feature branch history so that it stems from the tip of the updated main branch. [2M]
11.	Conflicts break your rebase process. Cancel the rebase entirely and return your repository to its state prior to the rebase attempt. [2M]
12.	A faulty validation logic was committed in src/test/java/com/apartment/TenantTest.java. Safely undo the impact of that commit while preserving the commit log history. [2M]
13.	Undo your last commit execution while ensuring all modified changes remain staged in index memory. [2M]
14.	You accidentally committed src/main/resources/db-config.env. Remove this file from project version control while keeping the file saved on your local drive. [2M]
15.	You must switch branches immediately to handle an emergency, but your changes in complaints.jsp are unfinished. Safely store your uncommitted changes without creating a commit record. [2M]
16.	View all stored work snapshots and restore your saved complaints.jsp modifications back to your workspace. [2M]
17.	Inspect the line-by-line differences between feature/tenant-registration and main specifically for src/main/webapp/index.jsp. [2M]
18.	Produce a compact, single-line visual timeline mapping out how project branches have diverged and merged over time. [2M]
19.	Work on feature/tenant-registration is complete. Return to main and bring the feature branch changes into main. [2M]
20.	Upload your updated main branch to GitHub, and verify that your local workspace and the remote repository share the exact same commit point. [2M]
Part II: Maven Java Application Development (40 Marks)
Section A: Project Debugging & Inspection [12 Marks]
Q1. POM Validation & Plugin Debugging [6 Marks]
•	Running mvn validate on the provided pom.xml results in an immediate build failure during project model parsing. Identify the XML schema violation causing this failure, explain why Maven rejects it, and write the corrected <dependency> configuration. (3M)
•	A developer attempts to execute the application locally using mvn tomcat7:run, but Maven fails to execute the goal. Identify why Maven cannot locate and execute this plugin, and provide the complete, corrected <plugin> block. (3M)
Q2. Dependency Resolution & Lifecycle Failures [6 Marks]
•	Executing mvn compile fails because Maven cannot resolve the declared database driver dependency. Identify why artifact resolution fails and write the corrected <dependency> block required for MySQL connectivity. (3M)
•	Executing mvn test-compile fails due to an incomplete dependency declaration in the <dependencies> section. Identify the missing element preventing test compilation and provide the corrected <dependency> block. (3M)
Section B: Deployment, Configuration & Architecture [10 Marks]
Q3. Build Output Analysis [5 Marks]
•	Inspect the provided pom.xml. When mvn clean package is executed successfully, what will be the exact name of the generated web archive file inside the target/ directory? Explain the rule governing this output filename. (3M)
•	Based on the embedded web server plugin configuration, what context path URL would normally be used to access the application upon local server execution? (2M)
Q4. Maven Core Concepts [5 Marks]
•	Differentiate between declaring a plugin inside the <pluginManagement> block versus declaring it directly inside the <plugins> block in pom.xml. (3M)
•	Explain the purpose of the -SNAPSHOT suffix in <version>0.0.1-SNAPSHOT</version> and how Maven handles snapshot artifacts differently from release artifacts during build resolution. (2M)
Section C: Command Line Operations & Custom Libraries [10 Marks]
Q5. Environment Inspection & Debugging Flags [5 Marks]
•	State the exact terminal command used to verify the JDK version detected and utilized by Maven on your machine. (2M)
•	Write the single terminal command required to clean previous build outputs, execute all phases up through packaging, and produce full debug log output for troubleshooting. (3M)
Q6. Local Repository Operations & Dependency Structure [5 Marks]
•	The POM contains a dependency on a vendor library (apartment-analytics.jar) that is not available in Maven Central. Write the full terminal command required to install this JAR into your local Maven cache using the coordinates specified in the POM. (3M)
•	Write the terminal command used to display the complete tree structure of direct and transitive dependencies for this project. (2M)
Section D: Testing Protocols & Dependency Management [8 Marks]
Q7. Test Execution Controls [4 Marks]
•	Specify the standard file path locations where Maven stores: a) Compiled test binary classes. b) Generated JUnit test execution reports. (2M)
•	Write the exact terminal command to execute only a single test class named MaintenanceBillingTest. (1M)
•	Which command-line flag allows a Maven build to complete its packaging phase even if one or more unit tests fail? (1M)
Q8. Dependency Analysis & Scope Management [4 Marks]
•	Write the exact Maven terminal command used to analyze dependency usage and detect unused declared dependencies in your project. (1M)
•	Explain why the javax.servlet-api dependency is configured with <scope>provided</scope> in web applications, and state what problem occurs at runtime if this scope setting is omitted when deploying to Apache Tomcat. (3M)
Part III: Dockerization and Container Management (20 Marks)
Scenario: Containerize the Apartment Management System backend for staging and production deployments.
1.	Download a local working copy of the remote application repository, enter the project directory, and confirm that essential project configuration files exist in your root workspace. [2M]
2.	Write a complete Dockerfile in the root directory to containerize the application using openjdk:17-jdk-slim as the base image, setting /app as the working directory, copying target/apartment-management.jar (or .war), and defining the startup instruction to run the application. [3M]
3.	Build a custom container image named apartmentapp-image from the current working directory. [2M]
4.	Launch a container named apartment-app-container running in the background, mapping host port 8080 to the container's application port 8080. [2M]
5.	Display all currently running containers. [1M]
6.	Display all containers regardless of whether they are running or stopped. [1M]
7.	Enter the running apartment-app-container interactively using a shell session to inspect the system environment. [2M]
8.	Temporarily stop the running apartment-app-container and then restart it. [2M]
9.	Save the state of a container with ID 0e993d2009a1 into a new image named your_dockerhub_username/apartmentapp:v1. [2M]
10.	Authenticate your terminal session with Docker Hub. [1M]
11.	Upload your your_dockerhub_username/apartmentapp:v1 to your public Docker Hub repository. [1M]
12.	Terminate your session and remove stored authentication credentials from the local machine. [1M]
