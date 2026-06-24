# Timeline Pro

> An interactive timeline graph extension for [SillyTavern](https://github.com/SillyTavern/SillyTavern) — visualize your chat history as a branching, navigable node graph.
>
> 为 SillyTavern 打造的交互式时间线图扩展——将聊天历史可视化为可导航的分支节点图。

---

## ✨ Features / 功能

- **📊 Visual Timeline Graph** — Renders your entire chat history as an interactive directed acyclic graph (DAG) using [Cytoscape.js](https://js.cytoscape.org/). Each message is a node, connected by edges showing the conversation flow.
  **可视化时间线图** — 使用 Cytoscape.js 将完整聊天历史渲染为交互式有向无环图。每条消息是一个节点，边展示对话流向。

- **🔀 Multi-Session / Branching** — Seamlessly handles branching conversations. Messages with identical content across different branches are merged into a single node.
  **多会话 / 分支支持** — 无缝处理分支对话。不同分支中内容相同的消息自动合并为单一节点。

- **🖱️ Rich Node Interactions**
  - **Click / Tap** — Opens a detailed tooltip showing the sender, timestamp, message content, swipe count, and a list of all chat sessions containing this message. Navigate to any session or create a new branch.
  - **Double-click** — Quick-jump to the first chat session containing this message.
  - **Hover** — Preview truncated message after a short delay.
  - **Context menu** — Right-click any node to open a specific chat session.
  - **Long-press (taphold)** — Toggle visibility of swipe (alternate response) nodes.
  **丰富的节点交互**
  - **单击** — 打开详细工具提示，显示发送者、时间戳、消息内容、滑动轮次及所有包含该消息的聊天会话列表。可跳转到任意会话或创建新分支。
  - **双击** — 快速跳转到包含该消息的第一个聊天会话。
  - **悬停** — 短暂延迟后预览截断的消息内容。
  - **右键菜单** — 右键点击节点可打开指定聊天会话。
  - **长按** — 切换显示滑动（替代回复）节点。

- **🔍 Search** — Real-time node search by message content. Matching nodes are highlighted; non-matching nodes dim.
  **消息搜索** — 按消息内容实时搜索节点。匹配节点高亮，不匹配节点自动淡化。

- **🔄 Graph Orientation** — Toggle between Top-to-Bottom (TB) and Left-to-Right (LR) layout. Auto-adjusts based on viewport on first render.
  **图谱方向切换** — 在自上而下和从左到右布局间切换。首次渲染时根据视口自动调整。

- **🔖 Bookmark Path Highlighting** — Bookmarked messages and their path to the root node are highlighted in the bookmark's color, with thicker edges and higher z-index.
  **书签路径高亮** — 书签消息及其到根节点的路径以书签颜色高亮，边线加粗，层级提升。

- **🥇 Gold Path** — On opening, the current conversation's path is automatically highlighted for easy tracking of where you are.
  **金色路径** — 打开时间线时自动高亮当前会话路径，方便定位。

- **📖 Interactive Legend** — Shows unique character names and edge bookmark colors. Hover for preview, click to lock filtering.
  **交互式图例** — 显示所有角色名称和边线书签颜色。悬停预览，点击锁定筛选。

- **🎨 Full Visual Customization**
  - **Node shape:** ellipse, triangle, rectangle, diamond, star, pentagon, hexagon, octagon, and 17+ more.
  - **Curve style:** haystack, straight, bezier, taxi, segments, and more.
  - **Colors:** bookmark color, character node color, user node color, edge color (with color pickers).
  - **Spacing:** node width/height, node/edge/rank separation, spacing factor.
  - **Alignment:** upper-left, upper-right, down-left, down-right.
  - **Theme integration:** optionally use SillyTavern's UI theme colors.
  - **Node locking:** toggle node position lock on/off.
  - **Swipe scaling:** scale node size by swipe count.
  **完整视觉定制**
  - **节点形状：** 椭圆、三角、矩形、菱形、星形、五边形、六边形、八边形等 20+ 种。
  - **连线样式：** haystack、直线、贝塞尔、taxi、线段等。
  - **颜色设置：** 书签色、角色节点色、用户节点色、连线色（颜色选择器）。
  - **间距：** 节点宽高、节点/连线/层级间距、间距因子。
  - **对齐方式：** 左上、右上、左下、右下。
  - **主题集成：** 可选择使用 SillyTavern 的 UI 主题色。
  - **节点锁定：** 开关节点位置锁定。
  - **滑动缩放：** 按滑动次数缩放节点大小。

- **🔧 Slash Command** — Use `/tl` in chat to open the timeline. `/tl r` to force-reload the graph.
  **斜杠命令** — 聊天中输入 `/tl` 打开时间线，`/tl r` 强制重载图谱。

- **👥 Group Chat Support** — Works with group chats, showing all member conversations in the timeline.
  **群聊支持** — 支持群聊，展示所有成员对话。

---

## 📦 Installation / 安装

1. In SillyTavern, go to **Extensions** → **Install Extension**.
2. Enter the extension URL:
   ```
   https://github.com/lumenbloom/Extension-Timeline-Pro
   ```
3. Restart SillyTavern (or reload extensions).

Alternatively, manually clone into `SillyTavern/data/default-user/extensions/`:

```bash
cd SillyTavern/data/default-user/extensions/
git clone https://github.com/lumenbloom/Extension-Timeline-Pro.git
```

---

## 🚀 Usage / 使用

1. Open a chat with a character or group.
2. In the extension panel, find **Timeline Pro** and click **Show Timeline**.
   — or type `/tl` in the chat input.
3. Explore the graph:
   - **Click** a node → detailed tooltip with session list.
   - **Double-click** → jump to that message.
   - **Click the rotate button** (↔) → toggle orientation.
   - **Click the expand button** (⇕) → show/hide swipe nodes.
   - **Search** in the top bar → filter messages.
4. Click the **×** or outside the modal to close.

---

## ⚙️ Configuration / 设置

All settings persist across sessions. Accessible from the Timeline Pro drawer panel:

| Setting | Description | Default |
|---------|-------------|---------|
| Lock Nodes | Prevent node movement after layout | ✅ |
| Fixed Tooltip | Pin tooltip to bottom-left corner | ❌ |
| Avatar As Root | Use character avatar as root node | ✅ |
| Show Legend | Display interactive legend | ✅ |
| Scale nodes with swipes | Size nodes by swipe count | ❌ |
| Use UI Theme | Use ST theme colors for nodes | ❌ |
| Node Shape | Shape of nodes | ellipse |
| Curve Style | Edge curve style | taxi |
| Alignment | Graph alignment direction | UL |
| Bookmark Color | Color for bookmark paths | #ff0000 |
| Character Node Color | Default character node color | #FFFFFF |
| User Node Color | Default user node color | #ADD8E6 |
| Edge Color | Default edge color | #555 |

---

## 🧩 Dependencies / 依赖

Bundled with the extension (no manual install needed):

- [Cytoscape.js](https://js.cytoscape.org/) — Graph rendering
- [cytoscape-dagre](https://github.com/cytoscape/cytoscape.js-dagre) — Dagre layout
- [cytoscape-context-menus](https://github.com/cytoscape/cytoscape.js-context-menus) — Right-click menu
- [cytoscape-popper](https://github.com/cytoscape/cytoscape.js-popper) — Tooltip positioning
- [Tippy.js](https://atomiks.github.io/tippyjs/) — Tooltips
- [dagre](https://github.com/dagrejs/dagre) — Graph layout algorithm

---

## ⌨️ Development / 开发

```bash
# The extension is plain JS — no build step required.
# Edit files directly, then reload the extension in SillyTavern.
```

**File structure:**

```
Extension-Timeline-Pro/
├── index.js              # Main entry point, settings, Cytoscape init
├── timeline.html         # UI drawer panel HTML
├── tl_utils.js           # Navigation, modal management, swipe handling
├── tl_style.js           # Node/edge styling, highlight logic, gold path
├── tl_graph.js           # Graph orientation, search highlighting
├── tl_node_data.js       # Data fetching, preprocessing, node building
├── tl_style.css          # Stylesheet
├── manifest.json         # Extension manifest
└── lib/                  # Third-party dependencies
    ├── cytoscape.min.js
    ├── cytoscape-dagre.min.js
    ├── cytoscape-context-menus.min.js / .css
    ├── cytoscape-popper.min.js
    ├── dagre.js
    ├── tippy.umd.min.js / tippy.css
    └── *.min.css         # Theme CSS files
```

---

## 📜 Version / 版本

**v2.1.0** — Author: [lumenbloom](https://github.com/lumenbloom)

---

## 🗺️ Roadmap / 路线图

- [ ] Edge labels
- [ ] Minimap mode
- [ ] More context menu options
- [ ] Experimental multi-tree view
- [ ] iOS mobile tap support

---

## 🤝 Contributing / 贡献

Issues, feature requests, and PRs are welcome at the [GitHub repository](https://github.com/lumenbloom/Extension-Timeline-Pro).

---

## 📄 License / 许可

MIT
