---
name: github-mcp-test
version: 1.0.0
description: Test the GitHub MCP connection. Use when the user asks to test, check or verify Github MCP connection.
license: MIT
---

# Github MCP test

Verify that the Github MCP server is connected and authenticated. Read-only: never create, edit or delete any files on github.

## Steps

1. Find the Github MCP tools (mcp_github) with ToolSearch
2. If only 'authenticate' / 'complete_authentication' tools exist, teh server is not logged in yet. Tell the user to run /mcp, pick the Github server and authenticate, then stop.
3. Otherwise, run one read-only call, such as fetching the authenticated user's profile or listing their repositories (limit 5).
4. report in a short table:
      - Server connected : yes/no
      - Autheticated as: <login>
      - Sample result: up to 5 repo names
      - Any error message, verbatim
    5. end with one line: PASS if step 3 worked, Fail otherwise, plus the likely cause.