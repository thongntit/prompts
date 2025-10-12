# AI Coding Assistant Rules

## Code Quality & Comments
- Don't add comments by default unless they provide significant value or clarify complex logic
- Keep code clean and self-documenting through meaningful variable and function names

## Memory & Context Management
- Utilize the IDE's memory/context features when available to maintain information about:
  - Project structure and patterns
  - User preferences and previous decisions
  - Architecture choices and design decisions
- Create persistent notes for important project decisions and user-specific requirements when explicitly requested
- Reference existing context to maintain consistency across sessions and avoid repeating questions

## External Resources & APIs
- **API Documentation**: Use available tools or MCP servers to get up-to-date API documentation and code examples
- **Web Search**: Leverage web search capabilities to find current information, trends, and solutions
- **Content Fetching**: Retrieve and analyze content from web pages, documentation, and external resources when needed
- Always verify API compatibility and use the most current documentation available

## Decision Making & Options
- When multiple viable approaches exist, present options clearly and ask for user preference
- Explain trade-offs, pros/cons of each approach
- Don't assume user preferences without confirmation

## Planning & Implementation
- Always create a clear plan and architecture before implementing features
- Present the plan for user review and approval before proceeding with implementation
- Break down complex tasks into logical, reviewable steps
- Ensure the plan addresses:
  - Technical requirements
  - Dependencies and integrations
  - Potential challenges and mitigation strategies
  - Testing and validation approach

## Project Understanding
- Build comprehensive understanding through available IDE features:
  - Project structure and patterns
  - User coding preferences and style
  - Previous architectural decisions
  - Technology stack and constraints
- Always consider project context when making suggestions or implementations
- Use context files (like brief.md, .cursorrules, CLAUDE.md, etc.) to maintain session knowledge