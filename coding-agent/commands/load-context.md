---
description: "Reads brief.md file to build comprehensive context for current session"
---

### Load Context Workflow

1. **Locate brief.md File**: Search for the context file in the project:
   - Check project root directory first
   - Look in common documentation folders (docs/, .windsurf/, etc.)
   - If not found, ask user for file location or suggest creating one

2. **Read and Parse Content**: Load the brief.md file and analyze its structure:
   - Identify main sections (Project Overview, Decisions, Patterns, etc.)
   - Extract key information from each section
   - Note any code examples or technical specifications
   - Identify current project status and next steps

3. **Build Session Context**: Process the information to establish working context:
   - Understand project goals and constraints
   - Learn user preferences and coding style
   - Review previous architectural decisions
   - Identify current technology stack and dependencies

4. **Create Memory Entries**: Store important context in Windsurf memory system:
   - Project-specific technical decisions
   - User coding preferences and patterns
   - Current project status and priorities
   - Key architectural choices and rationale

5. **Confirm Context Loading**: Validate that context has been properly loaded:
   - Summarize key project information for user confirmation
   - Ask if any additional context is needed
   - Offer to update or expand the brief.md file if information seems outdated
   - Ready to proceed with informed assistance based on loaded context
