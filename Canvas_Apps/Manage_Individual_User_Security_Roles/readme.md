
# Power Apps Unmanaged Solution: Security Role User Manager

If you dislike drilling down through the environment settings items in the Admin center to manage a user's Security Roles, this app is for you!  This folder contains an unmanaged Power Apps solution designed to manage an individual user's Security Roless.

## Overview

- **Purpose:** Manage Individual User Security Roles in the specified Power Platform environment.
- **Requirements:**  
  - User must be a **System Administrator** in the target environment to manage security roles.
  - The app must remain within a solution

## Data connections

- The following connections are required:
  - Canvas Apps (canvasapp), inherent Dataverse table
  - Environments, locally created Dataverse table
  - Security Roles (role), inherent Dataverse table
  - Users (systemuser), inherent Dataverse table

## Installation

1. Import the unmanaged solution into your Power Platform environment.
2. Link and/or create the necessary tables

## Local table creation

A local table named Environments must be created in order for the app to work properly across multiple environments.  You could also hardcode the necessary data (App.OnStart) if this will only operate in a single environment.  The following columns are required:
  - Name - Name of the environment (i.e. Development, Test, Production)
  - Environment ID - The ID of the target environment

## Usage

Upon opening the app, you should see a user gallery on the left that shows all of the users in your environment.  The environment should be specified directly above the 'Search User...' input as well as provide a count of the Users in the environment.  
*Note: Keep in mind this count will only match that of the gallery so if your environment has more users than the data row limit set by the app, the full count will not appear until you have scrolled through all of the users.*

  - Start by clicking or searching for a user to view their assigned Security Roles.
  - Once a user has been selected, the assigned Security Roles will appear under Assigned Roles, to right.
  - If you need to add a Security Role, search for it in the Available Roles.  Once you have found the role you want to assign, clicking on the role will associate it to their account.
  - Conversely, if you need to remove a user's role, clicking on the role under Assigned Roles will unassociate that role from their account.
  - There is a button in the app but it is not directly interacted with since that code is used multiple times; it operations like a function.  I left it visible so you could see all of the app controls.  It is used to create the collections of the necessary Security Roles so the galleries can display the proper items.  
