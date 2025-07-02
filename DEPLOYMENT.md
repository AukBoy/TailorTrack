# Deploying Your Next.js App to Hostinger

This guide provides two methods for deploying your Next.js application to a hosting provider like Hostinger.

---

## Recommended Method: Using Git (Automated)

This is the standard and most reliable way to deploy modern web applications. It automates the process, making updates quick and easy.

1.  **Push Your Code to a Git Repository:**
    *   Create a new repository on a service like [GitHub](https://github.com/), [GitLab](https://gitlab.com/), or [Bitbucket](https://bitbucket.org/).
    *   Follow their instructions to push your local project code to the new repository.

2.  **Create a Hostinger Account & Project:**
    *   Sign up for a hosting plan on [Hostinger](https://www.hostinger.com/) that supports Node.js/Next.js applications.
    *   In your Hostinger dashboard, create a new application or website.

3.  **Connect Your Git Repository:**
    *   During the project setup on Hostinger, you will be prompted to connect your Git provider (e.g., GitHub).
    *   Authorize Hostinger to access your account and select the repository containing your app's code. This is how Hostinger will access your code.

4.  **Configure Build Settings:**
    *   Hostinger will likely detect that you have a Next.js project and configure the build settings automatically.
    *   If you need to configure it manually, the settings are typically:
        *   **Build Command:** `npm run build`
        *   **Publish Directory:** `.next`
    *   You do not need to worry about the `genkit` commands for deployment.

5.  **Add Environment Variables (If Any):**
    *   If your project used a `.env` file, you must add these to your project's settings in the Hostinger dashboard.
    *   **Note:** Your current project does not have any environment variables.

6.  **Deploy:**
    *   Trigger the first deployment. Hostinger will pull your code, run the build command, and deploy the application to a public URL.
    *   Future deployments are automatic. Whenever you push new code to your Git repository, Hostinger will automatically redeploy the app.

---

## Alternative Method: Manual Upload (Without Git)

If you prefer not to use Git, you can build your application locally and upload the files manually. This method requires more steps and you'll have to repeat it for every update.

1.  **Install Dependencies:**
    *   After downloading and unzipping the project to your PC, open a terminal or command prompt in the project's root folder.
    *   Run the command: `npm install`. This will download all the necessary packages your app needs to run. You only need to do this the first time you set up the project.

2.  **Build Your Application:**
    *   In the same terminal, run the command: `npm run build`.
    *   This command creates a highly optimized folder named `.next`. This folder contains everything needed to run your application in production.

3.  **Compress Your Files:**
    *   Create a `.zip` file containing the following items from your project:
        *   The entire `.next` directory.
        *   The `public` directory (if it exists).
        *   The `package.json` file.
        *   The `next.config.ts` file.

4.  **Upload to Hostinger:**
    *   Log in to your Hostinger account and go to the **File Manager**.
    *   Navigate to the main directory for your website (often `public_html`).
    *   Upload the `.zip` file you created.

5.  **Unzip the Files:**
    *   In the File Manager, right-click on your uploaded `.zip` file and select **Extract** or **Unzip**.

6.  **Configure Node.js on Hostinger:**
    *   In your Hostinger dashboard, find the section for managing Node.js applications.
    *   Create a new Node.js application.
    *   Set the **Application Startup File** to `node_modules/.bin/next`.
    *   Set the **Application Mode** to `production`.
    *   Hostinger should automatically detect your `package.json` and run `npm install`. If not, you may need to trigger it manually from a terminal or control panel option.

7.  **Start the Application:**
    *   Once everything is configured, start your Node.js application from the Hostinger dashboard.

Your site should now be live! For more detailed, platform-specific instructions, always refer to Hostinger's official documentation for deploying Next.js applications manually.
