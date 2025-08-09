# 🕷️ mcp-complex: advanced web scraping with deepseek and bright data

today i built something pretty cool - a chatbot that can actually browse the web intelligently using deepseek ai and bright data's mcp tools. turns out it works amazingly well!

## what i built

a python script that combines:

- **deepseek-chat** as the ai model (way cheaper than gpt-4)
- **bright data's mcp server** for advanced web scraping
- **langgraph** for tool orchestration
- **claude desktop integration** (also works there!)

## why bright data is different from normal scraping

regular web scraping sucks because:

- sites block you with captchas
- popups everywhere
- javascript-heavy sites don't load properly
- rate limiting kills your requests
- authentication is a nightmare

bright data's tools are special because they:

- **bypass all the annoying stuff** - no captchas, popups, or blocks
- **handle javascript** - can scrape spa sites and dynamic content
- **real browser automation** - acts like a human user
- **authentication support** - can log into sites (with pro mode)
- **global proxy network** - looks like requests from real users worldwide
- **handles complex interactions** - clicking, scrolling, form filling

## what worked today

tested with these queries and got amazing results:

### 1. linkedin profile search

asked it to search my linkedin profile - it found and extracted all the key info without getting blocked

### 2. local coffee shops in parkville (reddit)

searched reddit for coffee shop recommendations in parkville - parsed through multiple threads and gave me a nice summary

### 3. best saxophones on amazon

scraped amazon product listings, compared prices, read reviews, and gave me solid recommendations

## the magic sauce

the key is using bright data's **pro mode** which unlocks:

- browser automation tools
- authentication handling
- advanced web data extraction
- javascript execution capabilities

without pro mode you just get basic http scraping (boring!)

## setup that actually works

### for claude desktop users:

add this to your `claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "Bright Data": {
      "command": "npx",
      "args": ["@brightdata/mcp"],
      "env": {
        "API_TOKEN": "your-bright-data-token",
        "PRO_MODE": "true"
      }
    }
  }
}
```

### for python script users:

1. install globally: `npm install -g @brightdata/mcp`
2. set up your `.env`:

```
API_TOKEN=your-bright-data-token
DEEPSEEK_API_KEY=your-deepseek-key
BROWSER_ZONE=your-browser-zone
WEB_UNLOCKER_ZONE=your-web-unlocker-zone
```

3. run: `uv run main.py`

## why this combo rocks

- **deepseek** is crazy cheap and smart enough for tool use
- **bright data** handles all the hard web scraping stuff
- **mcp** makes everything plug together nicely
- **works in both claude desktop and custom scripts**

## lessons learned

1. **always use pro mode** - without it you don't get the good tools
2. **install mcp packages globally** - prevents timeout issues
3. **disable other mcp servers** while testing - they conflict
4. **deepseek needs explicit api key** - even with custom base_url
5. **message history matters** - add assistant responses back to context

## next steps

could add:

- screenshot capabilities for visual content
- multi-step authentication flows
- scheduled scraping tasks
- data export to different formats
- more sophisticated error handling

but honestly, this already works way better than expected! the combination of a good ai model with proper web automation tools is pretty powerful.

---

_built in one afternoon because regular web scraping is pain and this actually works_ ✨

## 🔥 why this combo rocks

- **deepseek** 💰 is crazy cheap and smart enough for tool use
- **bright data** 🛡️ handles all the hard web scraping stuff
- **mcp** 🔌 makes everything plug together nicely
- **works in both claude desktop and custom scripts** 📱💻

## 📚 lessons learned

1. **always use pro mode** 🔥 - without it you don't get the good tools
2. **install mcp packages globally** 🌍 - prevents timeout issues
3. **disable other mcp servers** ⏸️ while testing - they conflict
4. **deepseek needs explicit api key** 🔑 - even with custom base_url
5. **message history matters** 💭 - add assistant responses back to context

## 🚀 next steps

could add:

- screenshot capabilities for visual content 📸
- multi-step authentication flows 🔐
- scheduled scraping tasks ⏰
- data export to different formats 📊
- more sophisticated error handling ⚠️

but honestly, this already works way better than expected! the combination of a good ai model with proper web automation tools is pretty powerful. 💪

---

_built in one afternoon because regular web scraping is pain and this actually works_ 🎉
