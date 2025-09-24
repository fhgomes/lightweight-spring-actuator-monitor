# Development Guidelines

## 📝 Versioning and Commit Standards

### Semantic Versioning
We follow [Semantic Versioning 2.0.0](https://semver.org/):

```
MAJOR.MINOR.PATCH

Example: 1.1.0
```

- **MAJOR**: Incompatible API changes
- **MINOR**: New features (backwards-compatible)
- **PATCH**: Bug fixes (backwards-compatible)

Version numbers should never contain leading zeros.

### Version Bumping Guidelines
- Breaking changes -> MAJOR bump (e.g., 1.1.0 -> 2.0.0)
- New features -> MINOR bump (e.g., 1.0.0 -> 1.1.0)
- Bug fixes -> PATCH bump (e.g., 1.1.0 -> 1.1.1)

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

### GitHub Integration and Issue Closing

#### Automatic Issue Closing
GitHub automatically closes issues when specific keywords are used in commit messages pushed to the default branch (`main` or `master`).

**✅ Correct Keywords for Auto-Closing:**
- `[fixes #7]` - Closes issue #7
- `[closes #7]` - Closes issue #7  
- `[resolves #7]` - Closes issue #7

**❌ Common Mistakes (Won't Close Issues):**
- `[refs #7]` - Only references, doesn't close
- `[fix #7]` - Missing 's' at the end
- `[close #7]` - Missing 's' at the end
- `[resolved #7]` - Wrong tense
- `fixes #7` - Missing brackets (project format requirement)
- `[fixes#7]` - Missing space after keyword

#### Closing Multiple Issues

**❌ Incorrect Format (Won't Work):**
```
[closes #8 #9 #11] feat: add memory monitoring
```

**✅ Correct Formats:**

**Option 1: Multiple bracket references**
```
[closes #8] [closes #9] [closes #11] feat: add memory monitoring
```

**Option 2: Main issue in brackets, others in body (Recommended)**
```
[closes #8] feat: add real-time memory monitoring

Closes #9
Closes #11

- Replace static memory values with live data
- Add trending indicators and historical tracking
- Implement progress bars and usage visualization
```

**Option 3: Mixed keywords in body**
```
[closes #8] feat: add real-time memory monitoring

Fixes #9
Resolves #11
```

#### Integration Requirements

For automatic issue closing to work:

1. **Default Branch**: Commit must be pushed to repository's default branch
2. **Repository Access**: Must have write access to the repository
3. **Issue Existence**: Referenced issues must exist in the same repository
4. **Exact Format**: Follow the project's bracket format exactly: `[keyword #number]`

#### Troubleshooting Common Issues

**Problem**: "My commit message didn't close the GitHub issue"

**Checklist**:
- [ ] Used correct closing keyword (`fixes`, `closes`, `resolves`)
- [ ] Issue number exists in the same repository
- [ ] Commit was pushed to the default branch (not a feature branch)
- [ ] Used project's bracket format: `[closes #7]`
- [ ] Keyword is lowercase
- [ ] Space exists between keyword and issue number

**Feature Branch Workflow**: 
If working on feature branches, issues close when the branch is merged to `main`, not on individual commits to the feature branch.

#### Advanced Examples

**Complex Feature with Multiple Related Issues:**
```
[closes #42] feat: implement comprehensive memory monitoring dashboard

Closes #43: Add real-time metric updates
Closes #44: Implement trending indicators
Resolves #45: Add educational tooltips and documentation

- Integrates Spring Boot Actuator endpoints for live data
- Adds historical tracking with up/down trend arrows  
- Implements progress bars with color-coded usage indicators
- Includes comprehensive help documentation for memory metrics
- Updates UI responsiveness across all memory visualization sections
```

**Bug Fix with Related Enhancement:**
```
[fixes #28] fix: resolve NaN values in memory calculations

Closes #29: Add graceful degradation for missing metrics

- Implements proper error handling for startup scenarios
- adds loading states when metrics are not yet available
- Includes defensive programming patterns for edge cases
- Updates user feedback during application initialization
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
