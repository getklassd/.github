<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/getklassd/.github/main/profile/assets/klassd-wordmark.png">
    <img alt="Klassd" src="https://raw.githubusercontent.com/getklassd/.github/main/profile/assets/klassd-wordmark-light.png" width="360">
  </picture>
</p>

<p align="center">
  <strong>A code-first, NuGet-distributed headless CMS for .NET.</strong><br>
  Define your content model as plain C# classes — get a Blazor admin and a headless API for free.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-10.0-512BD4.svg" alt=".NET 10">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT">
  <img src="https://img.shields.io/badge/admin-Blazor-512BD4.svg" alt="Blazor admin">
</p>

---

### What is it?

Your content schema lives in your **codebase**, not in a CMS UI. Declare pages, blocks and property
types as C# classes; the engine reflects over them to drive a **Blazor (Interactive Server) admin**
and a **headless JSON API**. No content-type designer, no hand-written migrations, no JavaScript
build step.

```csharp
[CmsPage(DefaultSlug = "")]
public class HomePage : PageBase
{
    [Localized] public string Title { get; set; } = "";
    public BlockArea HeroBlocks { get; set; } = new();
}
```

### Highlights

- 🧩 **Code-first** — refactor your content model in your IDE, not a web form
- 🔌 **Pluggable** — MongoDB / PostgreSQL / SQLite storage, FileSystem / S3 / GCS media
- 🌍 **Localized** — per-locale fields and market-local content scheduling
- 🔐 **Auth built in** — backoffice cookie auth + OIDC/SAML SSO seam
- 📦 **Headless** — public delivery API; render with any frontend, or none

### Coming soon

Klassd is in private development ahead of its first public release. The engine, storage/media
adapters, and a sample host will be published here — open source, MIT licensed — when it ships.

⭐ **Watch this space.** Public packages and source are on the way.

> Built with .NET 10 and Blazor. MIT licensed.
