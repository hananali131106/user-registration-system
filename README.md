Welcome to the User Registration System, a full-stack web application designed to manage user data seamlessly. Built with C# (ASP.NET Core) for the backend, React.js for the frontend, and powered by SQL Server for data storage, this system allows users to register, validate their data, and store it securely in a database.


Before diving into the setup process, ensure that you have the following tools installed:

.NET SDK (v5 or above) for the backend
Node.js (v14 or above) for frontend dependencies
SQL Server and SSMS (SQL Server Management Studio) for database management
React.js for building the user interface
Visual Studio Code (or the preferred code editor)

Setting Up the Project:
Let us get this project running step by step.

1. Clone the Repository

Start by cloning the project to your local machine:

git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name

2. Backend Setup

2.1. Install .NET Dependencies

Navigate to the Backend folder and restore the necessary dependencies:

cd Backend
dotnet restore

2.2. Configure SQL Server Database

Launch SQL Server Management Studio (SSMS) and create a new database (if not already set up).
Run the following SQL query to create the Users table:

CREATE TABLE Users (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    FullName NVARCHAR(100) NOT NULL,
    Email NVARCHAR(100) UNIQUE NOT NULL,
    PhoneNumber NVARCHAR(15) NOT NULL,
    Age INT NOT NULL
);

Ensure your appsettings.json file has the correct database connection string:

"ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\Local;Database=RegistrationDB;Trusted_Connection=True;"
}

2.3. Run the Backend API

Now, the prject ready to fire up the backend. Simply run the following command:


dotnet run
The backend API should now be live at http://localhost:5000 (or the port you configured).

3. Frontend Setup

3.1. Install Frontend Dependencies

Navigate to the Frontend folder and install all the necessary npm packages:

cd Frontend
npm install

3.2. Configure API Endpoint

Ensure your React application points to the correct API URL. In the frontend, check for the API call (usually where axios or fetch is used), and update it like so:

const API_URL = 'http://localhost:5000/api/users';

3.3. Start the React App

Next, run the React development server:

npm start

React app should now be accessible at http://localhost:3000 in the browser.

4. Run the Application

Now that both your backend and frontend are running, open up your browser and navigate to:

http://localhost:3000
You will be greeted with a user-friendly registration form. Fill in the required details, and upon successful registration, the data will be saved to your SQL Server database.

5. Testing Application

Once everything is set up:

Open the React app in your browser and try filling out the registration form.
After submission, head over to SQL Server Management Studio (SSMS) and confirm that the user data has been correctly saved to your database.

6. Troubleshooting

Double-check your database connection string and ensure that SQL Server is up and running.
If the API is not responding, consult the backend logs for any errors.
Confirm that both frontend and backend servers are running on the correct ports.

Congratulations! Now everything is set up and ready to be used!
