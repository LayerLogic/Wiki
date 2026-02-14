# AGENT.md — LayerLogic Development Guide for AI Agents

> **This file is intended for AI coding assistants** (GitHub Copilot, Cursor, Gemini, Claude, etc.).
> It describes LayerLogic's development conventions, coding standards, and SDLC processes.
> Follow these guidelines when generating, modifying, or reviewing code in this repository.

---

## Company Context

- **Company:** LayerLogic
- **Team size:** 2–3 software engineers
- **Methodology:** Agile with 2-week sprints
- **Regulatory context:** IEC 62304 compliance — all work must be traceable from requirements → design → implementation → testing
- **Domain:** Software that interfaces with hardware (Arduino, sensors, serial communication)

---

## Tech Stack

| Layer                | Technology                  | Notes                                                                                    |
| -------------------- | --------------------------- | ---------------------------------------------------------------------------------------- |
| **Language**         | JavaScript → **TypeScript** | We are actively migrating to TypeScript. **All new code must be written in TypeScript.** |
| **Runtime**          | Node.js (≥ 20.x)            |                                                                                          |
| **Backend**          | Express.js                  | REST APIs                                                                                |
| **Frontend**         | React.js / Vue.js           | Project-dependent — check `package.json`                                                 |
| **Database**         | MongoDB                     | Mongoose ODM for schemas and models                                                      |
| **Infrastructure**   | AWS (EC2, S3, Lambda, RDS)  |                                                                                          |
| **Containerisation** | Docker + Docker Compose     | Used for local dev and deployment                                                        |
| **Package manager**  | npm                         |                                                                                          |

---

## Coding Standards

### TypeScript / JavaScript

#### General Rules

1. **Write TypeScript for all new files.** Do not create new `.js` files. If modifying an existing `.js` file extensively, convert it to `.ts` as part of the change.
2. **Use strict mode.** All TypeScript files must have `strict: true` in `tsconfig.json`.
3. **No `any` type.** Avoid `any` — use proper types, generics, or `unknown` with type guards. If `any` is truly unavoidable, add a `// eslint-disable-next-line` with a comment explaining why.
4. **Prefer `const` over `let`.** Never use `var`.
5. **Use async/await** over `.then()` chains for asynchronous code.
6. **Use arrow functions** for callbacks and anonymous functions. Use named `function` declarations for top-level/exported functions.
7. **Destructure** objects and arrays when accessing multiple properties.
8. **No unused variables or imports.** Ensure the linter passes without warnings.

#### Naming Conventions

| Element                   | Convention                                         | Example                            |
| ------------------------- | -------------------------------------------------- | ---------------------------------- |
| **Variables & functions** | camelCase                                          | `getUserById`, `isActive`          |
| **Constants**             | UPPER_SNAKE_CASE                                   | `MAX_RETRY_COUNT`, `API_BASE_URL`  |
| **Classes & types**       | PascalCase                                         | `UserService`, `DeviceConfig`      |
| **Interfaces**            | PascalCase (no `I` prefix)                         | `UserProfile`, not `IUserProfile`  |
| **Enums**                 | PascalCase (members UPPER_SNAKE_CASE)              | `enum Status { ACTIVE, INACTIVE }` |
| **Files**                 | camelCase for modules, PascalCase for components   | `userService.ts`, `UserCard.vue`   |
| **Directories**           | kebab-case or camelCase (match project convention) | `user-service/` or `userService/`  |
| **Database collections**  | lowercase plural                                   | `users`, `devices`, `testResults`  |
| **Environment variables** | UPPER_SNAKE_CASE                                   | `DATABASE_URL`, `AWS_REGION`       |

#### Code Style

```typescript
// ✅ Good — typed, descriptive, async/await
async function getDeviceById(deviceId: string): Promise<Device | null> {
  const device = await DeviceModel.findById(deviceId);
  if (!device) {
    return null;
  }
  return device;
}

// ❌ Bad — untyped, vague, .then() chain
function getData(id) {
  return Model.findById(id).then(function (result) {
    return result;
  });
}
```

#### Error Handling

- Always use `try/catch` around async operations
- Create descriptive error messages that include context (what was being attempted, what went wrong)
- Never swallow errors silently — at minimum, log them
- Use custom error classes for domain-specific errors when appropriate
- In Express routes, always pass errors to the `next()` middleware or return proper HTTP error responses

```typescript
// ✅ Good
try {
  const device = await getDeviceById(deviceId);
  if (!device) {
    return res.status(404).json({ error: `Device not found: ${deviceId}` });
  }
  return res.json(device);
} catch (error) {
  console.error(`Failed to fetch device ${deviceId}:`, error);
  return res.status(500).json({ error: "Internal server error" });
}
```

#### Imports

- Group imports in this order, separated by a blank line:
  1. Node.js built-in modules (`fs`, `path`, `http`)
  2. Third-party packages (`express`, `mongoose`)
  3. Internal modules (relative imports)
- Use named imports over default imports where possible
- Never use wildcard imports (`import * as`)

```typescript
import { Router, Request, Response } from "express";
import mongoose from "mongoose";

import { DeviceService } from "../services/deviceService";
import { validateDeviceInput } from "../utils/validation";
```

### Express.js / Backend

- Use the **Router pattern** — each resource gets its own router file
- Validate all input using a validation library or middleware (e.g., Joi, Zod, express-validator)
- Never trust client input — sanitise and validate before processing
- Use environment variables for all configuration — never hardcode secrets, URLs, or credentials
- Use proper HTTP status codes (200, 201, 400, 401, 403, 404, 500)
- Keep route handlers thin — business logic belongs in service modules, not controllers

### React / Vue Frontend

- **Components:** One component per file, named with PascalCase
- **State management:** Use the project's existing state management pattern (check for Vuex/Pinia in Vue or Context/Redux in React)
- **Props:** Always type props explicitly (TypeScript interfaces or PropTypes)
- **Styles:** Follow the project's existing CSS approach (check for CSS modules, styled-components, or scoped styles)
- **Accessibility:** Include proper `aria-` attributes, `alt` text on images, and semantic HTML

### MongoDB / Mongoose

- Define schemas with explicit types — never use `Schema.Types.Mixed` without justification
- Add indexes for fields used in queries
- Use Mongoose middleware (`pre`, `post` hooks) for cross-cutting concerns (timestamps, validation)
- Never expose internal MongoDB `_id` fields directly in API responses without intent

---

## Git Workflow

### Branch Naming

All branches must start with the issue/change request number:

```
<issue-number>-short-description

# Examples
104-add-device-endpoint
42-fix-serial-timeout
104-132-refactor-auth-module     # Multiple issues
```

### Commit Messages

```
<Title — max 50 characters, capitalised, no period>

<Body — explain WHAT and WHY, not HOW. Wrap at 72 characters.>

Issue #<number>
```

**Rules:**

- Every commit **must** reference a change request number (`Issue #123`)
- Separate subject from body with a blank line
- Title: imperative mood ("Add endpoint" not "Added endpoint")
- Body: explain **what** and **why**, not how

### Pull Requests

1. Create a PR to merge into `main`
2. Fill in the PR template completely
3. Check off all relevant SDLC activities performed
4. Assign a reviewer before marking as ready
5. All CI checks must pass before merge
6. Delete the branch after merging

---

## Project Structure

Follow the existing project structure. If creating new directories, match the established patterns. Typical structure:

```
project/
├── src/
│   ├── config/          # Configuration, env vars, constants
│   ├── controllers/     # Route handlers (thin — delegate to services)
│   ├── middleware/       # Express middleware
│   ├── models/          # Mongoose schemas and models
│   ├── routes/          # Express routers
│   ├── services/        # Business logic
│   ├── types/           # TypeScript type definitions
│   └── utils/           # Helper/utility functions
├── tests/
│   ├── unit/            # Unit tests
│   └── integration/     # Integration tests
├── docker-compose.yml
├── Dockerfile
├── package.json
├── tsconfig.json
└── AGENT.md             # This file
```

---

## Testing

### Requirements

- **All new features** must have unit tests
- **All bug fixes** must have a regression test that fails before the fix and passes after
- **All API endpoints** should have integration tests
- Tests must pass before a PR can be merged

### Conventions

- Test files go in `tests/` or alongside source files as `*.test.ts` / `*.spec.ts` (match project convention)
- Use descriptive test names that explain the expected behaviour
- Follow the **Arrange → Act → Assert** pattern
- Mock external dependencies (database, APIs, hardware) in unit tests
- Reference requirement IDs in test descriptions when applicable

```typescript
// ✅ Good test structure
describe("DeviceService", () => {
  describe("getDeviceById", () => {
    it("should return the device when a valid ID is provided", async () => {
      // Arrange
      const mockDevice = { _id: "abc123", name: "Sensor A" };
      jest.spyOn(DeviceModel, "findById").mockResolvedValue(mockDevice);

      // Act
      const result = await deviceService.getDeviceById("abc123");

      // Assert
      expect(result).toEqual(mockDevice);
    });

    it("should return null when the device does not exist", async () => {
      jest.spyOn(DeviceModel, "findById").mockResolvedValue(null);
      const result = await deviceService.getDeviceById("nonexistent");
      expect(result).toBeNull();
    });
  });
});
```

---

## Environment Variables

- Store all configuration in environment variables
- Use a `.env` file for local development (never commit `.env` to git)
- Provide a `.env.example` file with placeholder values for all required variables
- Access env vars through a centralised config module, not scattered `process.env` calls

```typescript
// ✅ Good — centralised config
// src/config/index.ts
export const config = {
  port: parseInt(process.env.PORT || "3000", 10),
  databaseUrl: process.env.DATABASE_URL || "mongodb://localhost:27017/dev",
  awsRegion: process.env.AWS_REGION || "eu-north-1",
} as const;

// ❌ Bad — scattered process.env
app.listen(process.env.PORT || 3000);
mongoose.connect(process.env.DATABASE_URL);
```

---

## Docker

- Use multi-stage builds for production images
- Pin base image versions (e.g., `node:20-alpine`, not `node:latest`)
- Use `.dockerignore` to exclude `node_modules`, `.env`, `.git`, and test files
- Docker Compose for local development should include all dependencies (MongoDB, etc.)
- Never store secrets in Dockerfiles or docker-compose files — use environment variables

---

## Dependencies

Before adding a new dependency:

1. **Is it necessary?** Could the functionality be implemented with reasonable effort?
2. **Is it maintained?** Check recent commit activity, number of maintainers, open issues
3. **Is it secure?** Run `npm audit` after adding
4. **Is the license compatible?** Verify it doesn't conflict with our needs
5. **Pin the version** in `package.json` to avoid unexpected breaking changes

---

## Hardware / Serial Communication

Some projects interface with Arduino hardware via serial communication:

- Serial connections can be unreliable — always implement **connection state management** (connected, disconnected, reconnecting)
- Implement **timeouts** for serial reads and writes
- Handle serial port disconnection gracefully — don't crash the application
- Log all serial communication errors for debugging
- Never assume the hardware is connected — always verify connection state before sending commands
- Parse incoming serial data defensively — hardware can send malformed data

---

## Security

- Never commit secrets, API keys, or credentials to the repository
- Use environment variables for all sensitive configuration
- Validate and sanitise all user input on the backend
- Use parameterised queries — never concatenate user input into database queries
- Keep dependencies up to date — run `npm audit` regularly
- Use HTTPS for all external API calls

---

## API Design

- Use RESTful conventions for endpoints:
  - `GET /api/devices` — list all
  - `GET /api/devices/:id` — get one
  - `POST /api/devices` — create
  - `PUT /api/devices/:id` — update (full)
  - `PATCH /api/devices/:id` — update (partial)
  - `DELETE /api/devices/:id` — delete
- Return consistent response shapes:

```typescript
// Success
{ "data": { ... }, "message": "Device created successfully" }

// Error
{ "error": "Device not found", "statusCode": 404 }

// List
{ "data": [...], "total": 42, "page": 1, "limit": 20 }
```

- Use proper HTTP status codes
- Version APIs if breaking changes are needed (`/api/v1/`, `/api/v2/`)
- Document endpoints (inline comments or OpenAPI/Swagger)

---

## What NOT to Do

> These are common mistakes that AI agents tend to make. Avoid them.

1. **Don't create new `.js` files.** Use TypeScript (`.ts` / `.tsx`).
2. **Don't use `any`** without a documented reason.
3. **Don't install dependencies** without evaluating necessity and checking with the team.
4. **Don't commit `.env` files** or any secrets.
5. **Don't use `console.log` for production logging.** Use a structured logger if the project has one, or at least use `console.error` for errors.
6. **Don't create god-files.** Keep files focused — one responsibility per module. If a file exceeds ~300 lines, it probably needs to be split.
7. **Don't skip error handling.** Every async operation needs a `try/catch` or `.catch()`.
8. **Don't use inline styles** in frontend components unless absolutely necessary.
9. **Don't generate placeholder/dummy code** that isn't functional. If you create it, it should work.
10. **Don't change the project structure** without explicit approval. Follow the existing patterns.

---

### Workflow at a Glance

```
Issue Created → Branch → Code → Test → PR → Review → Merge
```

### Key Principles

1. **Every change ties to an issue.** No code changes without a corresponding change request.
2. **Every PR gets reviewed.** No self-merging without documented justification.
3. **Tests are mandatory.** New features need tests. Bug fixes need regression tests.
4. **Documentation matters.** If you change architecture, update the docs.
5. **Traceability is required.** Requirements → Design → Code → Tests must be linked.

---

_This file should be included in the root of every LayerLogic project repository._
