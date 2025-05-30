# 🛡️ Authenticate Service (SSO Gateway)

`identity-service` is the centralized **Single Sign-On (SSO)** authentication service for the `microservice-lab` project.

It provides a unified authentication layer for all microservices using:
- ASP.NET Core Identity
- JWT token issuance
- External authentication providers (Azure AD, LDAP, Google, GitHub, etc.)

🧩 In the future, this service can be **extended or replaced** with standards-compliant identity providers such as:
- [Keycloak](https://www.keycloak.org/)
- [OpenIddict](https://github.com/openiddict/openiddict-core)
- [IdentityServer](https://duendesoftware.com/)

---

## 🎯 Project Goals

- ✅ Provide a central authentication hub (SSO) for microservices
- 🔐 Support local and external authentication providers
- ⚙️ Generate and manage secure JWT access tokens
- 🔄 Easily replaceable or integratable with industry-standard identity platforms
- 🔁 Scalable with message brokers (e.g., Kafka, RabbitMQ) for auth-related events

---

## 🔧 Features

- ASP.NET Core Identity-based user management
- External logins: Azure AD, LDAP, Google, GitHub
- Issue JWT access tokens for downstream services
- Designed for use behind an API Gateway
- Extensible for OpenID Connect integration
- Optional event publishing (UserCreated, UserLogin, etc.)

---

## 🛠️ Designed for Microservices

This service acts as an **authentication gateway**, allowing all backend services to **delegate login and token validation** to this single point.

**Benefits**:
- Centralized login & logout
- Unified token issuance
- Reduced duplication across services
- Easy integration with OAuth2 / OpenID Connect ecosystems

---

## 🔮 Future Support (Planned)

- 🔄 Replaceable with or extendable via:
  - **Keycloak** (via OIDC)
  - **OpenIddict** (embedded in .NET)
  - **IdentityServer** (commercial)
- 🔄 Support for **Refresh Tokens**, token revocation
- 🔒 Role and Permission-based access control (RBAC)

---

## 🏗️ Part of the Microservice Lab

This service is part of the [`microservice-lab`](https://github.com/menvs/microservices-lab) project, which demonstrates best practices for building modern microservices with:
- Docker, Kubernetes
- Message Queues
- Redis, PostgreSQL, SQL Server
- Authentication & Authorization

---

## 📦 Endpoint Usage

| Endpoint              | Method | Purpose                         |
|-----------------------|--------|---------------------------------|
| `/api/auth/login`     | POST   | Local login (email + password) |
| `/api/auth/register`  | POST   | Register local account          |
| `/signin-google`      | GET    | Google login redirect           |
| `/signin-oidc`        | GET    | Azure AD / OIDC callback        |

---

## 📘 Learn More

- [ASP.NET Core Identity Docs](https://learn.microsoft.com/en-us/aspnet/core/security/authentication/identity)
- [OpenID Connect Protocol](https://openid.net/connect/)
- [Keycloak Docs](https://www.keycloak.org/documentation)
- [OpenIddict Guide](https://documentation.openiddict.com/)

---

## 🤝 License

MIT © 2025 YourName
