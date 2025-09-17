# Coding Guidelines for AI Assistance - Detailed coding standards for JavaScript, HTML, and CSS

## JavaScript Guidelines

### Code Style
- Use ES6+ features but ensure broad browser compatibility
- Prefer const over let, avoid var
- Use meaningful variable and function names
- Implement error handling for all network requests
- Use async/await for asynchronous operations

### Performance
- Minimize DOM operations
- Use requestAnimationFrame for animations
- Implement debouncing for frequent operations
- Cache DOM selections
- Use efficient selectors

### Security
- Sanitize all user inputs
- Use secure defaults for CORS settings
- Implement proper error handling
- Avoid eval() and similar unsafe functions
- Use Content Security Policy headers

## HTML Guidelines

### Structure
- Use semantic HTML5 elements
- Maintain proper heading hierarchy
- Include ARIA attributes where needed
- Keep the structure logical and clear

### Accessibility
- Ensure proper contrast ratios
- Include alt text for images
- Use ARIA labels appropriately
- Ensure keyboard navigation works
- Support screen readers

## CSS Guidelines

### Architecture
- Follow BEM methodology
- Use CSS variables for theming
- Maintain mobile-first approach
- Keep specificity low
- Use logical property groups

### Performance
- Avoid deeply nested selectors
- Minimize use of !important
- Use efficient selectors
- Consider paint performance
- Optimize animations

## Documentation Guidelines

### Code Comments
- Document complex logic
- Explain "why" not just "what"
- Use JSDoc for functions
- Keep comments current
- Include examples for complex operations

### README Updates
- Keep installation steps clear
- Document all configuration options
- Include troubleshooting guides
- Update screenshots when needed
- Maintain clear examples
