# OSRS玩家数据服务 OSRS STAT

一个提供实时《Old School RuneScape》玩家统计数据和排行榜数据的Model Context Protocol (MCP)服务器，支持多种游戏模式和玩家比较功能。
A Model Context Protocol (MCP) server that provides real-time player statistics and ranking data of 'Old School RuneScape', supporting multiple game modes and player comparison functions.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| get_player_stats | Retrieve comprehensive statistics for a specific OSRS player including skills, activities, and boss kill counts |
| get_skill_leaderboard | Get top players for a specific skill |
| get_activity_leaderboard | Get top players for activities (bosses, minigames, clues) |
| compare_players | Compare statistics between multiple OSRS players |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659429379](https://mcp.xiaobenyang.com/inspector/1777316659429379)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659429379](https://mcp.xiaobenyang.com/inspector/1777316659429379)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "OSRS玩家数据服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659429379/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "OSRS玩家数据服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659429379/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "OSRS玩家数据服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659429379",
          },
          "transport": "stdio"
        }
      }
}

```
