# 🔄 SDLC recommendations @ Convexity Tech Ltd

This document speaks to the adoption of a recommended standard and approach to software product development, in a way that is both fast, efficient, testable, and scalable.

## Life cycle phases

1. Requirement gathering and analysis
2. Design, architecture, and planning
3. Development / Implementation
4. Testing
5. Deployment
6. Monitoring and performance optimization
7. User documentation


### Requirement gathering and analysis

To kick things off, the first step is to gather and analyse the requirements, this may involve understanding the functional and non-functional requirements as well as the business goals, user needs, e.t.c. The team would collaborate with stakeholders to define the scope of the project and create a clear roadmap with timelines (deliverables) for the project.

* Information about each element to design
* Validating the installation of elements into the application according to the client requirements
* Calibrating the security protocols and performing risk analysis
* A Software Requirements Specification document is meant to be achieved from this phase

#### Recommended tools:
* Cloud collaboration software like miro 
* Simple text editor tool, micro-soft word, notepad, pdf, documents e.t.c


### Version control

Primarily, we use Gitlab as our remote version control system and Git flow as workflow. This workflow is best for projects with a structured release cycle. It introduces two long-lived branches: production for production-ready code, master for the default version, and develop for integrating features. Additional branches like feature, release, and hotfix are used for specific purposes, ensuring a strict and organized development process.


### Design, Architecture, and planning

At this phase a sense of clarity on the general requirements of the project has been attained, therefore high to low-level architecture and system designs can be carried out to further get the developers a clear overview of the system.
In most cases, the entity requirement diagram, systems diagram and software architecture will be a point of reference to fall back on﻿ if things seem to be going off rails.
When it comes to systems design and architecture there are numerous solutions that fit unique problems


* Devise the system design following the SRS document
* Check feasibility with the client's requirements
* All the details of this phase should be added to the Design Document Specification (DDS)
* The document should be shared with the stakeholders and analysts for review


#### Recommendations and tools:
* System and architecture design tools like draw.io  
* Eraser.io﻿ for easy creation, sharing, and collaboration of the DDS and managing project-specific knowledge base.
* Micro-service or Distributed architecture is most favored as a general architectural solution


### Development / Implementation

This phase involves the actual development of the software, or product in accordance with the plans and decisions made in previous phases.
This phase requires strict adherence to the guidelines of good software development ethics and/or standards.
Project setup and programming language and technology stack of choice for the implementation must be thoughtfully and carefully selected, as well as consider developer proficiency in said technology.

#### Recommendations:
* Javascript/Typescript is one of the most used in the organization. 
* Good project setup and clean code practices for easy collaboration, maintainability, and scalability.
* Enforcing TDD (Test Driven Development) to make sure development adheres to functional requirements and core software functionality is being tested as the project evolves.
* Good issue tracking on version control systems such as gitlab(preferred), github e.t.c
* Ensure you log the requests and responses made in methods using logger libraries


### Testing

Thorough testing is crucial to ensure the reliability and functionality of the services. Unit tests, integration tests, and end-to-end tests are performed to verify individual services as well as their interactions. Test automation frameworks, such as Selenium or JUnit, can be utilized. Continuous integration and continuous delivery (CI/CD) pipelines are established to automate the testing and deployment processes.

#### Recommendations:
* CI/CD setup from the development phase to mitigate the likely hood of a potential bug being introduced into the system.
* Make sure specific service test coverages are at least over the 70 to 80 percentile.


### Deployment

Once all the services pass all the tests, they are deployed to the target platform. containerization technologies like Docker and orchestration platforms like Kubernetes are commonly used for managing and deploying micro-services. Infrastructure-as-Code (IaC) tools, such as Terraform or AWS CloudFormation, enable the automated provisioning of infrastructure resources.

#### Recommendations:
* Look into automated provisioning of resources with IaC tools
* Easier to deploy to cloud solutions like Heroku are mostly used


### Monitoring and Performance Optimization

Once the services are live, monitoring tools should be employed to collect data on their performance, availability, and usage. This data helps identify bottlenecks and optimize the services for better efficiency. Logging and error tracking systems, such as ELK Stack or Splunk, provide insights into system and app behavior and aid in debugging.

#### Recommendations:
* Cloud providers like have some monitoring tools; Cloudtrail and Cloudwatch.
* DataDog can be used for a multi-cloud application


### Maintenance and Updates

Services require continuous maintenance and updates to address bugs, security vulnerabilities, and evolving business needs. The team regularly reviews and refines the services based on user feedback and new requirements. Version control and change management processes ensure proper handling of updates while minimizing disruptions.

Agile methodologies like sprints, scrum, or kanban are often followed throughout the SDLC to enable iterative and incremental development. Continuous improvement, collaboration, and regular feedback loops are key principles for a successful software development lifecycle.


### Documentation

Technical code documentation while writing should be neat and like using the following style.

/**
* @brief explain what the function does
* @param ratio this is oxygen to air ratio
* @return state the response expected
*/


User and API documentation should be done using gitbook and any other approved documentation system.






