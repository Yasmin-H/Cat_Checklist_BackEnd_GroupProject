# Cat_Checklist_BackEnd_GroupProject

## Project Theme

Our project theme initially began as a Cat Task Manager API but became an Animal Task Manager API. Although a regular to-do-list can suffice by using our
API you can manage your pets daily tasks with a stressfree mind. This project was inspired by Alex having to keep up with his multiple pets.

## API Description

The API allows the user to login and input their animals as well as the tasks associated with each pet.  

### User:
This represents a class which enables users to be added and managed within the database. The user can also have a list of animals.

### Animals:
This represents a class which enables the user to input their animal's name, birthday and the type of animal they own.

### Animal Type: 
This class represents different Animal Types a user can choose from eg Cat, Dog, Hedgehog etc. By having this additional steps, only the relevant associated TaskTypes will be present for the user when setting up a new task.
For example, Tharahan owns a fish which has MAINTENANCE and FEEDING as the available tasks. 

### Task:
This class is where the user is able to input the description of the task, assign a due date, whether it is completed or not and set the priority of the task (HIGH, MEDIUM, LOW) for their chosen pet.

### Task Type: 
This class allows implementation of the TaskTypeEnums which have been pre-listed for the user to select from.

## Relationships
There are 4 one to many relationships:
- One user to many Animals
- One AnimalType to many Animals
- One Animal to many Tasks
- One TaskType to many Tasks

## UML and ERD
![UML](https://user-images.githubusercontent.com/126498385/234849711-ce070932-bb02-4236-960c-da685652c6f8.png)

![ERD](https://user-images.githubusercontent.com/126498385/234849953-0981fac0-65b0-426d-830a-0cea8afb75f6.png)

## Tech Stack
<ul>
<li>Intellij IDEA (JDK 17)</li>
<li>PostgreSQL</li>
<li>Spring Boot</li>
<li>Postico</li>
<li>Postman</li>
</ul>

## SetUp Instructions 
<ol>
<li>Ensure the following are installed on your machine:</li>
<ul>
<li>Intellij IDEA (JDK 17)</li>
<li>PostgreSQL</li>
<li>Spring Boot</li>
<li>Postico</li>
<li>Postman</li>
</ul>

<li> Clone the repository from GitHub. Scroll to the top of this page and click on the green Code button. Ensure SSH is selected and copy the link provided. In your terminal, perform the following command:
  <pre><code>git clone git@github.com:Yasmin-H/Cat_Checklist_BackEnd_GroupProject.git</code></pre> </li>

<li> Create a new PostgreSQL database named 'Cat_Checklist' anywhere in your terminal.</li>
  <pre> <code>createdb Cat_Checklist </code></pre>

<li> Via Intellij IDEA, run the CatChecklistApiApplication and make sure the API is running on port 8080.</li>

<li> Via Postman, create a new collection called Animal Task Manager and add requests using the 'Postman Instructions' provided below.</li>
  
  ## PostMan Instructions 
  ### GET(INDEX)
  #### GET Users - The GET request retrieves all users
  <pre><code> Method: GET
  Endpoint : /users
  URL: http://localhost:8080/users</code></pre>
  
  #### GET Animals -The GET request retrieves all animals
  <pre><code> Method: GET
  Endpoint : /animals
  URL: http://localhost:8080/animals</code></pre>
 
  #### GET Tasks - The GET request retrieves all tasks 
  <pre><code> Method: GET
  Endpoint : /tasks
  URL: http://localhost:8080/tasks </code></pre>
  
  ### GET(SHOW)
  #### GET Users - The GET request retrieves all users
  <pre><code> Method: GET
  Endpoint : /users/{id}
  URL: http://localhost:8080/users</code></pre>
  
  #### GET Animals -The GET request retrieves all animals
  <pre><code> Method: GET
  Endpoint : /animals/{id}
  URL: http://localhost:8080/animals</code></pre>
 
  #### GET Tasks - The GET request retrieves all tasks 
  <pre><code> Method: GET
  Endpoint : /tasks/{id}
  URL: http://localhost:8080/tasks </code></pre>
  
   ### POST(CREATE)
  We will need to use the Request Body to input the details required for each user/animal/task. The request body must be in JSON format in the raw section.
  #### POST Users - This POST request adds a new user to the list.
  <pre><code> Method: POST
  Endpoint : /users
  URL: http://localhost:8080/users
 
 RequestBody example: 
  {
    "name" : "Bob"
  }                   </code></pre>
  
  
  #### POST Animals - This POST request adds a new animal to the list.
  <pre><code> Method: POST
  Endpoint : /animals
  URL: http://localhost:8080/animals
  
  RequestBody example: 
  {
    "userId" : 4,
    "name" : "Felix",
    "birthday" : "2020-05-05",
    "animalTypeId" : 1
  }                    </code></pre>
 
   
  #### POST Tasks - This POST request adds a new task to the list.
  <pre><code> Method: POST
  Endpoint : /tasks
  URL: http://localhost:8080/tasks 
 
 RequestBody example:
  {
    "content" : "cleaning the litterbox",
    "dueDate" : "28.04.2023",
    "priority" : "HIGH",
    "completed" : false,
    "animalId" : 2,
    "taskTypeId" : 3
 }                   </code></pre>
  
  ### PUT/PATCH (UPDATE)
  #### PUT Tasks - Changes all the content for each task id by changing the URL.
  <pre><code> Method: PUT
  Endpoint : /tasks/{id}
  URL: http://localhost:8080/tasks/1 
  
  RequestBody example:
  {
    "content" : "changing the water",
    "dueDate" : "27.04.2023",
    "priority" : "MEDIUM",
    "completed" : true
  }                   </code></pre>
  
   #### PATCH Users - Allows for the username to be edited.
  <pre><code> Method: PATCH
  Endpoint : /users/{id}
  URL: http://localhost:8080/users/1 </code></pre>
  
  ### DELETE (DESTORY)
  #### DELETE User - Will destroy any user by entering the userId in the URL.
  <pre><code> Method: DELETE
  Endpoint : /users/{id}
  URL: http://localhost:8080/users/3 </code></pre>
  
   #### DELETE Animal - Will destroy any animal by entering the animalId in the URL.
  <pre><code> Method: DELETE
  Endpoint : /animals/{id}
  URL: http://localhost:8080/animals/3 </code></pre> 
  
  
  #### DELETE Task - Will destroy any task by entering the taskId in the URL.
  <pre><code> Method: DELETE
  Endpoint : /tasks/{id}
  URL: http://localhost:8080/tasks/3 </code></pre>
  
  ## Dependencies
  <ul>
<li>Spring Data JPA</li>
<li>Spring Web</li>
<li>SpringBoot DevTools</li>
</ul>
  
  ## Collaborators
 <ul>
<li>Thibyaa Mahasivam (GitHub: thibyaa) </li>
<li>Yasmin Haidar (GitHub: Yasmin-H)</li>
<li>Alex Levendis-Takakis (GitHub: alexlt3001)</li>
<li>Tharahan Tharmaraja (GitHub: tharahan04) </li>
</ul>
