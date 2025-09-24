# 🤝 Contributing to Lightweight Spring Actuator Observer

First off, thank you for considering contributing to this project! 🎉

---

**Author:** [fhgomes](https://github.com/fhgomes/fhgomes)
**Contact:** tech.fernando.gomes@gmail.com

---

## 📋 Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)

## 📜 Code of Conduct

This project adheres to a [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## 🛠 How Can I Contribute?

### 🐛 Reporting Bugs
- Use the [bug report template](.github/ISSUE_TEMPLATE/bug_report.md)
- Check if the bug was already reported in [Issues](https://github.com/fhgomes/lightweight-spring-actuator-monitor/issues)
- Provide detailed steps to reproduce the issue
- Include browser information and console errors

### 💡 Suggesting Features
- Use the [feature request template](.github/ISSUE_TEMPLATE/feature_request.md)
- Explain the problem you're trying to solve
- Describe the solution you'd like
- Consider alternative solutions

### 🔧 Code Contributions
- Bug fixes
- New metrics support
- UI/UX improvements
- Performance optimizations
- Documentation improvements

## 🚀 Development Setup

Since this is a simple HTML/CSS/JavaScript project, setup is minimal:

1. **Fork** the repository on GitHub
2. **Clone** your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/lightweight-spring-actuator-monitor.git
   cd lightweight-spring-actuator-monitor
   ```

3. **Open** the HTML file in your browser for testing
4. **Test** with a running Spring Boot application with Actuator enabled

### 🧪 Testing Your Changes
- Test with different Spring Boot versions (2.x, 3.x)
- Verify compatibility with major browsers (Chrome, Firefox, Safari, Edge)
- Test responsive design on mobile devices
- Check console for JavaScript errors

## 📝 Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification with additional issue referencing:

### Branch Naming Convention
```
<type>/<issue-number>_<description>
```

Examples:
- `feat/42_dark_mode`
- `fix/7_memory_leak`
- `docs/13_readme_update`

### Commit Message Format
```
<type>: <description> [<reference>]
```

#### Issue References
- For work in progress:
  ```
  feat: implement dark mode [refs #42]
  feat: add initial theme support refs #42: still working on color scheme
  ```

- For completing work:
  ```
  fix: resolve memory calculation [fixes #7]
  docs: update browser support [closes #13]
  feat: add CPU chart [resolves #15]
  ```

### Types
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Code formatting (no functional changes)
- **refactor**: Code restructuring (no functional changes)
- **test**: Adding or updating tests
- **chore**: Maintenance tasks

### Examples
```bash
feat: add CPU usage trending chart [refs #15]

Implements a mini chart showing CPU usage over the last 10 data points
to help identify usage patterns and spikes.

feat: complete CPU monitoring implementation [fixes #15]

The timer wasn't being properly cleared when switching tabs,
causing multiple timers to run simultaneously.

docs: update README with browser compatibility info [refs #18]

Adds section explaining which browsers are supported and
known limitations with older versions.
```

### Issue Reference Keywords
- `[refs #123]` or `refs #123:` - References issue without closing
- `[fixes #123]` or `fixes #123:` - Closes issue
- `[closes #123]` or `closes #123:` - Closes issue
- `[resolves #123]` or `resolves #123:` - Closes issue

Note: The reference can be placed either in square brackets at the end of the first line or with a colon after the reference at the start of the description.

## 🔄 Pull Request Process

1. **Create a branch** from `main`:
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix
   ```

2. **Make your changes** following the coding standards

3. **Test thoroughly**:
	- Test in multiple browsers
	- Test with different screen sizes
	- Test error scenarios (invalid URLs, network errors)

4. **Commit your changes** following the commit guidelines:
   ```bash
   git add .
   git commit -m "feat: add new awesome feature"
   ```

5. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create a Pull Request**:
	- Use the PR template
	- Link related issues
	- Provide clear description of changes
	- Add screenshots if UI changes

### 📋 PR Checklist
- [ ] Code follows existing style and conventions
- [ ] Changes have been tested in multiple browsers
- [ ] Documentation updated (if needed)
- [ ] Commit messages follow conventional commits
- [ ] PR title describes the change clearly
- [ ] Related issues are linked

## 🎨 Coding Standards

### HTML
- Use semantic HTML5 elements
- Maintain consistent indentation (2 spaces)
- Add meaningful comments for complex sections

### CSS
- Follow BEM methodology when possible
- Use consistent naming conventions
- Group related properties together
- Use CSS custom properties for theming

### JavaScript
- Use modern ES6+ syntax
- Add comments for complex logic
- Handle errors gracefully
- Use consistent naming (camelCase)
- Avoid global variables

### 📱 Responsive Design
- Test on mobile, tablet, and desktop
- Use CSS Grid and Flexbox
- Ensure touch-friendly interface

## 🐛 Bug Reports

When reporting bugs, please include:
- **Browser** and version
- **Operating System**
- **Steps to reproduce** the issue
- **Expected behavior**
- **Actual behavior**
- **Screenshots** (if applicable)
- **Console errors** (if any)

## 💡 Feature Requests

When requesting features, consider:
- **Problem**: What problem does this solve?
- **Solution**: What would you like to see?
- **Alternatives**: Any alternative solutions?
- **Additional context**: Screenshots, examples, etc.

## 🏷️ Labels

We use these labels to categorize issues and PRs:
- `bug` - Something isn't working
- `enhancement` - New feature or improvement
- `documentation` - Documentation improvements
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention needed
- `question` - Further information requested

## 🎉 Recognition

Contributors will be recognized in our README.md file and release notes.

## 📞 Questions?

Feel free to:
- Open a [Discussion](https://github.com/fhgomes/lightweight-spring-actuator-monitor/discussions)
- Create an [Issue](https://github.com/fhgomes/lightweight-spring-actuator-monitor/issues)

Thank you for contributing! 🚀
