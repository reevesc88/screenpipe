```markdown
# screenpipe Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and workflows used in the `screenpipe` TypeScript codebase. You'll learn about file naming conventions, import/export styles, dependency update workflows, and testing patterns to ensure consistency and maintainability in your contributions.

## Coding Conventions

### File Naming
- **Style:** kebab-case
- **Example:**  
  ```
  screen-manager.ts
  video-pipeline.ts
  ```

### Import Style
- **Style:** Relative imports
- **Example:**
  ```typescript
  import { ScreenManager } from './screen-manager';
  import { VideoPipeline } from '../utils/video-pipeline';
  ```

### Export Style
- **Style:** Named exports
- **Example:**
  ```typescript
  // In screen-manager.ts
  export function createScreenManager() { ... }

  // In another file
  export const PIPELINE_VERSION = '1.0.0';
  ```

### Commit Patterns
- **Type:** Freeform (no strict prefix required)
- **Average Length:** ~64 characters

## Workflows

### Multi-Package Dependency Update
**Trigger:** When dependencies need to be updated across several packages/modules in the monorepo.  
**Command:** `/update-dependencies-all`

1. Identify outdated dependencies in each package.
2. Update the version numbers in all relevant `package.json` files.
3. Regenerate `package-lock.json` files to reflect new dependency versions.
4. Commit all changed `package.json` and `package-lock.json` files together.

**Files involved:**
- `*/package.json`
- `*/package-lock.json`

**Frequency:** ~2-4 times per month

**Example:**
```bash
/update-dependencies-all
```
This command will automate the process of updating dependencies across all packages.

## Testing Patterns

- **Framework:** Unknown (not explicitly detected)
- **File Pattern:** Test files follow the `*.test.*` naming convention.
  - Example: `screen-manager.test.ts`
- **Location:** Typically alongside the code they test or in a dedicated `__tests__` directory.

**Writing a test example:**
```typescript
// screen-manager.test.ts
import { createScreenManager } from './screen-manager';

describe('createScreenManager', () => {
  it('should initialize with default settings', () => {
    const manager = createScreenManager();
    expect(manager).toBeDefined();
  });
});
```

## Commands

| Command                 | Purpose                                                        |
|-------------------------|----------------------------------------------------------------|
| /update-dependencies-all| Update dependencies across all packages in the monorepo         |
```
