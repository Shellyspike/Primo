# Package Description: Primo.ActiveDirectory

The **Primo.ActiveDirectory** package provides a set of components for interacting with Active Directory Domain Services, enabling the creation, deletion, and configuration of users, groups, and computers.

## Overview

**Primo.ActiveDirectory** is a powerful tool for interacting with Active Directory, allowing the automation of user, computer, and group account management. The library provides a convenient interface for performing administrative tasks, including creating, deleting, and modifying the properties of objects within a domain environment.

## Getting Started Instructions

To install the **Primo.ActiveDirectory** package, use the Dependency Manager in Primo RPA Studio or visit [NuGet.org](https://www.nuget.org/).

### Installation Steps

1. **Open the Dependency Manager:**
   - From the main menu of Primo RPA Studio, select `Dependency Management`.
   - Or right-click on the project panel and select "Dependencies" from the context menu.

2. In the opened window, go to the **NuGet.org** section and enter **Primo.ActiveDirectory** in the search bar.

3. Click the funnel icon to display the list of available libraries. Find **Primo.ActiveDirectory** and click **Install**.

4. Click **Save**.

5. In the modal window that appears, click **Install** and then **Close** to complete the installation. The package will be added to your project.

## Documentation

For more detailed information on configuring and using **Primo.ActiveDirectory**, visit the [documentation on our website](https://docs.primo-rpa.com).

## Library Functionality

The library includes the following key elements:

1. **Active Directory connection**

2. **Computers**:
   - Add computer to group
   - Set computer status
   - Get computers in group
   - Get computer status
   - Join computer to domain
   - Computer exists
   - Create computer
   - Delete computer
   - Remove computer from group
   - Unjoin computer from domain

3. **Groups**:
   - Add group to group
   - Group exists
   - Create group
   - Delete group
   - Remove group from group

4. **General**
   - Update object properties
   - Rename object
   - Move object
   - Get objects by filter
   - Get objects by LDAP filter 
   - Get object properties
   - Get object unique name
   - Is object member of group

5. **Users**
   - Add user to group
   - Change user password
   - Set user status
   - Get password expiration date
   - Get user expiration date
   - Get user groups
   - Get users in group
   - Get user status
   - Force password change
   - Validate user credentials
   - User exists
   - Create user
   - Remove user from group
   - Delete user
   - Set user expiration date
   
To use an element, simply drag it into the workspace of your Primo RPA Studio project.

## Usage Examples of Primo.ActiveDirectory

An RPA project that teaches how to work with the library's components is available on the [Learning](https://github.com/PrimoRPA/Learning) page:

1. Download the archive containing all the learning materials.
2. Extract the archive and open the **ActiveDirectoryExamples** project in Studio.
3. Select the appropriate process file (`*.ltw`) to view and explore.

## General Properties

The following properties are common across multiple elements and are defined under the **General** section:

- **Continue on exception**: The script will continue running even if an error occurs during the execution of the element.
- **Disable logging**: Allows disabling logging in the console (only for this element). This is useful, for example, if the element handles confidential data. There is also an option to enable/disable logging centrally for all new elements added to the project. To do this, go to `File > Settings > General > Elements` and set the desired value in the `Disable logging for new elements` checkbox.
- **Name**: The name of the element, which is displayed in its header and in the log. For convenience, the element name can be changed within the process, for example, when multiple identical components are used.
- **Screenshot on error**: A screenshot will be taken if an error occurs.
- **Screenshot on finish**: Allows taking a screenshot upon the element's completion. All screenshots are saved in the `.Screenshots` folder, which is automatically created inside the process folder.
- **Wait after (ms)**: Pause after the element is executed.
- **Wait before (ms)**: Adds a pause before the element is executed.

## Active Directory Connection

All the components listed below are added to the workspace within the **Active Directory connection** element. This element establishes a connection with the Active Directory server and includes the following properties:

1. **Connection**:
   - Login — the format should be specified as `domain\login`.
   - Password
   - Password (encrypted)
   - Port
   - Server — the domain controller server.
   - Type — the type of connection (LDAP or LDAPS).

## Section "Computers"

### Component "Add computer to group"

Adds a computer to a specified group. Includes the following required properties:

1. **Computer**:
   - Computer unique name — the unique name of the computer.
   - Unique group name — the unique name of the group.

### Component "Set computer status"

Changes the status of a specified computer. Includes the following properties:

1. **Computer**:
   - Computer unique name — the unique name of the computer.
   - Status — required field representing the status to be set.

### Component "Get computers in group"

Retrieves the list of computers in a specified group. Includes the following properties:

1. **Output**:
   - Computers — the unique names of the computers.
2. **Computer**:
   - Group unique name — the unique name of the group.

### Component "Get computer status"

Gets the activity status of a specified computer. Includes the following properties:

1. **Output**:
   - Active status — required field indicating the computer’s active status.
2. **Computer**:
   - Computer unique name — required field representing the unique name of the computer.

### Component "Join computer to domain"

Joins a specified computer to the domain. Includes the following properties:

1. **Computer**:
   - User name — an administrator user on the computer being joined to the domain. If not provided, the robot’s account will be used.
   - Password — the user’s password.
   - Rejoin — specifies whether to rejoin the computer even if it's already joined.
   - Location — unique name of the parent node.
   - Create computer account — indicates whether a computer account will be created in Active Directory.
   - Computer unique name — required field for the computer's unique name.

### Component "Computer exists"

Checks if a specified computer exists. Includes the following properties:

1. **Output**:
   - Result — whether the computer exists.
2. **Computer** (required):
   - Value — the value being checked.
   - Location — the location in Active Directory to perform the search.
   - Filter — filter for the check:
      - SAM Account name — the unique name of the computer's account in Active Directory.
      - Common Name — the common name of the computer in Active Directory.
      - Use Principal name — the unique identifier (e.g., computer@domain.com).

### Component "Create computer"

Creates a new computer in Active Directory. Includes the following properties:

1. **Output**:
   - Unique name — the unique name of the newly created computer.
2. **Computer**:
   - Enabled — indicates whether the new computer is enabled.
   - SAM account name — required field for the computer’s SAM account name.
   - Common name — the common name of the new computer, required.
   - Location — unique name of the parent record, required.
   - Properties — properties of the computer (a table with two columns: the name of the property and its value).

### Component "Delete computer"

Deletes a computer. Includes the following required properties:

1. **Computer**:
   - Computer unique name — the unique name of the computer.
   - Recursive — specifies whether to delete along with child elements.

### Component "Remove computer from group"

Removes a specified computer from a group. Includes the following required properties:

1. **Computer**:
   - Unique group name — the unique name of the group.
   - Computer unique name — the unique name of the computer.

### Component "Unjoin computer from domain"

Removes a specified computer from the domain. Includes the following properties:

1. **Computer**:
   - User name — an administrator user on the computer being unjoined from the domain. If not provided, the robot’s account will be used.
   - Disable account — indicates whether the account should be disabled.
   - Password — the user’s password.
   - Computer unique name — required field representing the unique name of the computer.

## Section "Groups"

### Component "Create group"

Creates a new group in Active Directory. Includes the following properties:

1. **Output**:
   - Unique name — the unique name of the created group.
2. **Group**:
   - SAM account name — required field for the group's SAM account name.
   - Common name — required field for the common name of the new group.
   - Location — required field for the unique name of the parent record.
   - Properties — group properties (a table with two columns: the property name and its value).
   - Type — the type of the group.

### Component "Delete group"

Deletes a group. Includes the following required properties:

1. **Group**:
   - Recursive — specifies whether to delete along with child elements.
   - Group unique name — the unique name of the group.

### Component "Add group to group"

Adds a group to a specified group. Includes the following required properties:

1. **Group**:
   - Group unique name — the unique name of the group being added.
   - Unique parent group name — the unique name of the parent group.

### Component "Group exists"

Checks if a specified group exists. Includes the following properties:

1. **Output**:
   - Result — indicates whether the group exists.
2. **Group** (required):
   - Value — the value being checked.
   - Location — the Active Directory location where the search will be performed.
   - Filter — the filter for the check:
      - SAM Account name — the unique security account name (login) used to identify the object in Active Directory.
      - Common Name — the common name of the object in Active Directory, which can include the group's name and description.
      - Use Principal name — login in the format of an email address (e.g., user@domain.com). For groups, this value is used to search for the group by its UPN, if available.

### Component "Remove group from group"

Removes a specified group from another group. Includes the following required properties:

1. **Group**:
   - Group unique name — the unique name of the group being removed.
   - Parent group unique name — the unique name of the parent group.

## Section "General"

### Component "Update object properties"

Edits the properties of a specified object. Includes the following properties:

1. **Filter**:
   - New value — the value of the property being edited.
   - Property name — the name of the property being edited.
   - Properties — an array of properties to be edited.
   - Properties (table) — an array of properties (table with two columns: property name and value).
   - User unique name — required field for the user's unique name.

### Component "Rename object"

Renames an object. Includes the following properties:

1. **Filter**:
   - New name — the new common name (CN) of the object.
   - User unique name — required field for the user's unique name.

### Component "Move object"

Moves an object to another group. Includes the following properties:

1. **Filter**:
   - User unique name — required field for the user's unique name.
   - Unique group name — the unique name of the new parent group.

### Component "Get objects by filter"

Searches for objects according to a filter. Includes the following properties:

1. **Output**:
   - Objects — an array of unique object names.
2. **Filter**:
   - Property value — required field for the property value being searched.
   - Category — the category of objects to be retrieved (e.g., Person).
   - Class — the class of objects to be retrieved (e.g., group, user, computer, etc.).
   - Relation — the operator to be used for the filter:
      - Equal to — equal to the specified value.
      - Not Equal — not equal to the specified value.
      - Greater Than Or Equal To — greater than or equal to the specified value.
      - Less Than Or Equal To — less than or equal to the specified value.
   - Location — the distinguished name identifying the AD location.
   - Property — the property by which the filtering is performed. Required field.

### Component "Get objects by LDAP filter"

Searches for objects using an LDAP filter. Includes the following properties:

1. **Output**:
   - Objects — an array of unique object names.
2. **Filter**:
   - Location — the distinguished name identifying the AD location.
   - Filter — required field. The LDAP filter. For example, to search for users with `cn` starting with "Ivan", use the LDAP filter `(&(objectCategory=person)(objectClass=user)(cn=Ivan*))`.

### Component "Get object properties"

Retrieves the properties of a specified object. Includes the following properties:

1. **Output**:
   - All properties — all properties of the object.
   - Value — the value of the specified property.
2. **Property**:
   - Property name — the name of the specific property. If not specified, all properties will be retrieved.
   - User unique name — required field for the user's unique name.

### Component "Get object unique name"

Retrieves the unique name of an object. Includes the following properties:

1. **Output**:
   - Unique name — the unique name of the object.
2. **Filter**:
   - SAM account name — required field for the object's SAM account name.

### Component "Is object member of group"

Checks if an object is a member of a specified group. Includes the following properties:

1. **Output**:
   - Result — the result of the check.
2. **Filter**:
   - Child recursion — flag indicating whether to check within child groups.
   - Group unique name — the unique name of the group being checked.
   - User unique name — required field for the user's unique name.

## Section "Users"

### Component "Add user to group"

Adds a user to a specified group. Includes the following required properties:

1. **User**:
   - User unique name — the unique name of the user account.
   - Group unique name — the unique name of the group.

### Component "Change user password"

Changes the password of a user. Includes the following required properties:

1. **User**:
   - User unique name — the unique name of the user account.
   - Password — the new password for the user.

### Component "Set user status"

Changes the status of the specified user. Includes the following required properties:

1. **User**:
   - Status:
      - Disabled — the account will be disabled, preventing the user from logging in.
      - Enabled — the account will be enabled, allowing the user to access the system.
      - Unlocked — the account will be unlocked if it was locked due to incorrect password attempts or other reasons.
   - User unique name — the unique name of the user account.

### Component "Get password expiration date"

Retrieves the password expiration date of the specified user. Includes the following required properties:

1. **Output**:
   - Date — the password expiration date.
2. **User**:
   - User unique name — the unique name of the user account.

### Component "Get user expiration date"

Retrieves the account expiration date of the specified user. Includes the following required properties:

1. **Output**:
   - Date — the account expiration date.
2. **User**:
   - User unique name — the unique name of the user account.

### Component "Get user groups"

Retrieves the list of groups that the specified user is a member of. Includes the following required properties:

1. **Output**:
   - Groups — the user's group memberships.
2. **User**:
   - User unique name — the unique name of the user account.

### Component "Get users in group"

Retrieves the list of users in a specified group. Includes the following properties:

1. **Output**:
   - Users — unique names of the users.
2. **User**:
   - Group unique name — required field for the group's unique name.

### Component "Get user status"

Retrieves the lock and activity status of the specified user. Includes the following required properties:

1. **Output**:
   - Active status — whether the account is active.
   - Lock status — whether the account is locked.
2. **User**:
   - User unique name — the unique name of the user account.

### Component "Force password change"

Forces a password change for the user. Includes the following required properties:

1. **User**:
   - User unique name — the unique name of the user account.

### Component "Validate user credentials"

Validates the credentials of the specified user. Includes the following properties:

1. **Output**:
   - Result — the result of the validation.
2. **User**:
   - Value — required field for the filter value.
   - Password — the user's password.
   - Password (encrypted) — the encrypted password.
   - Filter — the user filter.

### Component "User exists"

Checks the existence of the specified user. Includes the following properties:

1. **Output**:
   - Result — whether the user exists.
2. **User** (required fields):
   - Value — the value being checked.
   - Location — the Active Directory location to search in.
   - Filter — the filter for the check.

### Component "Create user"

Creates a new user in Active Directory. Includes the following properties:

1. **Output**:
   - Unique name — the unique name of the created user.
2. **User**:
   - Enabled — flag to enable the new user.
   - SAM account name — required field.
   - Common name — required field.
   - Password — required field.
   - Location — required field for the unique name of the parent entry.
   - Properties — user properties (table with two columns: property name and value).

### Component "Delete user"

Deletes a user. Includes the following required properties:

1. **User**:
   - User unique name — the unique name of the user account.
   - Recursive — flag to delete along with child elements.

### Component "Set user expiration date"

Sets the expiration date of the specified user's account. Includes the following required properties:

1. **User**:
   - Date — the expiration date.
   - User unique name — the unique name of the user account.

## Feedback

If you have any questions or suggestions, please contact us at [support@primo-rpa.ru](mailto:support@primo-rpa.ru).
