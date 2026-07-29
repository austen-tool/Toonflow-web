```markdown
# Toonflow-web Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the Toonflow-web repository, a TypeScript codebase built with the Vue framework. You'll learn about file naming, import/export styles, commit message conventions, and how to structure and run tests. This guide ensures consistency and efficiency when contributing to Toonflow-web.

## Coding Conventions

### File Naming
- Use **PascalCase** for all file names.
  - Example: `UserProfile.vue`, `AppHeader.ts`

### Imports
- Use **relative import paths**.
  - Example:
    ```typescript
    import { UserService } from '../services/UserService'
    ```

### Exports
- Use **named exports** (not default).
  - Example:
    ```typescript
    // UserService.ts
    export function getUser() { ... }
    export const USER_ROLE = 'admin'
    ```

### Commit Messages
- Follow **Conventional Commits**.
- Use the `chore` prefix for maintenance commits.
- Average commit message length: ~44 characters.
  - Example:
    ```
    chore: update dependencies to latest version
    ```

## Workflows

_No specific automated workflows detected in this repository._

## Testing Patterns

- **Test file pattern:** `*.test.*`
  - Example: `UserService.test.ts`
- **Testing framework:** Not explicitly detected.
- Place test files alongside the code they test or in a dedicated `tests` directory.
- Example test file structure:
  ```typescript
  // UserService.test.ts
  import { getUser } from './UserService'

  describe('getUser', () => {
    it('returns a user object', () => {
      const user = getUser()
      expect(user).toBeDefined()
    })
  })
  ```

## Commands
| Command | Purpose |
|---------|---------|
| /test   | Run all tests in the repository |
| /lint   | Lint the codebase according to conventions |
| /commit | Generate a conventional commit message template |
```