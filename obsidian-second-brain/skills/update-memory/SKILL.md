---
name: update-memory
description: Manually refresh the memory bank files that describe the vault's structure and note connections. Use after significant vault changes (new projects, area restructuring, major note moves).
allowed-tools: Glob, Read, Write, Edit, Bash
---

# Update Memory Bank

Refresh the memory-bank files that help the AI understand the vault's structure and how notes connect.

## Memory bank location

By convention, memory-bank files live at `99_metadata/memory-bank/`:

- `vaultStructure.md` — overall organization (PARA folders, project list, area list, resource categories, archive contents)
- `noteConnections.md` — connection patterns (frontmatter fields used to link notes, primary hubs, topic clusters, link constraints)

If the user keeps these files elsewhere, ask before writing.

## Steps

1. **Analyze vault structure** following PARA (Projects, Areas, Resources, Archives)
2. **Identify connection patterns** — scan frontmatter fields, wikilinks, common hubs
3. **Update `99_metadata/memory-bank/vaultStructure.md`:**
   - Document the overall vault organization
   - Map all projects and their current `project-status`
   - Detail areas of responsibility
   - Catalog resource categories
   - Describe archive organization
4. **Update `99_metadata/memory-bank/noteConnections.md`:**
   - Document all connection types found in frontmatter (e.g., `AREA`, `PROJECT`, `Last-Contacted`, `ConnectionType`)
   - Map primary connection hubs (notes with the most inbound links)
   - Detail topic clusters and domains
   - Describe any connection constraints or rules
5. **Add timestamped entries** to document the update in both files
6. **Match existing formatting** — preserve heading structure, nesting style, and bullet conventions
7. **Base everything on observed patterns** — never assume, always derive from actual files
