# Showcase Your Learning With Docusaurus + Azure Static Web App

This is a tutorial shared as part of the #30DaysOfSWA series, to showcase the use of Azure Static Web Apps with the open-source Docusaurus static site generator from Meta.

## What We'll Learn:

 * What is Docusaurus?
 * Quickstart: setup classic site
 * Configure: docusaurus.config.js
 * Deploy: Azure Static Web Apps
 * Customize: Themes & Plugins
 * `Exercise`: 
    - Add API to fetch content!
    - Add Auth to tweet content!
    - Add MDX component to page!

---

## What is Docusaurus?

Docusaurus is an open-source project from Meta that helps you build, deploy, and maintain, open source project websites. It was rated one of the top 3 [rising stars of JavaScript](https://docusaurus.io/) in 2021, under the _static site generators_ category. 

Read their [documentation](https://docusaurus.io/docs) and visit their [showcase](https://docusaurus.io/showcase) for real-world examples of what you can build with docusaurus.

---

## Setup Site: Quickstart

1. Setup a Docusaurus site (`classic` theme) in a dedicated folder (`www`) in repo. The command automatically installs the required packages and their dependencies.

```bash
 npx create-docusaurus@latest www classic
```

2. Let's see what was created for us. The output has been cleaned up for clarity.

```
ls -l www/

README.md   
babel.config.js 
blog/              
docs/    
docusaurus.config.js               
node_modules/        
package-lock.json    
package.json           
sidebars.js                 
src/                  
static/    
```

3. Let's preview the site locally, to validate this worked.

```bash
cd www
npx docusaurus start

[INFO] Starting the development server...
[SUCCESS] Docusaurus website is running at http://localhost:3000/.
```

You should see something like this - this is the default landing page for the scaffolded Docusaurus site.

![Landing Page](./img/11-landing.png)

4. The dev server supports hot reloading. Try making a minor change to the site source - for example edit `docusaurus.config.js` and change the `title` to **"My Static Web Apps Site"**. You should see this in your site preview, instantly:

![Landing Page Reloaded](./img/11-reload.png)

5. You can now build a **production-ready** version of that site as follows. Note that the static files are generated in the **build/** directory.

```bash
cd www/
npm run build
..
..
[SUCCESS] Generated static files in "build".
[INFO] Use `npm run serve` command to test your build locally.
```

## Deploy Site: To Azure

Docusaurus is built using React - so you can use [the same configuration settings](https://docs.microsoft.com/en-us/azure/static-web-apps/front-end-frameworks) for Docusaurus, when deploying to Azure Static Web Apps. 

You have three options to  get started:
 * via browser with [the Azure Portal quickstart](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=react)
  * via terminal with [the Azure CLI quickstart](https://docs.microsoft.com/en-us/azure/static-web-apps/get-started-cli?tabs=vanilla-javascript)
  * via IDE with [the VS Code Extension quickstart](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=vanilla-javascript) 

If you prefer the first approach, click the button to go to the Azure portal, then follow the [quickstart](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=react) guidance, but using *this* project's details instead.

[![Deploy to Azure button](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/?feature.customportal=false&WT.mc_id=30daysofswa-61155-cxall#create/Microsoft.StaticApp)

## Deploy Site: with VSCode

I'll use the [Visual Studio Code extension](https://docs.microsoft.com/en-us/azure/static-web-apps/getting-started?tabs=vanilla-javascript) to make this happen with just a few clicks. 

1. **Install Extension** | Open Visual Studio Code (IDE) in the project folder for your repo. Install the [Azure Static Web Apps extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestaticwebapps) by visiting this page and clicking "Install".

![VS Code Extension for SWA](./img/11-extension.png)

When extension is installed, you should see this window in your VS Code editor, confirming readiness for use.

![VS Code Extension Installed](./img/11-vscode.png)

2. **Create your first Azure Static App** | The extension's [documentation page](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestaticwebapps) walks you through the steps needed visually, so reference it! You can also visit its [GitHub](https://github.com/microsoft/vscode-azurestaticwebapps/wiki/Creating-a-Static-Web-App) page for more details. Start by clicking the `Azure` icon in your VS Code sidebar, scroll down to the `Static Web Apps` section, then click the "+" button to **Create Static Web App**.

![Activate SWA Extension](./img/11-swa-plus.png)

