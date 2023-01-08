# Freelance Marketplace School Work

This is a digital freelancing marketplace that will connect talented professionals with economic opportunities and give organisations access to affordable and low-risk human capital.


---

## Folder structure

All the application code is located within the `freelance` folder. It is organised in an MVP structure, with the following folders:

### Models

The Model component corresponds to all the data-related logic that the user works with. This can represent either the
data that is being transferred between the View and Controller components or any other business logic-related data.

Most of the models are simple, they only contain a few properties and a few methods and represent tables in the
database.

Most `SQL` queries are located here.

### Views

The view defines how the app's data should be displayed. It is used for all the UI logic of the application.

The `views/_layout.php` file is the main layout file that all the other views are rendered into.

### Controllers

The controller contains logic that updates the model and/or view in response to input from the users of the app.

They act as an interface between Model and View components to process all the business logic and incoming requests,
manipulate data using the Model component and interact with the Views to render the final output.

### Extra files & folders

- `public/index.php`: This is the main entry point of the application. All routes are defined here
- `public/static/`: This folder contains all the static files that are used throughout the application like CSS, JavaScript and fonts.
- `public/uploads/`: This folder contains all the uploaded files that are used throughout the application. It should
  not have been added to the repo - it was only added as a convenience with regard to presenting it as a school project.
- `utils/`: This folder contains all the utility classes that are used throughout the application.
- `tasks/`: This folder contains asynchronous tasks that should be run periodically.
- `Router.php`: This is the main file that handles all the routing logic of the application.
- `Settings.php`: This is the main configuration file that contains all the configuration variables.
- `Database.php`: This is the main file that contains all the database connection logic.
- `db_schema.sql` and `db_schema.png`: These are the database schema files.
- `db_data.sql`: This is the database (backup) data file. Again, it should not have been added to the repo - it was
  only added as a convenience with regard to presenting it as a school project.
- `.env.example`: contains all environment variables that should be set.

---

## Local setup

Clone the repository to your local machine.

```bash
git clone
```

Then you will need to install [Composer](http://getcomposer.org/) following the instructions on their site.

From the `freelance` directory, run the following command:

```bash
composer update
```

Set up a MySQL database on your local machine with the following configuration as defined in `Database.php`:

```txt
- Database name: freelance
- Username: freelance
- Password: freelance
```

You can alternatively use a database connection string to connect a database by setting the `CLEARDB_DATABASE_URL` environment variable.

**Set up schema:**

Use the SQL in the `db_schema.sql` file to create the database schema.

**Set up data (Optional):**

Use the SQL in the `db_data.sql` file to populate the database with some data.

### Environment variables (Optional)

Check out the environment variables used by the app in the `env.example` file.

### Mail (Optional)

Mails are sent via `smtp.gmail.com` (Gmail). See more in `utils/Mailer.php`.

Set the following environment variables to get it working:

- `MAIL_USERNAME`: Your Gmail email address.
- `MAIL_PASSWORD`: Your Gmail password.

### Payments (Optional)
---

## Running the application

From the `freelance/public` directory, run the following command to run the application locally on port 9000:

```txt
php -S 0.0.0.0:9000
```

---

Once you register as a freelancer you will have access to the freelancer dashboard.

From here you have the ability to do the following:

1. View and edit your user profile.
2. View and edit your freelancer profile.
3. View jobs.
    1. Give proposals for the jobs.
    2. Withdraw your proposals.
    3. Post work for completed jobs.
    4. Rate clients after completing a job.
4. View jobs you have given proposals to (My jobs).

All of the above functionality can be accessed via the sidebar.

1. From the `my jobs` page, select a job.
2. Click on the `submissions/ratings` button and fill in the form to submit your work.
3. Wait for the freelancer to accept or reject the work.
4. You can then proceed to rate the freelancer.
