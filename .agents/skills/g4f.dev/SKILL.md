```markdown
# g4f.dev Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and workflows used in the `g4f.dev` JavaScript codebase. You'll learn about file naming conventions, import/export styles, commit message standards, and how to update translations and UI components effectively. The guide also covers testing patterns and provides handy commands for common development tasks.

## Coding Conventions

- **File Naming:**  
  Use `camelCase` for file names.  
  _Example:_  
  ```
  components.js
  translations.js
  router.js
  ```

- **Import Style:**  
  Use relative imports for modules.  
  _Example:_  
  ```js
  import { translate } from './translations.js';
  import { MyComponent } from './components.js';
  ```

- **Export Style:**  
  Use named exports.  
  _Example:_  
  ```js
  // translations.js
  export function translate(key) { ... }
  export const supportedLanguages = ['en', 'es', 'fr'];
  ```

- **Commit Messages:**  
  Follow the [Conventional Commits](https://www.conventionalcommits.org/) style, using prefixes like `feat`.  
  _Example:_  
  ```
  feat: add support for new language in translations
  ```

## Workflows

### Update Translation and UI Workflow
**Trigger:** When someone wants to add or update translations and refine UI components or navigation.  
**Command:** `/update-translation-ui`

1. **Edit or add translation keys** in `playground/js/snippets.json`.
2. **Update `translations.js`** to handle new or changed keys.
   ```js
   // translations.js
   export function translate(key) {
     return translations[key] || key;
   }
   ```
3. **Modify UI components** in `components.js` to use updated translations.
   ```js
   // components.js
   import { translate } from './translations.js';
   // Usage in a component
   const label = translate('welcome_message');
   ```
4. **Update `router.js` or `store.js`** if navigation or application state is affected by translation changes.
5. **Adjust `index.html`** if necessary for UI changes (e.g., adding language selectors).

**Files Involved:**
- `playground/js/snippets.json`
- `playground/js/translations.js`
- `playground/js/components.js`
- `playground/js/router.js`
- `playground/js/store.js`
- `playground/index.html`

**Frequency:** ~2x/month

## Testing Patterns

- **Test Framework:** Unknown (not detected).
- **Test File Pattern:** Test files are named with the pattern `*.test.*`.
  _Example:_  
  ```
  components.test.js
  translations.test.js
  ```
- **Test Structure:**  
  Place test files alongside the modules they test, following the naming pattern above.

## Commands

| Command                | Purpose                                                          |
|------------------------|------------------------------------------------------------------|
| /update-translation-ui | Update translation keys and UI components for multilingual support |
```
