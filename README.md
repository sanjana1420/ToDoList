# Tkinter To-Do List Application with MySQL Database

This is a simple Tkinter-based To-Do List application that allows users to register, login, and manage their tasks. The application uses MySQL to store user and task information.

## Features

- User Registration
- User Login
- Add Tasks
- Remove Tasks
- Mark Tasks as Complete
- Persistent Storage of Tasks in MySQL Database


## Installation

1. **Clone the Repository**
    ```sh
    git clone https://github.com/your-username/tkinter-todo-app.git
    cd tkinter-todo-app
    ```

2. **Install Required Python Packages**
    ```sh
    pip install mysql-connector-python
    ```

3. **Setup MySQL Database**
    - Create a database named `project`.
    - Create a `users` table:
      ```sql
      CREATE TABLE users (
          id INT AUTO_INCREMENT PRIMARY KEY,
          username VARCHAR(50) NOT NULL,
          email VARCHAR(100),
          phone VARCHAR(15),
          password VARCHAR(100) NOT NULL
      );
      ```
    - Create a `tasks` table:
      ```sql
      CREATE TABLE tasks (
          id INT AUTO_INCREMENT PRIMARY KEY,
          username VARCHAR(50) NOT NULL,
          task_name VARCHAR(255) NOT NULL,
          task_status VARCHAR(20) DEFAULT 'InProgress'
      );
      ```

4. **Update Database Configuration**
    - Update the database connection details in the `connect_to_db()` function:
      ```python
      def connect_to_db():
          return mysql.connector.connect(
              host="localhost",
              user="your_db_user",
              password="your_db_password",
              database="project"
          )
      ```

## Usage

1. **Run the Application**
    ```sh
    python main.py
    ```

2. **Login or Register**
    - On the login screen, either login with your existing credentials or click "Register here" to create a new account.

3. **Manage Tasks**
    - Once logged in, you can add, remove, and mark tasks as complete.

## Screenshots

![Login Screen](screenshots/login_screen.png)
![Register Screen](screenshots/register_screen.png)
![To-Do List](screenshots/todo_list.png)

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-foo`).
3. Commit your changes (`git commit -am 'Add some foo'`).
4. Push to the branch (`git push origin feature-foo`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Tkinter Documentation](https://docs.python.org/3/library/tkinter.html)
- [MySQL Connector/Python Documentation](https://dev.mysql.com/doc/connector-python/en/)

