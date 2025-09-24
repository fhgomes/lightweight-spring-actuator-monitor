# AI Interaction Examples - Practical examples of common AI interactions

**Version**: 1.0  
**Last Updated**: 2025-01-16  
**Maintainer**: AI Documentation System

This document provides practical examples of how to interact with AI when working on this project.

## Adding a New Metric

**Example Prompt:**
```
I want to add support for monitoring thread deadlock detection. Please help me:
1. Add a new metric card for deadlock information
2. Implement the API call to /actuator/metrics/jvm.threads.deadlocked
3. Display the count with appropriate warning styling
4. Include educational content about deadlock detection
```

**Expected Approach:**
- AI should maintain the single-file architecture
- Follow existing CSS classes and styling patterns
- Add educational tooltips explaining what thread deadlocks are
- Include error handling for when the metric isn't available
- Update documentation to reflect the new feature

**Example Commit for New Metric:**
```
[refs #25] feat: add thread deadlock detection support

Adds new metric card for monitoring thread deadlocks, including:
- API integration with /actuator/metrics/jvm.threads.deadlocked
- Warning styling for detected deadlocks
- Educational tooltips about thread deadlock detection
```

## Improving Performance

**Example Prompt:**
```
The dashboard feels slow when refreshing metrics every 2 seconds with many metrics displayed. 
Please optimize the performance while maintaining real-time updates.
```

**Expected Guidelines:**
- Analyze current DOM update patterns
- Implement efficient batching of updates
- Use requestAnimationFrame for smooth animations
- Cache DOM selections to avoid repeated queries
- Consider debouncing for user interactions
- Maintain the target refresh efficiency of < 100ms per update

**Example Commit:**
```
[refs #31] perf: optimize metric refresh performance

- Implements DOM update batching
- Adds requestAnimationFrame for smooth updates
- Caches DOM selections
- Adds debouncing for frequent updates
```

## Security Enhancement

**Example Prompt:**
```
I need to make this dashboard more secure for production use. What security improvements should I implement?
```

**Expected Security Focus:**
- Review and enhance CORS configuration guidance
- Implement input sanitization for user-entered URLs
- Add Content Security Policy recommendations
- Suggest secure defaults for all configurations
- Provide production deployment security checklist
- Address potential XSS vulnerabilities

**Example Commit:**
```
[refs #42] security: enhance production security measures

- Implements strict CSP headers
- Adds URL sanitization
- Updates CORS configuration guidance
- Includes security checklist for production
```

## UX/UI Enhancement

**Example Prompt:**
```
Users find it hard to understand when their application is having memory issues. 
How can I improve the visual indicators and educational content?
```

**Expected UX Approach:**
- Enhance color coding for different severity levels
- Add progressive disclosure for detailed explanations
- Implement better visual hierarchy for critical metrics
- Include contextual help and tooltips
- Maintain accessibility standards (WCAG compliance)
- Provide clear actionable recommendations

**Example Commit:**
```
[refs #38] feat: improve memory issue indicators

- Enhances color coding for severity levels
- Adds progressive disclosure for explanations
- Implements tooltips for quick understanding
- Updates visual hierarchy for critical metrics
```

## Documentation Update

**Example Prompt:**
```
I've added support for custom Actuator endpoints. Please help me update the documentation 
to reflect this new capability.
```

**Expected Documentation Standards:**
- Update README.md with new feature description
- Add configuration examples for custom endpoints
- Include troubleshooting section for common issues
- Update screenshots if UI changes are involved
- Maintain clear, action-oriented language
- Include security considerations for custom endpoints

**Example Commit:**
```
[refs #45] docs: add custom endpoint configuration guide

- Documents custom endpoint setup
- Adds configuration examples
- Updates security considerations
- Includes troubleshooting section
```

## Bug Fix Assistance

**Example Prompt:**
```
The memory usage chart sometimes shows NaN values. This happens when the application 
starts up and metrics aren't available yet. How should I fix this?
```

**Expected Bug Fix Approach:**
- Identify root cause (metrics not available during startup)
- Implement graceful degradation (show loading state)
- Add proper error handling for missing/invalid data
- Consider showing helpful messages during loading
- Ensure fix doesn't break existing functionality
- Add defensive programming patterns

**Example Fix Commit:**
```
[fixes #52] fix: handle NaN values in memory chart

- Adds graceful degradation for missing metrics
- Implements loading states
- Improves error handling
- Updates user feedback during startup
```

## Code Review Request

**Example Prompt:**
```
Please review this JavaScript function I wrote for calculating memory percentage. 
Check for performance issues, browser compatibility, and code style compliance.
```

**Expected Review Focus:**
- Verify ES6+ compatibility with target browsers
- Check mathematical accuracy and edge cases
- Ensure proper error handling
- Validate against project coding standards
- Suggest performance optimizations if needed
- Verify accessibility implications

## Testing Strategy

**Example Prompt:**
```
What testing approach should I use to ensure the dashboard works reliably 
across different Spring Boot applications and browsers?
```

**Expected Testing Guidance:**
- Browser compatibility testing strategy
- Manual testing checklist for different scenarios
- Performance testing recommendations
- Accessibility testing approaches
- Security testing considerations
- Integration testing with various Spring Boot versions
