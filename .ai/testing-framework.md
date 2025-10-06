# AI Agent Testing Framework

**Version**: 1.0.0  
**Last Updated**: 2025-10-05
**Maintainer**: AI Documentation System

## 📋 Overview
This document provides a comprehensive testing framework for AI agents to validate their changes and ensure quality before submission.

## 🧪 Testing Procedures

### Pre-Change Analysis
Before making any changes, AI agents should:

1. **Identify Impact Scope**
   - Determine which files will be modified
   - Assess potential side effects
   - Check dependencies and references

2. **Create Test Plan**
   - Define what needs to be tested
   - Identify success criteria
   - Plan rollback strategy if needed

### Change Validation Steps

#### For Code Changes (dashboard-monitor.html)
1. **Syntax Validation**
   - Check HTML structure validity
   - Validate CSS syntax
   - Verify JavaScript syntax

2. **Functional Testing**
   - Test core monitoring functionality
   - Verify API connectivity
   - Test responsive design
   - Check browser compatibility

3. **Performance Testing**
   - Measure load times
   - Check memory usage
   - Verify refresh mechanisms

#### For Documentation Changes
1. **Content Validation**
   - Check markdown syntax
   - Verify internal links
   - Test external references

2. **Structure Consistency**
   - Ensure proper heading hierarchy
   - Check formatting consistency
   - Verify version information

3. **Cross-Reference Validation**
   - Check links between documents
   - Verify referenced files exist
   - Ensure consistency across related docs

### Testing Commands

#### HTML/CSS/JS Validation
```powershell
# Check HTML syntax (requires validation tool)
Get-Content "dashboard-monitor.html" | Select-String -Pattern "<[^>]*>" | ForEach-Object { $_.Line }

# Check for JavaScript syntax errors (basic check)
Get-Content "dashboard-monitor.html" | Select-String -Pattern "function|var|let|const" | ForEach-Object { $_.Line }
```

#### Link Validation
```powershell
# Check for broken internal links
Get-Content "*.md" | Select-String -Pattern "\[.*\]\(.*\.md\)" | ForEach-Object { $_.Line }

# Verify referenced files exist
$links = Get-Content "*.md" | Select-String -Pattern "\[.*\]\(([^)]+)\)" | ForEach-Object { $_.Matches.Groups[1].Value }
$links | ForEach-Object { if (-not (Test-Path $_)) { Write-Host "Missing: $_" } }
```

## 🔄 Documentation Update Workflows

### When AI Instructions Change
1. **Update .ai/README.md**
   - Increment version number
   - Update last modified date
   - Add changelog entry

2. **Update .ai/changelog.md**
   - Add new version entry
   - Document all changes made
   - Follow semantic versioning

### When Project Code Changes
1. **Update main CHANGELOG.md**
   - Increment project version
   - Document functional changes
   - Follow Keep a Changelog format

2. **Update README.md version references**
   - Update version badges if present
   - Sync version numbers across docs

## 📝 Version Management

### AI Documentation Versioning
- **Current Version**: Check `.ai/changelog.md` header
- **Increment Rules**:
  - MAJOR: Breaking changes to AI instructions
  - MINOR: New AI guidance or significant additions
  - PATCH: Fixes, clarifications, minor improvements

### Project Versioning  
- **Current Version**: Check `CHANGELOG.md` header
- **Increment Rules**:
  - MAJOR: Breaking changes to functionality
  - MINOR: New features or significant enhancements
  - PATCH: Bug fixes and minor improvements

## 🛠 Automated Checks

### Pre-Submission Checklist
```markdown
- [ ] All syntax validated
- [ ] Functional tests passed
- [ ] Documentation updated
- [ ] Version numbers incremented
- [ ] Changelog entries added
- [ ] Links verified
- [ ] Cross-references checked
- [ ] Commit message prepared
```

### Quality Gates
1. **Code Quality**
   - No syntax errors
   - Maintains single-file architecture
   - Preserves browser compatibility

2. **Documentation Quality**
   - Clear and concise language
   - Proper markdown formatting
   - Consistent versioning

3. **Integration Quality**
   - No broken links
   - Consistent cross-references
   - Aligned version numbers

## 🚀 Testing Workflow Example

### Step 1: Pre-Change Assessment
```powershell
# Check current versions
Get-Content ".ai\changelog.md" | Select-String "Version"
Get-Content "CHANGELOG.md" | Select-String "## \["
```

### Step 2: Make Changes
- Implement required modifications
- Follow coding standards
- Maintain documentation consistency

### Step 3: Validate Changes
```powershell
# Test HTML structure (basic)
$html = Get-Content "dashboard-monitor.html" -Raw
if ($html -match "<html.*>.*</html>") { Write-Host "✓ HTML structure valid" }

# Check for JavaScript errors (basic)
if ($html -match "function.*{.*}") { Write-Host "✓ JavaScript functions present" }

# Validate markdown files
Get-ChildItem "*.md" | ForEach-Object {
    $content = Get-Content $_.FullName -Raw
    if ($content -match "^# ") { Write-Host "✓ $($_.Name) has proper heading" }
}
```

### Step 4: Update Documentation
- Increment appropriate version numbers
- Add changelog entries
- Update cross-references

### Step 5: Final Validation
```powershell
# Verify all changes are consistent
Write-Host "=== Final Validation ==="
Write-Host "AI Docs Version:" (Get-Content ".ai\changelog.md" | Select-String "Version" | Select-Object -First 1)
Write-Host "Project Version:" (Get-Content "CHANGELOG.md" | Select-String "## \[" | Select-Object -First 1)
Write-Host "All checks completed!"
```

## 📋 Success Criteria

### For Code Changes
- ✅ Functionality preserved or enhanced
- ✅ No new errors introduced
- ✅ Performance maintained or improved
- ✅ Documentation updated

### For Documentation Changes
- ✅ Information accurate and current
- ✅ Formatting consistent
- ✅ Links functional
- ✅ Versions synchronized

## 🔧 Tools and Resources

### Validation Tools
- PowerShell commands for basic checks
- Browser developer tools for testing
- Markdown validators (online tools)
- Link checkers for documentation

### Reference Materials
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)
- [Markdown Guide](https://www.markdownguide.org/)
- Project's `.ai/guidelines.md` for standards

---

*This testing framework ensures consistent quality and proper documentation maintenance across all AI agent contributions.*
