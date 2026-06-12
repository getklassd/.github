<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/getklassd/.github/main/profile/assets/klassd-wordmark.png">
    <img alt="Klassd" src="https://raw.githubusercontent.com/getklassd/.github/main/profile/assets/klassd-wordmark-light.png" width="360">
  </picture>
</p>

<p align="center">
  <strong>Code-first, NuGet-distributed building blocks for .NET.</strong><br>
  Define it as plain C# classes — get the admin, the API, and the infrastructure for free.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/.NET-10.0-512BD4.svg" alt=".NET 10">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT">
  <a href="https://www.nuget.org/profiles/getklassd"><img src="https://img.shields.io/badge/NuGet-getklassd-004880.svg" alt="NuGet"></a>
  <a href="https://getklassd.com"><img src="https://img.shields.io/badge/web-getklassd.com-FF6F61.svg" alt="getklassd.com"></a>
</p>

---

### Projects

| Project | What it is | Links |
|---|---|---|
| **Klassd** | A code-first, headless **CMS** for .NET. Declare pages, blocks and property types as C# classes; the engine reflects over them to drive a Blazor admin and a headless JSON API — no content-type designer, no hand-written migrations, no JS build step. | [repo](https://github.com/getklassd/Klassd) · [docs](https://getklassd.com/docs) · [NuGet](https://www.nuget.org/profiles/getklassd) |
| **Klassd.Workflows** | A code-first background-job & **workflow engine** for .NET. Jobs are C# classes that run as their own Kubernetes pod (or a local process in dev); compose them into DAG workflows and watch each run live. | [repo](https://github.com/getklassd/Klassd.Workflows) · [docs](https://getklassd.com/workflows) · [NuGet](https://www.nuget.org/profiles/getklassd) |
| **Klassd.Auth** | A self-hostable **authentication** core for .NET — email/password, sessions, social login & SSO (OIDC, Microsoft Entra ID), MFA and per-user metadata, behind storage-agnostic SQLite / PostgreSQL / MongoDB adapters. Powers sign-in for Klassd and Klassd.Workflows. | [repo](https://github.com/getklassd/Klassd.Auth) · [docs](https://getklassd.com/auth) · [NuGet](https://www.nuget.org/profiles/getklassd) |

All three are in **public beta** (`0.0.x`), MIT licensed, and published to NuGet.org.

### The idea

Your schema and your infrastructure live in your **codebase**, not in a UI. You write C# classes;
Klassd reflects over them to give you the admin screens, the APIs, and the wiring. Refactor in your
IDE, review in pull requests, ship as NuGet packages — no separate modelling tool to keep in sync.

```csharp
// Klassd — a content type is just a class
[CmsPage(DefaultSlug = "")]
public class HomePage : PageBase
{
    [Localized] public string Title { get; set; } = "";
    public BlockArea HeroBlocks { get; set; } = new();
}

// Klassd.Workflows — a job is just a class
public sealed class NightlyReport : IJob
{
    public async Task RunAsync(IJobContext ctx) => ctx.Log("running…");
}
```

### Highlights

- 🧩 **Code-first** — model content and jobs in C#, refactor in your IDE, not a web form
- 🔌 **Pluggable** — swap storage (MongoDB / PostgreSQL / SQLite), media (FileSystem / S3 / GCS) and artifact backends
- ☸️ **Cloud-native** — Klassd.Workflows runs each job as its own Kubernetes pod, the same worker runs locally
- 🔐 **Auth as a building block** — Klassd.Auth: email/password, sessions, OIDC/Entra SSO and MFA, used by both the CMS and Workflows
- 📦 **Headless & NuGet-native** — public delivery API; compose only the packages you wire up

### Get started

```bash
# The CMS
dotnet add package Klassd.Backoffice --prerelease
dotnet add package Klassd.Data.Sqlite --prerelease

# The workflow engine
dotnet add package Klassd.Workflows.Core --prerelease

# Authentication
dotnet add package Klassd.Auth.Core --prerelease
dotnet add package Klassd.Auth.AspNetCore.Cookies --prerelease
```

Full quickstarts, screenshots and guides are at **[getklassd.com](https://getklassd.com)**.

> Built with .NET 10 and Blazor. MIT licensed. ⭐ Star the repos if you find them useful.
