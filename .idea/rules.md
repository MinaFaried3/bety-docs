# Dash Platform — JetBrains / .idea AI Rules

- **Media & Image Uploads:** All image and binary file uploads MUST be sent as `multipart/form-data`. Endpoints creating or updating entities accept the uploaded image URL string in JSON request bodies.
- **Backend Architecture:** ASP.NET Core (.NET 8+) Modular Monolith, SQL Server, Redis, Monolithic WebSockets, Server-Sent Events, Uber H3 spatial indexing.
- **Frontend Architecture:** Flutter (Android, iOS, Web Dashboard). Clean Architecture, Cubit state management, Dio + Retrofit API layer, Dartz `Either<Failure, T>`, easy_localization (en-US & ar-SA).
- **API Contracts:** Follow `base_request.md`, `base_response.md`, and `headers.md`.
- **GitHub Relative Hyperlinks:** NEVER use `file:///...` absolute URIs in markdown links. ALWAYS use relative paths.
- **Document Synchronization Matrix:** Enforce 7-rule cascading updates matrix across all specification documents.
