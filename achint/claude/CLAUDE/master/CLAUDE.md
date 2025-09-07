## Working with Claude
<!-- This is a good set of instructions to be placed at the master (user) level -->

### Development Philosophy

- **Simplicity**: Write simple, straightforward code
- **Readability**: Make code easy to understand
- **Performance**: Consider performance without sacrificing readability
- **Maintainability**: Write code that's easy to update
- **Testability**: Ensure code is testable
- **Reusability**: Create imodular, reusable code and functions
- **Less Code = Less Debt**: Minimize code footprint
- **Documentation**: Document important decisions and complex logic


### Coding Best Practices

- **Early Returns**: Use to avoid nested conditions
- **Descriptive Names**: Use clear variable/function names (prefix handlers with "handle")
- **Constants Over Functions**: Use constants where possible
- **DRY Code**: Don't repeat yourself
- **Functional Style**: Prefer functional, immutable approaches when not verbose
- **Minimal Changes**: Only modify code related to the task at hand
- **Function Ordering**: Define composing functions before their components
- **TODO Comments**: Mark issues in existing code with "TODO:" prefix
- **Simplicity**: Prioritize simplicity and readability over clever solutions
- **Build Iteratively** Start with minimal functionality and verify it works before adding complexity
- **Functional Code**: Use functional and stateless approaches where they improve clarity
- **Clean logic**: Keep core logic clean and push implementation details to the edges
- **File Organsiation**: Balance file organization with simplicity - use an appropriate number of files for the project scale
- **Code Leaks**: Use server-side logic for sensitive operations
- **Error Handling**: Implement comprehensive error handling
- **Performance vs. Security**: Prioritize performance and security equally when needed


### Tools Available

The following tools are available if you need them:

- If you need to access documentation about APIs or libraries, use the context7 MCP
- If you need to see the UI for bug-fixing use the playwright MCP


### Security Best Practices

#### Secrets Management
- **Never commit secrets**: Keep API keys, passwords, and tokens out of version control
- **Environment variables**: Store all secrets in environment variables (`.env` for local development)
- **Separate environments**: Use different secrets for development, staging, and production
- **Minimal exposure**: Only expose secrets to the processes that need them

#### Client-Side Security
- **No secrets in frontend**: Never expose API keys, database credentials, or sensitive tokens in client-side code
- **Validate on server**: Always validate and sanitize data on the server, never trust client input
- **Secure headers**: Implement proper security headers (CSP, HSTS, X-Frame-Options)
- **HTTPS everywhere**: Use HTTPS for all communications, especially in production
- **Input sanitization**: Sanitize all user inputs to prevent XSS and injection attacks

#### API Security
- **Authentication**: Implement proper authentication (OAuth, JWT, API keys)
- **Authorization**: Verify permissions for every protected resource
- **Rate limiting**: Implement rate limiting to prevent abuse
- **CORS properly**: Configure CORS restrictively, don't use wildcards in production
- **Error messages**: Don't leak sensitive information in error responses
- **Logging**: Log security events but never log sensitive data

#### Data Protection
- **Encrypt sensitive data**: Encrypt sensitive data at rest and in transit
- **Hash passwords**: Use strong hashing algorithms (bcrypt, Argon2) for passwords
- **Principle of least privilege**: Grant minimal necessary permissions
- **Data validation**: Validate all data inputs and outputs

#### Dependencies & Code
- **Keep dependencies updated**: Regularly update packages to patch security vulnerabilities
- **Code reviews**: Review all code changes for security implications
- **Static analysis**: Use security linters and static analysis tools
- **Sensitive data in logs**: Never log passwords, tokens, or personal information


### Expectations

When working with my code:

- **Think deeply** before making any edits
- **Understand the full context** of the code and requirements
- **Ask clarifying questions** when requirements are ambiguous
- **Think from first principles** - don't make assumptions
- **Keep project docs current** - update them whenever you introduce meaningful changes
- **At the end of every change, update CLAUDE.md with anything useful you wished you'd known at the start**.
   This is CRITICAL - Claude should capture learnings, gotchas, patterns discovered, or any context that would have made the task easier if known upfront. This continuous documentation ensures future work benefits from accumulated knowledge


### Code Changes

When suggesting or making changes:

- Respect the existing patterns and conventions
- Keep changes small and incremental
- Provide rationale for significant design decisions
