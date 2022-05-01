# UFABC Manager Core

This project is meant to help UFABC students to deal with all information that is needed to manage during the    
graduation. It is supposed to be the Core structure of three projects in development:

- UFABC Manager Core: responsible for all the main functions, as managing the user information, all UFABC subjects,    
  calculations, etc.
- UFABC Manager API: which calls the services presented in the Core, so we can access them without using directly
  the    
  Core. The only reason to have an API is to test the usage of the three components, and the API wasn't really needed.
- UFABC Manager CLI - represents the application that the user will actually call.

```mermaid graph LR;    
 CLI --> API; API --> Core; Core --?--> Database[User info database]; Core --?--> File[User  info file];  
 ```   

# Project Status

Currently, the project is in development yet. Therefore, any released version is not ready to be used by any user, and
the usage of this project should be done with extreme caution.

# Expected features

`List subjects`: list the available subjects on the latest grade.

- As an additional feature, we should be able to list all grades that are available on a specific course;
- As another additional feature, we should be able to list all grades on a specific course with some restrictions, as:  
  number of credits, type of discipline, etc.

`List courses`: list available courses

- With the list of courses, as an additional feature, we can add some info if desired, as number of credits to be  
  completed and the quantity for each type of discipline.

`Manage user courses`: add, delete and update user subject names and grades.

- As an additional feature, we could calculate the CR (Performance Coefficient) and the CP (Progression Coefficient).
- We could list all user courses so far, with his grades and some information
- We could suggest the next subjects based on:
    - the course that the user has informed to be doing;
    - the subjects that he/she hasn't completed yet;
    - the next ones based on the course recommendations

`Download files`: as a hidden feature to the user, we should be able to download all filed needed to do the other
features, without needing the user to download it. Looks like an unneeded feature but, since the website can cause some
problems sometimes, downloading it can increase the application perceived value a lot.

Since the application will need to persist some info, it was decided that it will persist things based on a Docker MySQL
Database, created by the application.

# Installation

The core application will not be available to be installed by any manners, since the API will use it as a library.
Therefore, to use the Core and its current available features, you should download the API code/binary and run it.

On the other hand, despite not being executable, the usage of the Core code/library will have some main needed
applications:

| Application |   Version    | Optional |
|:-----------:|:------------:|:--------:|
|   Docker    |    Latest    |  false   |
 |    Rust     | Cargo 1.59.0 |  false   |