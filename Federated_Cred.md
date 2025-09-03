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
