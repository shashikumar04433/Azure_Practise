# Web App

### Types of Deployment in App Service:
```
* Web App → Your custom code or containerized app.
* Static Web App → Frontend-only sites (JS frameworks, static content).
* Web App + Database → App + DB created together.
* WordPress on App Service → Quick WordPress setup on Azure.
```
**1. Web App**
```
**What it is: **A normal Azure App Service where you can deploy your own code or container.

**Use case**: Hosting APIs, backend services, or full-stack apps that need scaling and managed hosting.
Example: A Python Flask API or .NET Core MVC app deployed directly.

2. Static Web App
What it is: An Azure service for static sites (HTML, CSS, JavaScript, React, Angular, Vue, etc.).

Use case: Hosting modern frontend apps with global CDN, free SSL, and CI/CD integration.

Example: A React single-page application served globally with backend APIs connected via Azure Functions.

3. Web App + Database
What it is: A wizard that creates a Web App along with a database (usually Azure SQL or MySQL).

Use case: When your app needs both a web frontend/backend and persistent database storage.

Example: An e-commerce site that stores products, users, and orders in Azure SQL while serving the web app on App Service.

4. WordPress on App Service
What it is: A ready-to-use WordPress CMS running on Azure App Service with MySQL.

Use case: Launching a content-driven website or blog quickly using WordPress.

Example: A company blog, news portal, or portfolio site built on WordPress.
