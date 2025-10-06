# Automated Documentation Update System

**Version**: 1.0.0  
**Last Updated**: 2025-10-05
**Maintainer**: AI Documentation System

## 📋 Overview
This document provides automated workflows and scripts for AI agents to systematically update documentation, manage versions, and generate commit messages when making changes.

## 🔄 Automated Update Workflows

### For AI Documentation Changes

#### PowerShell Script: Update AI Documentation
```powershell
# AI Documentation Update Script
function Update-AIDocumentation {
    param(
        [string]$ChangeType,    # "major", "minor", "patch"
        [string]$Description,   # Brief description of changes
        [string]$Details        # Detailed changes for changelog
    )
    
    $currentDate = Get-Date -Format "yyyy-MM-dd"
    
    # Read current AI version
    $changelogContent = Get-Content ".ai\changelog.md" -Raw
    $currentVersion = ($changelogContent | Select-String "Version.*?(\d+\.\d+\.\d+)" | Select-Object -First 1).Matches.Groups[1].Value
    
    # Calculate new version
    $versionParts = $currentVersion.Split('.')
    $major = [int]$versionParts[0]
    $minor = [int]$versionParts[1]
    $patch = [int]$versionParts[2]
    
    switch ($ChangeType) {
        "major" { $major++; $minor = 0; $patch = 0 }
        "minor" { $minor++; $patch = 0 }
        "patch" { $patch++ }
    }
    
    $newVersion = "$major.$minor.$patch"
    
    # Update .ai/README.md
    $readmeContent = Get-Content ".ai\README.md" -Raw
    $readmeContent = $readmeContent -replace "Version.*?: .*", "Version**: $newVersion  "
    $readmeContent = $readmeContent -replace "Last Updated.*?: .*", "Last Updated**: $currentDate"
    Set-Content ".ai\README.md" $readmeContent
    
    # Update .ai/changelog.md
    $newEntry = @"
### [$newVersion] - $currentDate

$Details

"@
    
    $changelogContent = $changelogContent -replace "## Version History", "## Version History`n`n$newEntry"
    $changelogContent = $changelogContent -replace "Version.*?: .*", "Version**: $newVersion  "
    $changelogContent = $changelogContent -replace "Last Updated.*?: .*", "Last Updated**: $currentDate"
    Set-Content ".ai\changelog.md" $changelogContent
    
    Write-Host "✅ AI Documentation updated to version $newVersion"
    return $newVersion
}
```

#### Usage Examples:
```powershell
# For major AI instruction changes
Update-AIDocumentation -ChangeType "major" -Description "Breaking changes to AI workflow" -Details @"
#### Changed
- **AI Workflow Restructure**
  - Complete redesign of testing framework
  - New automated update system implementation
  - Breaking changes to existing AI instruction format

#### Added
- **Automated Documentation Updates**
  - PowerShell scripts for version management
  - Systematic changelog generation
  - Commit message automation
"@

# For minor additions
Update-AIDocumentation -ChangeType "minor" -Description "Added testing framework" -Details @"
#### Added
- **AI Agent Testing Framework**
  - Comprehensive validation procedures
  - Automated quality checks
  - Pre-submission checklists
"@

# For patches/fixes
Update-AIDocumentation -ChangeType "patch" -Description "Fixed documentation links" -Details @"
#### Fixed
- **Documentation Links**
  - Corrected broken internal references
  - Updated file path references
  - Enhanced cross-document navigation
"@
```

### For Project Code Changes

#### PowerShell Script: Update Project Documentation
```powershell
# Project Documentation Update Script
function Update-ProjectDocumentation {
    param(
        [string]$ChangeType,    # "major", "minor", "patch"
        [string]$Description,   # Brief description of changes
        [string]$Details        # Detailed changes for changelog
    )
    
    $currentDate = Get-Date -Format "yyyy-MM-dd"
    
    # Read current project version
    $changelogContent = Get-Content "CHANGELOG.md" -Raw
    $currentVersion = ($changelogContent | Select-String "## \[(\d+\.\d+\.\d+)\]" | Select-Object -First 1).Matches.Groups[1].Value
    
    # Calculate new version
    $versionParts = $currentVersion.Split('.')
    $major = [int]$versionParts[0]
    $minor = [int]$versionParts[1]
    $patch = [int]$versionParts[2]
    
    switch ($ChangeType) {
        "major" { $major++; $minor = 0; $patch = 0 }
        "minor" { $minor++; $patch = 0 }
        "patch" { $patch++ }
    }
    
    $newVersion = "$major.$minor.$patch"
    
    # Update CHANGELOG.md
    $newEntry = @"
## [$newVersion] - $currentDate

$Details

"@
    
    $changelogContent = $changelogContent -replace "# Changelog", "# Changelog`n`n$newEntry"
    Set-Content "CHANGELOG.md" $changelogContent
    
    # Update README.md if it contains version references
    if (Test-Path "README.md") {
        $readmeContent = Get-Content "README.md" -Raw
        if ($readmeContent -match "version|Version") {
            # Update version badges or references if they exist
            $readmeContent = $readmeContent -replace "v\d+\.\d+\.\d+", "v$newVersion"
            Set-Content "README.md" $readmeContent
        }
    }
    
    Write-Host "✅ Project documentation updated to version $newVersion"
    return $newVersion
}
```

## 💬 Commit Message Generation System

### PowerShell Script: Generate Commit Messages
```powershell
function Generate-CommitMessage {
    param(
        [string]$Type,           # "feat", "fix", "docs", etc.
        [string]$Description,    # Brief description
        [string]$IssueNumber,    # Optional issue number
        [string]$Action = "refs", # "refs", "fixes", "closes"
        [string]$Details         # Optional detailed description
    )
    
    $issueRef = if ($IssueNumber) { "[$Action #$IssueNumber] " } else { "" }
    $commitMessage = "$issueRef$Type`: $Description"
    
    if ($Details) {
        $commitMessage += "`n`n$Details"
    }
    
    Write-Host "📝 Suggested Commit Message:"
    Write-Host "================================"
    Write-Host $commitMessage
    Write-Host "================================"
    
    return $commitMessage
}
```

### Usage Examples:
```powershell
# For AI documentation changes
Generate-CommitMessage -Type "docs" -Description "add comprehensive AI testing framework and automated update system" -Details @"
- Created .ai/testing-framework.md with validation procedures
- Added .ai/auto-update-system.md with automated workflows  
- Implemented PowerShell scripts for version management
- Added commit message generation system
- Enhanced AI agent development workflow
"@

# For project feature changes
Generate-CommitMessage -Type "feat" -Description "enhance memory monitoring with real-time updates" -IssueNumber "15" -Action "closes" -Details @"
- Added live memory metrics integration
- Implemented trending indicators with historical tracking
- Enhanced UI with progress bars and visual feedback
- Improved error handling for missing metrics
"@

# For bug fixes
Generate-CommitMessage -Type "fix" -Description "resolve memory calculation errors in trending display" -IssueNumber "23" -Action "fixes" -Details @"
- Fixed byte-to-MB conversion bugs
- Corrected trending calculations to show actual differences
- Added proper handling for zero-difference states
- Eliminated race conditions in auto-refresh timers
"@
```

## 🤖 Comprehensive AI Agent Workflow

### Complete Update Process
```powershell
function Complete-AIWorkflow {
    param(
        [string]$WorkType,        # "ai-docs", "project-code"
        [string]$ChangeType,      # "major", "minor", "patch"
        [string]$CommitType,      # "feat", "fix", "docs", etc.
        [string]$Description,     # Brief description
        [string]$Details,         # Detailed changes
        [string]$IssueNumber,     # Optional issue number
        [string]$Action = "refs"  # "refs", "fixes", "closes"
    )
    
    Write-Host "🚀 Starting Complete AI Workflow..."
    
    # Step 1: Update appropriate documentation
    if ($WorkType -eq "ai-docs") {
        $newVersion = Update-AIDocumentation -ChangeType $ChangeType -Description $Description -Details $Details
        Write-Host "📚 AI Documentation updated to v$newVersion"
    } elseif ($WorkType -eq "project-code") {
        $newVersion = Update-ProjectDocumentation -ChangeType $ChangeType -Description $Description -Details $Details
        Write-Host "📦 Project documentation updated to v$newVersion"
    }
    
    # Step 2: Run validation tests
    Write-Host "🧪 Running validation tests..."
    & ".ai\testing-framework.md" # Reference to testing procedures
    
    # Step 3: Generate commit message
    Generate-CommitMessage -Type $CommitType -Description $Description -IssueNumber $IssueNumber -Action $Action -Details $Details
    
    Write-Host "✅ Complete AI Workflow finished successfully!"
}
```

## 📋 Quick Reference Commands

### For AI Agents to Use After Changes

#### AI Documentation Changes:
```powershell
Complete-AIWorkflow -WorkType "ai-docs" -ChangeType "minor" -CommitType "docs" -Description "add AI testing framework" -Details "Created comprehensive testing procedures and automated update workflows"
```

#### Project Code Changes:
```powershell
Complete-AIWorkflow -WorkType "project-code" -ChangeType "minor" -CommitType "feat" -Description "enhance monitoring dashboard" -IssueNumber "12" -Action "closes" -Details "Added real-time metrics and improved user interface"
```

#### Bug Fixes:
```powershell
Complete-AIWorkflow -WorkType "project-code" -ChangeType "patch" -CommitType "fix" -Description "resolve connection timeout issues" -IssueNumber "8" -Action "fixes" -Details "Improved error handling and retry mechanisms"
```

## 🔧 Integration with .ai/guidelines.md

This system integrates with the existing guidelines by:
- Following semantic versioning rules from `.ai/guidelines.md`
- Using commit message format from development standards
- Maintaining changelog format consistency
- Preserving branch naming conventions

## 📝 Manual Override Options

AI agents can still manually update documentation when:
- Complex changes require custom changelog entries
- Multiple related changes need consolidated versioning
- Special circumstances require deviation from automated flow

## ✅ Success Validation

After using this system, AI agents should verify:
- ✅ Version numbers are correctly incremented
- ✅ Changelog entries are properly formatted
- ✅ All documentation files are synchronized
- ✅ Commit message follows project standards
- ✅ No broken links or references introduced

---

*This automated system ensures consistent documentation maintenance and proper versioning across all AI agent contributions while providing clear commit message guidance.*
