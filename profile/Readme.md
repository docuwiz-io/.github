<img width="2204" height="1416" alt="image" src="https://github.com/user-attachments/assets/ca09a80e-624c-475f-95fa-2e31411ecaa0" />


# Docuwiz

**The only Docs-as-Code platform with built-in collaboration, versioning, and AI linting to create accurate, complete, and usable API docs.**

[Website](https://www.docuwiz.io) · [Documentation](https://docs.docuwiz.io) · [Changelog](./CHANGELOG.md) · [Roadmap](./ROADMAP.md)

---

## What is Docuwiz?

Docuwiz is a documentation hub where API teams author, preview, and publish guides and API references in a single collaborative workspace. It combines a rich content editor, OpenAPI automation, Git-based version control, and an interactive API console — so your docs stay accurate, up to date, and genuinely useful to developers.

> "The clear structure defined by the Docs as Code configuration files organizes the navigation menu neatly for all users."

---

## Core features

### Docs-as-Code authoring
Write in Markdown with rich blocks — code snippets, tables, callouts, images, and custom components. Configuration files define your navigation structure, keeping docs organized as your product grows.

### Automated API references
Import an OpenAPI Specification (OAS) and Docuwiz generates a full, interactive API reference automatically. Parameters, response schemas, error codes, and examples are rendered cleanly — no manual effort required.

### AI linting
Docuwiz validates your OAS in real time. The linter enforces your API style guide, catches missing descriptions, inconsistent naming, and schema errors before they reach users — reducing support tickets upstream.

### Interactive API console
Developers can make live test calls directly from your API reference pages. No separate API client needed — try requests, inspect responses, and debug right in the docs.

### Git version control
Every change — including typos — is tracked. Docuwiz integrates with your Git workflow so documentation lives alongside code, with branching, pull request reviews, and full history.

### Collaboration
Technical writers, engineers, and product managers work in one workspace. Comments, reviews, and real-time editing keep teams aligned.

---

## Quick start

```bash
# Install the Docuwiz CLI
npm install -g @docuwiz/cli

# Authenticate
docuwiz login

# Initialize a new project
docuwiz init my-api-docs

# Preview locally
cd my-api-docs
docuwiz dev
```

Then visit `http://localhost:3000` to see your docs live.

→ Full quickstart guide: [docs.docuwiz.io/quickstart](https://docs.docuwiz.io/quickstart)

---

## Import your OpenAPI spec

```bash
docuwiz import openapi ./openapi.yaml
```

Docuwiz parses your spec and scaffolds a full API reference including all paths, operations, parameters, request bodies, and response schemas.

---

## Project structure

```
my-api-docs/
├── docuwiz.config.json    # Navigation, theme, and project settings
├── docs/
│   ├── quickstart.md      # Getting started guide
│   ├── authentication.md  # Auth guide
│   └── guides/            # How-to guides
├── api/
│   └── openapi.yaml       # Your OpenAPI spec (source of truth)
└── .github/
    └── workflows/
        └── docuwiz.yml    # CI/CD validation
```

---

## Configuration

`docuwiz.config.json` controls navigation, versioning, and theme:

```json
{
  "name": "My API Docs",
  "logo": "./assets/logo.svg",
  "primaryColor": "#5C4EE5",
  "navigation": [
    {
      "group": "Getting started",
      "pages": ["quickstart", "authentication", "errors"]
    },
    {
      "group": "API reference",
      "pages": ["api/overview", "api/endpoints"]
    }
  ],
  "versions": ["v1", "v2"],
  "openapi": "./api/openapi.yaml"
}
```

---

## Integrations

| Tool | What it does |
|---|---|
| GitHub Actions | Validate OAS and lint docs on every PR |
| GitLab CI | Same as above for GitLab workflows |
| VS Code extension | Preview and lint locally inside your editor |
| Slack | Notify your team when docs are published |

→ See [`/integrations`](./integrations/) for ready-to-use workflow files.

---

## Comparison

| Feature | Docuwiz | Mintlify | GitBook | ReadMe |
|---|---|---|---|---|
| Docs-as-Code (Git-native) | ✅ | ✅ | Partial | ❌ |
| AI linting (OAS validation) | ✅ | ❌ | ❌ | ❌ |
| Interactive API console | ✅ | ✅ | ❌ | ✅ |
| Automated API reference | ✅ | ✅ | ❌ | ✅ |
| Real-time collaboration | ✅ | ❌ | ✅ | ❌ |
| Built-in versioning | ✅ | Partial | ✅ | ✅ |
| Self-hostable | Coming soon | ❌ | ❌ | ❌ |

---

## Examples

See the [`/examples`](./examples/) folder for:

- Sample `docuwiz.config.json` for different team setups
- A complete OpenAPI spec (Petstore) with Docuwiz output
- GitHub Actions workflow for CI/CD validation
- Multi-version docs setup

---

## Links

- **Docs:** [docs.docuwiz.io](https://docs.docuwiz.io)
- **Website:** [docuwiz.io](https://www.docuwiz.io)
- **Issues:** [GitHub Issues](../../issues)
- **Discussions:** [GitHub Discussions](../../discussions)
- **Security:** [SECURITY.md](./SECURITY.md)

---

## License

See [LICENSE](./LICENSE) for details.
