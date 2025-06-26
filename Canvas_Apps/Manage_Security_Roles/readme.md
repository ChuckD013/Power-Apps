# Power Apps Unmanaged Solution: Security Role Manager

This folder contains an unmanaged Power Apps solution designed to manage users within the Security Roles of your environment.

## Overview

- **Purpose:** Manage Security Roles in the specified Power Platform environment.
- **Requirements:**  
  - User must be a **System Administrator** in the target environment to manage security roles.
  - The app must remain within a solution

## Installation

1. Import the unmanaged solution into your Power Platform environment.
2. Link and/or create the necessary tables

## Data connections

- The following connections are necessary:
  - Canvas Apps (canvasapp), inherent Dataverse table
  - Environments, locally created Dataverse table
  - Security Roles (role), inherent Dataverse table
  - Users (systemuser), inherent Dataverse table

## Local table creation

A local table named Environments must be created in order for the app to work properly across multiple environments.  You could also hardcode the necessary data (App.OnStart) if this will only operate in a single environment.  The following columns are required:
  - Name - Name of the environment (i.e. Development, Test, Production)
  - Environment ID - The ID of the target environment.

## Usage

Upon opening the app, you should see the Security Roles that are contained within the environment you are in.  The environment should be specified directly above the 'Search Roles...' input as well as provide a count of the roles.
  - Start by clicking or searching for a Security Role to view the users therein.
  - Once a security role has been selected, the users listed in that role will then appear to the right.
  - If you need to add a user, search for them in the combobox above the user gallery.  Once you have found the user, clicking on their name will add them to that role.
  - Conversely, if you need to remove a user from the security role, click on the trash icon and that role will no longer be assoicated to them.

---

*More details and usage instructions will be added soon.*
