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
