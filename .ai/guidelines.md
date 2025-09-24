# Development Guidelines

## 📝 Versioning and Commit Standards

### Branch Naming Convention
```
<type>/<issue-number>_<description>
```

Example:
- `feat/42_dark_mode`
- `fix/7_memory_leak`
- `docs/13_readme_update`

Note: Always use underscore (_) to separate words in branch names for better readability.

### Commit Message Format
```
<type>: <description> [<reference>]
```

#### Issue References:
- Work in progress: `[refs #7]` or `refs #7: description`
- Completing work: 
  - `[fixes #7]` or `fixes #7: description`
  - `[closes #7]` or `closes #7: description`
  - `[resolves #7]` or `resolves #7: description`

#### Types:
- `feat` - New features
- `fix` - Bug fixes
- `docs` - Documentation changes
- `style` - Formatting, missing semicolons, etc.
- `refactor` - Code restructuring
- `test` - Adding/updating tests
- `chore` - Maintenance tasks

#### Examples:
```
feat: add dark mode support [refs #42]
fix: correct memory calculation [fixes #7]
docs: update installation guide [closes #13]
style: format code according to guidelines [refs #15]
```

## 🔄 Version Control Workflow

1. Always branch from `main`
2. Keep branches focused on single issues
3. Reference issues in commits and PRs
4. Use meaningful commit messages
5. Squash commits before merging when appropriate

## 📋 Pull Request Guidelines

1. Use PR templates
2. Link related issues
3. Include before/after screenshots for UI changes
4. Update documentation if needed
5. Ensure all checks pass
