```markdown
# gateway Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `gateway` TypeScript codebase. You'll learn about file organization, import/export styles, commit conventions, and how to write and run tests. The repository does not use a detected framework, so patterns are framework-agnostic and focus on clean, maintainable TypeScript code.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - **Example:**  
    ```
    user-service.ts
    api-handler.ts
    ```

### Import Style
- Use **relative imports** for internal modules.
  - **Example:**  
    ```typescript
    import { getUser } from './user-service';
    import { handleApi } from '../utils/api-handler';
    ```

### Export Style
- Use **named exports** instead of default exports.
  - **Example:**  
    ```typescript
    // In user-service.ts
    export function getUser(id: string) { ... }
    export const USER_ROLE = 'admin';

    // Importing
    import { getUser, USER_ROLE } from './user-service';
    ```

### Commit Messages
- Follow the **Conventional Commits** standard.
- Use the `chore` prefix for routine changes.
  - **Example:**  
    ```
    chore: update dependencies to latest versions
    ```

## Workflows

### Code Changes and Commits
**Trigger:** When making any code changes  
**Command:** `/commit`

1. Make your code changes following the coding conventions.
2. Stage your changes:  
   ```
   git add .
   ```
3. Commit using a conventional commit message (e.g., `chore: update dependencies`):  
   ```
   git commit -m "chore: update dependencies"
   ```
4. Push your changes to the repository:  
   ```
   git push
   ```

### Writing and Running Tests
**Trigger:** When adding new features or fixing bugs  
**Command:** `/test`

1. Create a test file named with the pattern `*.test.*` (e.g., `user-service.test.ts`).
2. Write your tests using your preferred testing framework.
3. Run your tests using the appropriate command (framework not detected; commonly `npm test` or `yarn test`).
4. Ensure all tests pass before committing.

## Testing Patterns

- Test files follow the pattern: `*.test.*`
  - **Example:**  
    ```
    user-service.test.ts
    ```
- The testing framework is not specified; use standard TypeScript testing tools (e.g., Jest, Mocha).
- Place tests alongside the code they test or in a dedicated `tests` directory.

  **Example Test File:**
  ```typescript
  // user-service.test.ts
  import { getUser } from './user-service';

  describe('getUser', () => {
    it('returns user data for valid id', () => {
      const user = getUser('123');
      expect(user).toBeDefined();
    });
  });
  ```

## Commands
| Command    | Purpose                                      |
|------------|----------------------------------------------|
| /commit    | Guide for making and committing code changes |
| /test      | Steps for writing and running tests          |
```
