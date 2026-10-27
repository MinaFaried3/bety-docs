# OpenCode Detailed Rules & System Specifications

- **GitHub Relative Hyperlink Rule (MANDATORY):** NEVER use absolute `file:///...` URIs in markdown links. ALWAYS use relative paths (e.g. `[headers.md](../headers.md)`).
- **Backend Architecture:** ASP.NET Core (.NET 8+) Modular Monolith, SQL Server, Redis, Monolithic WebSockets, Server-Sent Events, Uber H3 geospatial indexing.
- **Frontend Architecture:** Flutter (Android, iOS, Web Dashboard). Clean Architecture, Cubit state management, Dio + Retrofit API layer, Dartz `Either<Failure, T>`, easy_localization (en-US & ar-SA).
- **Document Synchronization Matrix:** 7-rule cascading updates matrix as defined in `.agents/AGENTS.md`.
- **API Specification:** Follow `base_request.md`, `base_response.md`, and `headers.md`.
- **Media & Image Uploads:** All binary/image files must be uploaded via `multipart/form-data`.
- **Roadmap:** 12-week cap, 8-week MVP (RIDE passenger transport base scenarios), relative markdown hyperlinks in all weekly plan files.
