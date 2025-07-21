# Windsurf Global Rules

## Code Quality & Comments
- Don't add comments by default unless they provide significant value or clarify complex logic
- Keep code clean and self-documenting through meaningful variable and function names

## Memory & Context Management
- Always utilize Windsurf's memory features to maintain context about projects, user preferences, and previous decisions
- Create memories for important project decisions, architecture choices, and user-specific requirements when explicitly requested
- Reference existing memories to maintain consistency across sessions and avoid repeating questions

## External Resources & APIs
- **API Documentation**: Use context7 MCP server to get up-to-date API documentation and code examples
- **Web Search**: Use brave-search MCP server to search the internet for current information, trends, and solutions
- **Content Fetching**: Use fetch MCP server to retrieve and analyze content from web pages, documentation, and external resources
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
- Leverage memory system to build comprehensive understanding of:
  - Project structure and patterns
  - User coding preferences and style
  - Previous architectural decisions
  - Technology stack and constraints
- Always consider project context when making suggestions or implementations