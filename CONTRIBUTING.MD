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
- Check if the bug was already reported in [Issues](https://github.com/fhgomes/lightweight-spring-actuator-observer/issues)
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
   git clone https://github.com/YOUR-USERNAME/lightweight-spring-actuator-observer.git
   cd lightweight-spring-actuator-observer
   ```

3. **Open** the HTML file in your browser for testing
4. **Test** with a running Spring Boot application with Actuator enabled

### 🧪 Testing Your Changes
- Test with different Spring Boot versions (2.x, 3.x)
- Verify compatibility with major browsers (Chrome, Firefox, Safari, Edge)
- Test responsive design on mobile devices
- Check console for JavaScript errors

## 📝 Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Commit Message Format
```
<type>(<scope>): <subject>

<body>

<footer>
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
feat: add CPU usage trending chart

Implements a mini chart showing CPU usage over the last 10 data points
to help identify usage patterns and spikes.

Fixes #15

fix: resolve memory leak in auto-refresh timer

The timer wasn't being properly cleared when switching tabs,
causing multiple timers to run simultaneously.

Closes #23

docs: update README with browser compatibility info

Adds section explaining which browsers are supported and
known limitations with older versions.

Refs #18
```

### Linking to Issues
- `Fixes #123` - Closes issue #123
- `Closes #123` - Closes issue #123
- `Resolves #123` - Closes issue #123
- `Refs #123` - References issue #123 without closing

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
- Open a [Discussion](https://github.com/fhgomes/lightweight-spring-actuator-observer/discussions)
- Create an [Issue](https://github.com/fhgomes/lightweight-spring-actuator-observer/issues)

Thank you for contributing! 🚀