## Fedrated Credentials:

**1.What Are Federated Credentials?**
```
Federated credentials let an application or a service authenticate to a
cloud provider without storing secrets, passwords, or keys.
```
```
* Instead of hardcoding credentials, your cloud trusts an external identity provider (IdP)
(like GitHub, GitLab, Azure AD, Google, etc.) to issue tokens.
```

**Example:**
```
* Normally, a GitHub Action would need to store a cloud secret
(AWS key, Azure SP password, etc to connect and to perform deployment or the operations.
* With federated credentials, GitHub directly asks the cloud provider forshort-lived access using its own identity
 → no secrets stored.(It works with the token for shot time automattically)
```
**How It Works (Simple Flow)**
```
* External Identity Provider (like GitHub Actions, Azure AD, Google Workspace) issues a token for the workflow or app.
* Cloud Provider (AWS, Azure, GCP) verifies that token.
* Cloud grants temporary access to the resources (for the role/service account).
```

**Think of it like a “passport check”:**
```
GitHub gives you a passport (OIDC token).
AWS/Azure/GCP checks if your passport is valid and matches conditions.
If valid → you get a temporary visa (short-lived access token).
```
**Advantages**
```
* No secrets to rotate (secure).
* Short-lived tokens (reduce attack risk).
* Easier automation (CI/CD friendly).
```

**Practical Steps**
```
Step1:Create a app registration
 * Goto Azure Portal -> Azure AD ->App Registrations -> new app registraion

Step2:Add Federated Credential
 * In the app, go to Certificates & Secrets → Federated credentials → Add credential.
 Choose:
 Identity provider: GitHub
 Repository: username/repo-name
 Branch or environment: main

Step3:Assign Role
 * Go to your resource (e.g., Azure Subscription/Resource Group).
 * Assign a role (like Contributor/Reader) to the App Registration.

```
**Eg of the github actions.yml**
```
jobs:
  deploy:
    runs-on: ubuntu-latest
    permissions:
      id-token: write
      contents: read
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Login to Azure //for login into the azure ur not passing here a secret it will automattically will login using the fed credentials
        uses: azure/login@v1
        with:
          client-id: ${{ secrets.AZURE_CLIENT_ID }} 
          tenant-id: ${{ secrets.AZURE_TENANT_ID }}
          subscription-id: ${{ secrets.AZURE_SUBSCRIPTION_ID }}
```
 
