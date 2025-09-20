# Lab outline

## Exercise 1: Set up user account against SAP and all that is involved in that. (10 minutes)

1. Export OpenAI JSON file.

## Exercise 2: Configure SAP API in Azure API Management (30 minutes)

1. Create API
   1. Import OpenAPI specification file (JSON)
   2. Configure API
      1. Set display name, name, web service URL, API URL suffix.
      2. Uncheck Subscription required (for simplicity). Or perhaps it would be better to show them how to configure things when this is checked, since it is by default?
         1. Use subscription key
         2. Have user create a new subscription or use built-in sub.
         3. Pass subscription key and proper header.
      3. Perhaps reduce allowable operations to not have so many possible endpoints? Should retain some GET, POST, and DELETE endpoints.
   3. Configure Named values
      1. Add username (plain)
      2. Add password (secret)
   4. Set inbound policy to pass in username and password using named value tokens.
   5. Test API in APIM UI.
      1. Make sure to use top 5 in test queries, as the UI seems to fail with a large amount of data.

## Exercise 3: Create MCP Server from API in APIM (10 minutes)

1. In APIM, select the MCP Server (Preview) item from the left-hand menu.
2. Create a new server by selecting Expose an API as an MCP server
3. Select the API created above and select the operations to expose.
4. Enter a display name, name, and optional description.
5. Select just a two or three GET endpoints to use as tools.
6. Select Create.

## Exercise 4: Manage Access to your MCP server (15 minutes)

1. In APIM, create a product and subscription to lock down access to the MCP server API.

## Exercise 5: Test and use the MCP server (10 - 20 minutes)

1. Use MCP Inspector (Leave out if using Copilot Studio)
   1. Install NPX
   2. Configure connection to APIM MCP server
   3. Make sure to do Top 5 in queries.
2. Use VS Code and GitHub Copilot
   1. Connect to MCP server from VS Code
   2. Use VS Code and GitHub copilot (in agent mode) to issue natural language queries against the MCP server and SAP data.

## Exercise 6: Create an agent (Copilot Studio or via code with Semantic Kernel) (30 minutes)

1. Create agent
2. Use MCP server with agent
3. Interact with the agent (autonomous?)