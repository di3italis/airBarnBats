//something about postman xsrf variable
xsrftoken
var xsrfCookie = postman.getResponseCookie("XSRF-TOKEN");
postman.setEnvironmentVariable('xsrftoken', xsrfCookie.value);

## Ongoing Maintenance
The main limitation of the free Render Postgres database instance is that it will be deleted after 90 days. In order to keep your application up and running, you MUST create a new database instance before the 90 day period ends.

Set up calendar reminders for yourself to reset your Render Postgres database instance every 85 days so your application(s) will not experience any downtime.

Each time you get your calendar reminder, follow the steps below.

Navigate to your Render Dashboard, click on your database instance, and click on either the "Delete Database" or "Suspend Database" button.

Next, follow the instructions in Phase #3 above to create a new database instance.

Finally, you will need to update the environment variables for EVERY application that was connected to the original database with the new database information. For each application:

Click on the application name from your Dashboard
Click on "Environment" in the left sidebar
Replace the value for DATABASE_URL with the new value from your new database instance, and then click "Save Changes"
At the top of the page, click "Manual Deploy", and choose "Clear build cache & deploy".
After each application is updated with the new database instance and re-deployed, manually test each application to make sure everything still works and is appropriately seeded.
