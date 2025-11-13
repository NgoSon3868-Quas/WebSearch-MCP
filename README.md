# Cấu hình MCP Server Web Search (Brave)

Repository này chứa cấu hình MCP Server Web Search sử dụng Brave Search API để sử dụng trên nhiều máy tính.

## Cấu hình

File `mcp.json` chứa cấu hình để thêm vào `.cursor/mcp.json` hoặc `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "web-search": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-brave-search"
      ],
      "env": {
        "BRAVE_API_KEY": "your-brave-api-key-here"
      }
    }
  }
}
```

## Lưu ý quan trọng

⚠️ **Cần Brave API Key**: Bạn cần lấy Brave API Key từ https://brave.com/search/api/ và thay thế `"invalid-placeholder"` trong file cấu hình.

## Lấy Brave API Key

1. Truy cập: https://brave.com/search/api/
2. Đăng ký tài khoản (nếu chưa có)
3. Tạo API key mới
4. Copy API key và thay thế trong file `mcp.json`

## Sử dụng

1. Clone repository này:
   ```bash
   git clone https://github.com/NgoSon3868-Quas/WebSearch-MCP.git
   cd WebSearch-MCP
   ```

2. Chỉnh sửa file `mcp.json` và thay thế `"invalid-placeholder"` bằng Brave API Key của bạn

3. Copy nội dung từ `mcp.json` vào file cấu hình MCP của bạn:
   - Windows: `C:\Users\<username>\.cursor\mcp.json`
   - Mac/Linux: `~/.cursor/mcp.json`
   
   Hoặc merge vào file `mcpServers` hiện có của bạn.

4. Khởi động lại Cursor IDE

## Yêu cầu

- Node.js và npm đã được cài đặt
- Package `@modelcontextprotocol/server-brave-search` sẽ được tự động tải khi sử dụng
- Brave API Key hợp lệ

## Tính năng

MCP Server Web Search cung cấp các công cụ để:
- Tìm kiếm trên web
- Tìm kiếm địa phương (local search)
- Lấy kết quả tìm kiếm từ Brave Search

## Kiểm tra cấu hình

Sau khi thêm cấu hình và khởi động lại Cursor:
1. Vào Settings > Tools & MCP
2. Kiểm tra trong danh sách "Installed MCP Servers" có `web-search` với trạng thái "Ready"

## Bảo mật

⚠️ Không commit API key vào public repository. Luôn sử dụng placeholder và cập nhật trên máy local.
