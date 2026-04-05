Here are the answers to your reflection questions, tailored to the activity you just built:

### 1. What is the difference between GET and POST?

- **GET** is used to **retrieve** data from the server. When you visit `/formtest` to view your list, you are using a GET request. The data is appended to the URL (e.g., `?email=test@me.com`), which makes it less secure for sensitive info and limited in size.
- **POST** is used to **send** data to the server to be processed or stored. When you submit your email form, you use POST. The data is hidden inside the "body" of the request, meaning it doesn't show up in the URL bar, making it more secure and capable of sending much larger amounts of data.

### 2. Why do we use `@csrf` in forms?

We use `@csrf` to prevent **Cross-Site Request Forgery** attacks. It generates a hidden "token" that Laravel checks whenever a form is submitted. This ensures that the person submitting the form is actually on **your** website and not a hacker trying to send a fake request from a different tab in your browser. Without this, Laravel will throw a `419 Page Expired` error as a security measure.

### 3. What is session used for in this activity?

In this specific activity, the **Session** acts as a **temporary database**. Since we aren't using a real database (like MySQL) yet, the session allows us to "remember" the emails you typed even after the page reloads. It stores the data on the server side and links it to your specific browser session.

### 4. What happens if session is cleared?

If the session is cleared (either by clicking your `/delete-emails` link, closing the browser, or the session timing out), **all stored emails will be permanently lost**. Because the data is only stored in RAM (memory) and not saved to a hard drive/database, clearing the session resets the `$emails` array back to being empty.
