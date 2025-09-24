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
[<reference>] <type>: <description>
```

#### Issue References:
- Work in progress: `[refs #7]`
- Completing work: 
  - `[fixes #7]`
  - `[closes #7]`
  - `[resolves #7]`

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
[refs #42] feat: add dark mode support
[fixes #7] fix: correct memory calculation
[closes #13] docs: update installation guide
[refs #15] style: format code according to guidelines
```

## 🔄 Version Control Workflow

1. Always branch from `main`
2. Keep branches focused on single issues
3. Reference issues in commits and PRs
4. Use meaningful commit messages
5. Squash commits before merging when appropriate

## 📋 Pull Request Guidelines

### PR Creation Process
1. Ensure your branch is up to date with main
2. Follow the PR template structure
3. Use descriptive titles with issue references
4. Include appropriate labels

### Required Content
1. Clear description of changes
2. Screenshots for UI changes
3. List of tested browsers
4. Documentation updates if needed
5. Completion of PR checklist

### PR Checklist
- [ ] Branch follows naming convention
- [ ] Commits are properly formatted with issue references
- [ ] Changes are tested across supported browsers
- [ ] Documentation is updated
- [ ] Code follows project standards
- [ ] No unnecessary file changes

### Review Process
1. Address reviewer comments promptly
2. Squash commits when requested
3. Keep PR focused and small
4. Update branch when needed
5. Add test cases for bug fixes

For more detailed contribution guidelines, see [CONTRIBUTING.md](../CONTRIBUTING.md).
