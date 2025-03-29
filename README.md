# Theatre CSM Live Project: Rentals

## Introduction
In this live project, I spent two weeks working with my peers on developing a content management service for a Theatre company that was built using ASP.NET **MVC** and Entity Framework. My assignment was to track rentals and their condition utilizing CRUD functionality. I've always been very good at problem-solving and time management, and this live project really tested my abilities, as this was more difficult than I anticipated. Despite this, I managed to get through more stories than the Python Live Project, creating many elements for the first time. I understand how to create a good quality product, and the work that goes into it. I was able to utilize important aspects of being a software developer within a real project, including Version Control, Project Management and Azure DevOps.

## M for Models
Before we get to tracking and displaying rental history for this theatre, we have to create the model that will define what we will be tracking and displaying. Four properties are defined in the RentalHistory class, or model.

![model_TheatreRental](https://github.com/user-attachments/assets/2184b6a5-ec37-423e-8898-d7c0928dfafa)

## V for Views
CRUD functionality is used to define our views pages, and these views are Razor pages that use a combination of HTML and C#. Before we get into that, however, let's start with the index page!

  ### Index
  The index view for the rental history homepage displays each rental in a nicely styled table, as you can see here.
  
  ![index-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/2cbe1820-9bcc-4af0-801b-97bca6284c88)
  
  The top of the page starts with the title of this section, Rental History, and a link to create a new entry. In the head of the table, there is a title on the left side and a sorting feature on the right.
  
  ![index1_TheatreRental](https://github.com/user-attachments/assets/83ec22b9-a977-4549-9334-1bdeee79d909)
  
  The user can select multiple ways to sort the table entries by clicking on the dropdown menu and selecting an option. (More on the functionality in [C for Controller](#c-for-controller).)

  ![sorting_menu-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/94ad4e74-5f00-45e6-ad3b-9ff240608d8d)
  
  For the rest of the rows, the first three columns are each one property of the Rental Model. A foreach loop is used to iterate through each entry in order to display them all on the page.
  The first column displays different icons based on whether or not the Rental is damaged. A red X for items that are damaged and a green check for items that are not.
  
  ![index2_TheatreRental](https://github.com/user-attachments/assets/a9b48892-0ec1-4c5a-9c1d-d4afa833d3d8)
  
  The second and third columns are the name and description of each rental. The second column is displayed as a Bootstrap badge, and the third column text is black if the description is for a damaged rental and light gray if the description is for an undamaged rental.
  
  ![index3_TheatreRental](https://github.com/user-attachments/assets/3f274e8d-4616-492d-b90f-b79932917b1b)
 
  ![Index-css1](https://github.com/user-attachments/assets/2285d2ff-b0a9-4fb9-a90c-ba0222cdc3e2)
  ![Index-css2](https://github.com/user-attachments/assets/54d14044-eb8e-4d72-8b46-309f7f3b9ddd)
  
  The final column is a hidden dropdown menu that allows for a user to edit, see details of, or delete a rental. The primary key is used to connect these link to the rental they are in row with. Icons and a divider are added for a nicely styled menu.
  
  ![index4_TheatreRental](https://github.com/user-attachments/assets/9e95d84f-ee87-4622-a942-23af69d8d01a)
  
  The dropdown is not visible until the user hovers over that row. When the dropdown appears, a vertical ellipsis button becomes visible where the user can click to view the dropdown menu.
  
  ![hidden_menu-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/40d500ca-0a55-4da4-b228-10f9865fe548)

  ### C for Create
  The create view is a form where the user can input a new rental entry.
  The 'Create' button has the type attribute of submit, allowing for the form to be submitted to the database and display on the Index page.
  
  ![create1_TheatreRental](https://github.com/user-attachments/assets/cc2beb6f-9f6c-45e4-ad34-521aac9003da)

  jQuery is used to change the label of the DamagesIncurred textbox when the checkbox is clicked on.

  ![create2_TheatreRental](https://github.com/user-attachments/assets/d1047761-5b92-41b7-abb9-5eb941ca9500)

  When the checkbox is not checked, the label will say Notes. When the checkbox is checked, the label will say Damages Incurred.

  ![checkbox_label_change-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/1498f543-5509-40f0-916e-aaf4ad6a7af8)

  *More about the form and the saving to the database*
  
  ### R for Read
  The details view is the webpage that displays all of the information that was provided for that particular rental. The code in this views page is more generic so that each rental can be inputted in, which is done in the [controller](#c-for-controller). The bottom of the page also has links to edit the rental or to go back to the rental history list.

  ![details_TheatreRental](https://github.com/user-attachments/assets/8770baa8-3fd4-40e1-bf06-b8d5ceead472)
  
  ### U for Update

  In order to update each rental listing, we select the edit option in the hidden dropdown menu in the same row of that item. This page looks very similar to the [create](#c-for-create) page.
  Make your changes, and click the 'Save' button to apply those changes. You should see that reflected on the index page.
  If you decide you don't want to make edits to the selected item, you can click 'Back to List' to go back to the index page.
  
  ![edit_page-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/cf220be6-2600-46b1-95fc-00ec0035e90c)

  ### D for Delete
  Of course, you can't create items without the ability to delete them too! Like the [Edit](#u-for-update) page, you can select the hidden dropdown menu in the same row as the item, and click 'Delete'.
  The user will be taken to another page asking if they're sure they want to delete, which they can either click 'delete' as confirmation, or 'back to list' to cancel the delete.
  
  ![delete-page-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/4c9ecaba-5e70-4c8e-ad78-0f0b810b9f0c)

  Here is views page code for the additional delete page. Please refer to the [controller](#c-for-controller) section below to see the functionality of deleting an item.
  
  ![delete](https://github.com/user-attachments/assets/a0c8fd38-9d46-4f12-b41e-8c5beeab8918)

## C for Controller
The controller of an MVC program 'controls' the functions and interactions between the models and views, as well as gives the program the access to a database, which is the case for this Rental Histories module.

To start, we want to create a new instance, or entry, for the database, which will be used throughout this controller.

![controller_TheatreRental](https://github.com/user-attachments/assets/ebd8f4d1-d43d-475c-9ff7-42b9d64aee79)

Next, functionality for the Index page is established. This homepage has a sorting feature that is defined here, and all of the rentals in the database are taken and sorted based on which method the user chooses from the menu. The View is returned, but changes as different sorting options are chosen.
Refer to the [Index](#index) section above to see this in action!

![controller2_TheatreRental](https://github.com/user-attachments/assets/7d1dc6fa-f3d7-43f1-8b6b-814228fcc089)

Each rental in the database also has a details page, where the user can look at each rental on it's own page. In order to access specific rentals, the Id is used to connect all the aspects of that one rental together.
You also see here that when the Create page is opened to create a new rental entry, it will load with the input fields blank. Additional functionality here is developed as you see above in the [Create](#c-for-create) Views page.

![controller3_TheatreRental](https://github.com/user-attachments/assets/453a0aa6-ce59-4b2c-a73e-62a6b640bde2)

Not only can rentals be created, they can be edited and deleted.

When a rental is being edited, the Id is used, like Details, in order to connect all aspects of that one rental together. This inital view is of the item in the create form, but with the input fields filled in with the information of that rental.
The user can make changes to this rental, and when they select the 'Change' button, the database will update this rental with the same ID the new information.

![controller4_TheatreRental](https://github.com/user-attachments/assets/2d5ba345-a136-4c86-95f3-08f8b9f33477)

Again, in order to delete a rental, the Id is used to ensure the deletion of the correct item. If the user clicks the 'Delete' button on the delete confirmation page, the rental will be removed from the Index View, as well as the database entirely.

![controller5_TheatreRental](https://github.com/user-attachments/assets/2c79f02a-7d4a-4db5-ac80-0a5303f4a3ab)

## Other Skills
- Further developed my abilities to debug and optimize code by leveraging my resources and researching best practices.
- Close attention to detail, especially in how I can work on a smaller part of a much larger project. The overall project had four overarching sections, and each section had it's own subsections. The Rental Histories that I was assigned is one of those subsections.
- Strong time management, as I was able to complete what was expected of me earlier than scheduled, allowing me to work further on aspects like the sorting feature on the index page.
- Fluid adaptibility in what works best for each element. For example, using an @HTML.ActionLink() wasn't always the best way to give functionality to a button on a razor page, and a simple <input type='submit'></input> worked just as well, if not better.
