# Deploying an Expo Web project to the AWS Amplify Console

- In the Amplify console, give it permission to read your GitHub account or org's repositories. Create an app and specify the repository you want to build and deploy from.
- Designate a branch you want to release from. `master` is fine for a demo but in practice you'll probably want a branch like `production`. Later you can add more release branches like `staging`.
- Amplify will automatically clone your repository and run the build commands in your `amplify.yml` file. In this demo, we have no build commands. Then it will upload and serve the static files in your `baseDirectory` specified in the YAML file.
- Amplify takes care of serving the files for you.
- You can also set up custom domains, including subdomains. It's easiest if the domains are already set up in Route 53. Each domain or subdomain can be associated with a release branch. Ex: staging.example.com can be associated with the `staging` branch.
- Amplify will provision TLS certificates using ACM. This takes awhile.
