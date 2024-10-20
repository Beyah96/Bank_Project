# Bank Management System
![Difficulty](https://img.shields.io/badge/Project-Medium-FFA500)
![C++](https://img.shields.io/badge/C%2B%2B-Beginner%20Friendly-00599C)
![License](https://img.shields.io/badge/License-MIT-green)

This project is a console-based **Bank Management System** developed in C++. It allows basic operations such as adding, updating, deleting, and viewing client details. Client data is stored in a text file, and the program utilizes file I/O operations to manage records. The system can handle multiple clients and features a user-friendly menu-driven interface.

## Features

- **Add New Client**: Register a new client by entering their account details.
- **View Client List**: Display all registered clients along with their account details.
- **Update Client Information**: Modify existing client details (PIN, name, phone, balance).
- **Delete Client**: Remove a client’s record from the database.
- **Search Client by Account Number**: Find a specific client based on their account number.

---

## How it Works

### Program Logic

The system stores client information (account number, PIN, name, phone number, balance) in a text file (`Clients.txt`). Each record is serialized in a specific format and delimited by a custom separator (`#;/**/;#`). Operations such as adding, updating, or deleting clients are directly reflected in the text file, ensuring that data persists between executions.

### Breakdown of Components

1. **Client Structure (`struct stClient`)**: Holds the basic details of each client.
2. **File Operations**: Client records are read from and written to `Clients.txt`.
3. **Menu System**: The main menu allows users to select operations (e.g., `AddNewClient`, `DeleteClient`, etc.).
4. **Client Search**: The system searches records based on account number for updates or deletions.

## File Structure

- **`main.cpp`**: Contains all program logic.
- **`Clients.txt`**: Automatically generated file that stores all client records.

## Requirements

- **C++ Compiler**: Ensure you have a working C++ compiler installed (e.g., GCC, MSVC).
- **Development Environment**: A text editor or IDE (e.g., VSCode, CLion).

## How to Compile and Run

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/Beyah96/Bank_Project.git
    cd Bank_Project
    ```

2. **Compile the Code** (using GCC):
    ```bash
    g++ -o Bank_Project main.cpp
    ```

3. **Run the Executable**:
    ```bash
    ./Bank_Project
    ```

## Example Usage

Upon starting the program, you will be greeted with the main menu:

### Main Menu:

1. Show Client List
2. Add New Client
3. Delete Client
4. Update Client Info
5. Find Client
6. Exit

- **To add a new client** : select option `2` and provide the necessary information:
    - Account Number
    - PIN Code
    - Full Name
    - Phone Number
    - Account Balance

- **To view all clients** : select option `1` to display all stored records.

- **To update or delete a client** : enter their account number when prompted. The system will search for the client and allow further actions if found.

## Logic Breakdown

- **Adding a Client** : Checks if the account number is unique and appends the new record to `Clients.txt`.
- **Updating Client Info** : Searches for the account number, retrieves the record, allows modification, and rewrites the updated data.
- **Deleting a Client** : Searches for the client by account number and excludes the record from the new file content.
- **Client Search** : Scans the file for the account number and displays the information if found.

## File Format

Client records are stored in `Clients.txt` in the following format (delimited by `#;/**/;#`):

```bash
<account_number>#;//;#<pin_code>#;//;#<full_name>#;//;#<phone_number>#;//;#<account_balance>
```

## Example
```bash
123456#;//;#7890#;//;#John Doe#;//;#555-1234#;//;#1000.50
987654#;//;#4321#;//;#Jane Smith#;//;#555-5678#;//;#2500.00

```

## Additional Information

- **Data Integrity** : The system ensures data consistency by rewriting the entire file during update and delete operations. Only non-deleted records are saved back to the file.
- **Security** : PIN codes are stored as plain text in this simple implementation, but could be encrypted in a more advanced version for better security.

## License

This project is open-source and licensed under the MIT License. Contributions and improvements are welcome!
