# MCP Practice IK

A Model Context Protocol (MCP) server designed for demonstration and practice. This server implements basic MCP capabilities including tools, resources, and prompts using the `mcp` python library.

## Features Implemented

The following steps describe the current state of the project:

1.  **Server Initialization**: initialized a `FastMCP` server instance named "DemoServerIK".
2.  **Tool Implementation**: Added an `add` tool that takes two integers and returns their sum.
    - Usage: Call tool `add` with arguments `a` and `b`.
3.  **Resource Implementation**: Created a dynamic resource `greeting://{name}`.
    - Usage: Read resource `greeting://<name>` to get a personalized greeting string.
4.  **Prompt Implementation**: Defined a `greet_user` prompt.
    - Usage: specific prompt `greet_user` to generate a welcome message.

## Setup

1.  Clone the repository.
2.  Create a virtual environment:
    ```bash
    python -m venv venv
    ```
3.  Activate the virtual environment:
    - Windows: `.\venv\Scripts\activate`
    - Unix/MacOS: `source venv/bin/activate`
4.  Install dependencies:
    ```bash
    pip install mcp
    pip install uv
    ```

## Usage

You can run this server using an MCP client.

### Using with `mcp` CLI or `uvx`

If you have `uv` installed:

```bash
uvx mcp install server.py
```

Or using the installed package:

```bash
# Ensure you are in the virtual environment
mcp install server.py
```
### output: 
```bash
(venv) PS C:\Users\Himanshu Shrivastava\Desktop\ik\git\mcp_practice_ik> mcp install server.py
[02/15/26 15:49:57] INFO     Added server 'DemoServerIK' to Claude config claude
[02/15/26 15:49:57] INFO     Successfully installed DemoServerIK in Claude app 
```
### Note: It automatically adds the server to the Claude app.
### Else do it manually as per below steps:
### Configuration for Claude Desktop

Add the following to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "mcp-practice-ik": {
      "command": "uvx",
      "args": [
        "mcp",
        "install",
        "path/to/server.py"
      ]
    }
  }
}
```
*Note: Adjust `path/to/server.py` to the absolute path of the file on your system.*
