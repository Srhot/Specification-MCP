# Specification MCP
[![smithery badge](https://smithery.ai/badge/@Srhot/specification-mcp)](https://smithery.ai/server/@Srhot/specification-mcp)

A structured documentation system for project knowledge management via Model Context Protocol (MCP).

## Overview

Specification MCP is an MCP server that helps teams create, manage, and access structured project documentation. It generates and maintains a set of interconnected Markdown documents that capture various aspects of project knowledge — from high-level goals to technical implementation and daily progress.

## Features

- **AI-Generated Documentation**: Uses Gemini API to auto-generate comprehensive documentation.
- **Structured Knowledge System**: Maintains six core document types in a hierarchical structure.
- **MCP Integration**: Implements Model Context Protocol for seamless AI assistant integration.
- **Customizable Directory**: Allows users to choose the location for generated files.
- **Document Templates**: Includes ready-to-use templates (project brief, product context, etc.).
- **AI-Assisted Updates**: Manually update or regenerate documents with AI help.
- **Smart Search**: Context-aware search across all documents.

## Installation

### Installing via Smithery

To install specification-mcp for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@Srhot/specification-mcp):

```bash
npx -y @smithery/cli install @Srhot/specification-mcp --client claude
```

### Manual Installation
```bash
# Clone the repository
git clone https://github.com/Srhot/Specification-MCP.git
cd Specification-MCP

# Install dependencies
npm install

# Create .env file with your Gemini API key (optional)
echo "GEMINI_API_KEY=your_api_key_here" > .env
```

## Usage

### Development

```bash
npm run dev
```

### Production

```bash
npm run build
npm run start
```

## MCP Integration

To integrate Specification MCP with the Model Context Protocol (MCP), add this to your `mcp.json` file:

```json
{
  "memoryBank": {
    "command": "node",
    "args": ["/path/to/Specification-MCP/dist/index.js"],
    "env": {
      "GEMINI_API_KEY": "your_gemini_api_key_here"
    }
  }
}
```

> Replace `/path/to/Specification-MCP/dist/index.js` with the full path to your built file.

## MCP Tools

### `initialize_memory_bank`

Creates a new Memory Bank structure.

**Parameters:**

- `goal` (string): Project goal (min 10 characters)
- `geminiApiKey` (optional): Your API key
- `location` (optional): Path to create the memory bank

### `update_document`

Updates a specific document.

**Parameters:**

- `documentType`: One of: `projectbrief`, `productContext`, `systemPatterns`, `techContext`, `activeContext`, `progress`
- `content` (optional): New content
- `regenerate` (boolean): Use AI to regenerate?

### `query_memory_bank`

Context-aware search across documents.

**Parameters:**

- `query` (string): Your search query (min 5 characters)

### `export_memory_bank`

Exports documents to JSON or folder.

**Parameters:**

- `format`: `"json"` or `"folder"`
- `outputPath` (optional): Export path

## Document Types

- `projectbrief.md`: Project scope, goals
- `productContext.md`: User-focused features
- `systemPatterns.md`: Architecture & components
- `techContext.md`: Technology stack
- `activeContext.md`: Current work, open tasks
- `progress.md`: History, milestones

## License

MIT
