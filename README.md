# ML File Manager Pro

**Version:** 1.6.18  
**Author:** 1WD LLC  
**Website:** [WPLaunchify.com](https://wplaunchify.com)  
**License:** GPL v2 or later  

## 🚀 Production-Ready WordPress MCP File Manager

ML File Manager Pro is a comprehensive WordPress plugin that provides complete filesystem access through the Model Context Protocol (MCP). It serves as a complete SFTP replacement, enabling AI agents like Claude (Cursor) to perform full file management operations on your WordPress server.

## ✨ Key Features

### 🔧 Complete File System Operations
- **File Management:** Read, write, delete, copy, move files
- **Directory Operations:** Create, list, navigate directories  
- **Archive Support:** Create and extract ZIP files
- **Permission Control:** Change file permissions (chmod)
- **Pattern Matching:** Find files using glob patterns
- **Path Security:** Robust security with allowed root validation

### 🤖 AI Agent Integration
- **MCP Protocol:** Full JSON-RPC 2.0 compliance
- **Cursor IDE:** Perfect integration with Cursor's MCP system
- **Claude Support:** Works with Claude and other MCP-compatible AI tools
- **Tool Discovery:** Automatic tool registration and schema validation

### 🔐 Enterprise Security
- **API Key Management:** Generate, revoke, and manage API keys
- **Path Validation:** Prevents directory traversal attacks
- **Allowed Roots:** Configurable filesystem access boundaries
- **WordPress Integration:** Native WordPress authentication support

## 📦 Installation

1. Upload the `plugin-files/ml-file-manager.php` file to your `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Navigate to **ML File Manager** in your WordPress admin menu
4. Generate an API key in the **API Settings** section

## 🔧 Configuration

### For Cursor IDE (Recommended)

1. Open Cursor → **Settings → MCP Servers → Edit JSON**
2. Add the following configuration:

```json
{
  "mcpServers": {
    "ml-file-manager": {
      "command": "npx",
      "args": [
        "-y",
        "-p",
        "mcp-remote@0.1.29",
        "-p", 
        "undici@7",
        "mcp-remote",
        "https://yoursite.com/wp-json/ml-file-manager/v1/mcp-http?X-API-Key=YOUR_API_KEY",
        "--transport",
        "http-only"
      ]
    }
  }
}
```

3. Replace `https://yoursite.com` with your WordPress site URL
4. Replace `YOUR_API_KEY` with the API key generated in WordPress admin
5. Save and click **Reconnect** (or restart Cursor)

## 🛠️ Available MCP Tools

### Core Operations
- `mcp_ml-file-manager_get_status` - Get system status and plugin info
- `mcp_ml-file-manager_list_files` - List files and directories
- `mcp_ml-file-manager_fs_stat` - Get file/directory information

### File Content Operations  
- `mcp_ml-file-manager_fs_read` - Read file contents (text or base64)
- `mcp_ml-file-manager_fs_write` - Write content to files
- `mcp_ml-file-manager_fs_delete` - Delete files or directories

### Advanced Operations
- `mcp_ml-file-manager_fs_copy` - Copy files or directories
- `mcp_ml-file-manager_fs_move` - Move/rename files or directories  
- `mcp_ml-file-manager_fs_chmod` - Change file permissions
- `mcp_ml-file-manager_fs_zip` - Create ZIP archives
- `mcp_ml-file-manager_fs_unzip` - Extract ZIP archives
- `mcp_ml-file-manager_fs_glob` - Find files matching patterns

## 🔄 Version History

### v1.6.18 (Current - Production Ready)
- ✅ **100% Functionality:** All 12 MCP tools working perfectly
- ✅ **Production Ready:** Comprehensive testing and validation
- ✅ **Security Hardened:** Robust path validation and security controls
- ✅ **Performance Optimized:** Efficient file operations and memory usage

### Previous Versions
- v1.6.0-1.6.17: Iterative development and debugging
- v1.4.1: Initial working foundation
- Full version history available in `old-versions/` directory

## 🤝 Support

For support and documentation:
- **Website:** [WPLaunchify.com](https://wplaunchify.com)
- **Documentation:** Available in WordPress admin panel
- **Issues:** Report via GitHub or support channels

---

**Developed by 1WD LLC** | **[WPLaunchify.com](https://wplaunchify.com)**

*Empowering WordPress with AI-driven file management capabilities.*