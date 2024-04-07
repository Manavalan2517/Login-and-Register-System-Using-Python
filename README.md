# Login-and-Register-System-Using-Python

## Summary
The code snippet is a class called `Validate` that provides methods for validating and managing user registration, login, and account deletion. It uses the `bcrypt` library for password hashing and the `re` library for email validation. The class also includes methods for updating a JSON file with user data and checking if a username already exists.

## Example Usage
```python
validateObj = Validate()
validateObj.register_user("john", "password123", "john@example.com")
validateObj.login_user("john", "password123")
validateObj.delete_account("john")
```

## Modules Used
- `questionary`----> `for creating interactive prompts and questionnaires`
- `json`--------------> `Used for parsing and generating JSON data`
- `rich.console`---> `enables rich text and beautiful formatting in the terminal`
- `time.sleep`------> `used to pause the execution of the script for a specified number of seconds.`
- `bcrypt`------------> `to build a cryptographic hash of passwords`
- `re`------------------> `used for searching, matching, and manipulating strings based on specific patterns`
  
## Code Analysis
### Inputs
- `username` (string): The username entered by the user.
- `password` (string): The password entered by the user.
- `email` (string): The email entered by the user.
___
### Flow
1. The `Validate` class checks if the JSON file "data.json" exists. If not, it creates a new file with an empty "gamedata" dictionary.
2. The `hash_password` method takes a password as input, generates a salt, and hashes the password using bcrypt.
3. The `update_json` method updates the "gamedata" dictionary in the JSON file with the username, hashed password, and email.
4. The `validate_username` method checks if the username is valid (not empty and contains only lowercase letters) and if it already exists in the JSON file.
5. The `validate_password` method checks if the password meets certain criteria (minimum length, contains a number, lowercase letter, and uppercase letter).
6. The `validate_email` method uses a regular expression to validate the email format.
7. The `register_user` method validates the username, password, and email, hashes the password, and updates the JSON file with the user data.
8. The `login_user` method checks if the username exists in the JSON file, retrieves the hashed password, and compares it with the entered password using bcrypt.
9. The `delete_account` method checks if the username exists in the JSON file, deletes the user data from the "gamedata" dictionary, and updates the JSON file.
10. The `register` function prompts the user to enter a username, password, and email, validates the inputs, and calls the `register_user` method.
11. The `login` function prompts the user to enter a username and password, calls the `login_user` method, and displays a welcome message if successful.
12. The `delete_account` function prompts the user to enter a username and password, calls the `login_user` method to validate the credentials, and calls the `delete_account` method to delete the user account.
___
### Outputs
- The `register_user` method returns `True` if the registration is successful, and `False` if any validation error occurs.
- The `login_user` method returns `True` if the login is successful, and `False` if the username or password is incorrect.
- The `delete_account` method returns `True` if the account is successfully deleted, and `False` if the username is not found in the JSON file.
___
