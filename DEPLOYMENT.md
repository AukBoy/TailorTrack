# Deploying Your Next.js App to Hostinger

This guide provides the general steps to deploy your Next.js application to a hosting provider like Hostinger. The process is similar for other modern hosting platforms like Vercel or Netlify.

## Deployment Steps

1.  **Push Your Code to a Git Repository:**
    *   Create a new repository on a service like [GitHub](https://github.com/), [GitLab](https://gitlab.com/), or [Bitbucket](https://bitbucket.org/).
    *   Follow their instructions to push your local project code to the new repository. This is how Hostinger will access your code.

2.  **Create a Hostinger Account & Project:**
    *   Sign up for a hosting plan on [Hostinger](https://www.hostinger.com/) that supports Node.js/Next.js applications.
    *   In your Hostinger dashboard, create a new application or website.

3.  **Connect Your Git Repository:**
    *   During the project setup on Hostinger, you will be prompted to connect your Git provider (e.g., GitHub).
    *   Authorize Hostinger to access your account and select the repository containing your app's code.

4.  **Configure Build Settings:**
    *   Hostinger will likely detect that you have a Next.js project and configure the build settings automatically.
    *   If you need to configure it manually, the settings are typically:
        *   **Build Command:** `npm run build`
        *   **Publish Directory:** `.next`
    *   You do not need to worry about the `genkit` commands for deployment.

5.  **Add Environment Variables (If Any):**
    *   If your project used a `.env` file for secret keys (like API keys), you must add these to your project's settings in the Hostinger dashboard. Go to the "Environment Variables" section and copy the key-value pairs from your local `.env` file.
    *   **Note:** Your current project does not have any environment variables, so you can likely skip this step.

6.  **Deploy:**
    *   Once configured, trigger the first deployment. Hostinger will pull your code, run the build command, and deploy the application to a public URL.
    *   Future deployments are usually automatic. Whenever you push new code to your connected Git branch (e.g., `main`), Hostinger will automatically redeploy the app with the latest changes.

That's it! Your site will be live. For more detailed, platform-specific instructions, always refer to Hostinger's official documentation.
