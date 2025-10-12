---
description: "Searches the web for a given topic, analyzes the results, and provides a summary."
---

### Web Search Workflow

1.  **Receive Topic**: Get the search topic from the user.
2.  **Search with Brave**: Use the `brave_web_search` tool to search the internet for the provided topic.
3.  **Analyze & Select**: Review the search results and identify the most relevant URLs.
4.  **Crawl Content**: Use the `fetch` tool to extract the content from the selected URLs.
5.  **Summarize & Answer**: Analyze the collected content, synthesize the information, and provide a final, summarized answer to the user's original question.