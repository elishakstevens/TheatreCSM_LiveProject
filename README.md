# Theatre CSM Live Project: Rentals

## Introduction
In this live project, I spent two weeks working with my peers on developing a content management service for a Theatre company that was built using ASP.NET **MVC** and Entity Framework. My assignment was to track rentals and their condition utilizing CRUD functionality. I've always been very good at problem-solving and time management, and this live project really tested my abilities, as this was more difficult than I anticipated. Despite this, I managed to get through more stories than the Python Live Project, creating many elements for the first time. I understand how to create a good quality product, and the work that goes into it. I was able to utilize important aspects of being a software developer within a real project, including Version Control, Project Management and Azure DevOps.

## M for Models
Before we get to tracking and displaying rental history for this theatre, we have to create the model that will define what we will be tracking and displaying. Four properties are defined in the RentalHistory class, or model.

![model_TheatreRental](https://github.com/user-attachments/assets/2184b6a5-ec37-423e-8898-d7c0928dfafa)

## V for Views
CRUD functionality is used to define our views pages, and these views are Razor pages that use a combination of HTML and C#.
  ### C for Create
  The create view is a form where the user can input a new rental entry.

  ![create1_TheatreRental](https://github.com/user-attachments/assets/7cf84a82-5002-4942-823a-b3e0b7de3420)

  jQuery is used to change the label of the DamagesIncurred textbox when the checkbox is clicked on.

  ![create2_TheatreRental](https://github.com/user-attachments/assets/d1047761-5b92-41b7-abb9-5eb941ca9500)

  When the checkbox is not checked, the label will say Notes. When the checkbox is checked, the label will say Damages Incurred.

  ***GIF of checkbox and changing label***
  
  ### R for Read
  The details view is the webpage that displays all of the information that was provided for that particular rental. This views razor page is more generic so that each rental can be inputted in, which is done in the [controller](#c-for-controller). The bottom of the page also has links to edit the rental or to go back to the rental history list.

  ![details_TheatreRental](https://github.com/user-attachments/assets/8770baa8-3fd4-40e1-bf06-b8d5ceead472)

  Here is an example details page with one of the test rentals that I created.

  ***Photo of Details Page***
  
  ### U for Update
  
  ### D for Delete
  
  ### Index/Home
  The index view for the rentals homepage displays each rental in a nicely styled table, as you can see here.
  
  ***Photo of rental homepage***
  
  The top of the page starts with the title of this section, Rental History, and a link to create a new entry. In the head of the table, there is a title on the left side and a sorting feature on the right.
  
  ![index1_TheatreRental](https://github.com/user-attachments/assets/83ec22b9-a977-4549-9334-1bdeee79d909)
  
  The user can select multiple ways to sort the table entries by clicking on the dropdown menu and selecting an option. (More on the functionality in [C for Controller](#c-for-controller).)
  
  ***GIF of sorting feature***
  
  For the rest of the rows, the first three columns are each one property of the Rental Model. A foreach loop is used to iterate through each entry in order to display them all on the page.
  The first column displays different icons based on whether or not the Rental is damaged. A red X for items that are damaged and a green check for items that are not.
  
  ![index2_TheatreRental](https://github.com/user-attachments/assets/ae6b34ff-130e-4a24-9b01-94033b78dd0e)
  
  ***CSS for Icons***
  
  The second and third columns are the name and description of each rental. The second column is displays as a Bootstrap badge, and the third column text is black if the description is for a damaged rental and light gray if the description is for an undamaged rental.
  
  ![index3_TheatreRental](https://github.com/user-attachments/assets/3f274e8d-4616-492d-b90f-b79932917b1b)
  
  ***CSS for Rental & Description***
  
  The final column is a hidden dropdown menu that allows for a user to edit, see details of, or delete a rental. The primary key is used to connect these link to the rental they are in row with. Icons and a divider are added for a nicely styled menu.
  
  ![index4_TheatreRental](https://github.com/user-attachments/assets/9e95d84f-ee87-4622-a942-23af69d8d01a)
  
  The dropdown is not visible until the user hovers over that row. When the dropdown appears, a vertical ellipsis button becomes visible where the user can click to view the dropdown menu.
  
  ***GIF of Hidden Dropdown***

## C for Controller
RentalHistories Controller
![controller_TheatreRental](https://github.com/user-attachments/assets/ebd8f4d1-d43d-475c-9ff7-42b9d64aee79)
![controller2_TheatreRental](https://github.com/user-attachments/assets/7d1dc6fa-f3d7-43f1-8b6b-814228fcc089)
![controller3_TheatreRental](https://github.com/user-attachments/assets/453a0aa6-ce59-4b2c-a73e-62a6b640bde2)
![controller4_TheatreRental](https://github.com/user-attachments/assets/2d5ba345-a136-4c86-95f3-08f8b9f33477)
![controller5_TheatreRental](https://github.com/user-attachments/assets/2c79f02a-7d4a-4db5-ac80-0a5303f4a3ab)



## Other Skills
- 
