# 🤖 Termux-AI · Terminal AI Chat Client

> A powerful, feature-rich terminal-based AI chat client powered by **OpenRouter API**. Works seamlessly on **Termux (Android)**, **Linux**, and **macOS**.

<div align="center">

![Version](https://img.shields.io/badge/version-3.0-blue?style=flat-square)
![Language](https://img.shields.io/badge/language-Bash-green?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-brightgreen?style=flat-square)
![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20Android-informational?style=flat-square)

</div>

---

## ✨ Features

- **🎯 Multi-Model Support** — Access 50+ AI models (GPT-4o, Claude, Gemini, Llama, etc.)
- **📝 Markdown Rendering** — Beautiful syntax highlighting with `glow`, `bat`, or ANSI fallback
- **💾 Chat Persistence** — Save and load conversations as JSON files for future reference
- **🎨 Rich Terminal UI** — Colored output, spinners, and intelligently formatted responses
- **🔐 Secure Configuration** — API keys stored with restricted permissions (mode 600)
- **🔄 Auto-Dependency Detection** — Automatically detects and installs missing dependencies
- **⚡ Network Resilient** — Built-in retry logic and graceful timeout handling
- **🌍 Cross-Platform Support** — Termux, Ubuntu, Fedora, Arch, macOS, and more

---

## 📋 Requirements

| Requirement | Details |
|---|---|
| **curl** | HTTP client for API requests (auto-installed if missing) |
| **jq** | JSON processor for response parsing (auto-installed if missing) |
| **OpenRouter API Key** | Get a free API key at [openrouter.ai/keys](https://openrouter.ai/keys) |

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/Corrupted-Devil/Termux-AI
cd Termux-AI
```

### 2. Make the Script Executable
```bash
chmod +x Termux-AI.sh
```

### 3. Launch the Application
```bash
./Termux-AI.sh
```

### 4. Enter Your API Key
On first run, you'll be prompted for your OpenRouter API key. It will be securely saved to `~/.openrouter_chat.conf` for future sessions.

---

## 💬 Available Commands

| Command | Description |
|---------|-------------|
| `/help` | Display all available commands and shortcuts |
| `/clear` | Clear conversation history |
| `/history` | Display full chat with markdown rendering |
| `/model` | Switch to a different AI model |
| `/key` | Update or change your API key |
| `/md` | Toggle markdown rendering on/off |
| `/save` | Save current chat to a JSON file |
| `/load` | Load a previously saved conversation |
| `/exit` or `/quit` | Exit the application |

---

## 🎮 Usage Examples

### Start a conversation
```
You › Tell me about machine learning
```

### Switch models during chat
```
You › /model
Current model: openai/gpt-4o-mini
New model (blank = keep current): anthropic/claude-opus-4-5
```

### Save your chat for later
```
You › /save
Filename (default: chat_20260628_120000.json): my_research.json
✓ Chat saved to ~/.openrouter_chats/my_research.json
```

### Toggle markdown rendering
```
You › /md
Markdown rendering disabled (plain text + typing effect).
```

---

## 📂 Configuration & Storage

Configuration and chat history are stored in your home directory:

```
~/.openrouter_chat.conf       # Main config (API key + default model)
~/.openrouter_chats/          # Saved conversation directory
  ├── chat_20260628_120000.json
  ├── my_research.json
  ├── coding_session.json
  └── ...
```

**Config File Format** (`~/.openrouter_chat.conf`):
```ini
API_KEY=sk-or-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
DEFAULT_MODEL=openai/gpt-4o-mini
```

---

## 🎨 Supported AI Models

Access 50+ models from leading providers via OpenRouter:

| Provider | Available Models |
|---|---|
| **OpenAI** | `openai/gpt-4o-mini`, `openai/gpt-4-turbo`, `openai/gpt-3.5-turbo` |
| **Anthropic** | `anthropic/claude-opus-4-5`, `anthropic/claude-3-sonnet`, `anthropic/claude-3-haiku` |
| **Google** | `google/gemini-2.0-flash-001`, `google/gemini-pro` |
| **Meta** | `meta-llama/llama-3.3-70b-instruct`, `meta-llama/llama-2-70b-chat` |
| **Mistral** | `mistralai/mistral-large`, `mistralai/mistral-7b` |
| **And many more!** | Visit [openrouter.ai/models](https://openrouter.ai/models) for the complete list |

---

## 🖥️ Platform-Specific Installation

### Termux (Android)
```bash
pkg install bash curl jq git
git clone https://github.com/Corrupted-Devil/Termux-AI.git
cd Termux-AI
chmod +x Termux-AI.sh
./Termux-AI.sh
```

### Ubuntu / Debian
```bash
sudo apt-get update
sudo apt-get install curl jq git
git clone https://github.com/Corrupted-Devil/Termux-AI.git
cd Termux-AI
chmod +x Termux-AI.sh
./Termux-AI.sh
```

### macOS
```bash
brew install curl jq git
git clone https://github.com/Corrupted-Devil/Termux-AI.git
cd Termux-AI
chmod +x Termux-AI.sh
./Termux-AI.sh
```

### Fedora / RHEL / CentOS
```bash
sudo dnf install curl jq git
git clone https://github.com/Corrupted-Devil/Termux-AI.git
cd Termux-AI
chmod +x Termux-AI.sh
./Termux-AI.sh
```

### Arch / Manjaro
```bash
sudo pacman -S curl jq git
git clone https://github.com/Corrupted-Devil/Termux-AI.git
cd Termux-AI
chmod +x Termux-AI.sh
./Termux-AI.sh
```

---

## 🎨 UI Features & Formatting

### Syntax Highlighting
Code blocks are automatically highlighted with language-specific colors:
- **Python** → Amber
- **JavaScript** → Bright Yellow  
- **TypeScript** → Sky Blue
- **Bash/Shell** → Light Green
- **JSON/XML** → Light Cyan
- And many more languages!

### Markdown Support
Beautifully rendered markdown including:
- **Headers** (# ## ###) with visual underlines
- **Bold** and *italic* text formatting
- `Inline code` with distinct background styling
- ```code blocks``` with full syntax highlighting
- > Blockquotes with visual indicators
- Ordered and unordered lists
- Horizontal dividers and separators

---

## 🔧 Advanced Configuration

### Disable Auto-Dependency Installation
Edit the `check_dependencies()` function in `Termux-AI.sh` if you prefer manual dependency management.

### Use Custom Models
In the `/model` command, enter any model identifier from [openrouter.ai/models](https://openrouter.ai/models). The list updates regularly with new model releases.

### Typing Effect
When markdown rendering is disabled (`/md`), responses display with a realistic typing effect for enhanced interactivity.

### Environment Variables
```bash
# Override default model (optional)
export TERMUX_AI_MODEL="anthropic/claude-opus-4-5"

# Disable colored output
export NO_COLOR=1
```

---

## 🐛 Troubleshooting

### ❌ "Missing required deps: curl jq"
The script will attempt automatic installation. If it fails:

```bash
# Ubuntu/Debian
sudo apt-get install curl jq

# Fedora/RHEL
sudo dnf install curl jq

# macOS
brew install curl jq

# Termux (Android)
pkg install curl jq
```

### ❌ "Invalid API key (401)"
Your API key is invalid or expired. Get a new one at [openrouter.ai/keys](https://openrouter.ai/keys), then update it:
```bash
You › /key
Enter new API key: sk-or-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
✓ API key updated successfully
```

### ❌ "Network error — check your connection"
Ensure:
- You have active internet connectivity
- OpenRouter API is accessible (check [status page](https://openrouter.io/status))
- Your firewall isn't blocking HTTPS traffic

### ❌ "Empty response. Model may be unavailable"
The selected model is currently unavailable. Try:
```bash
You › /model
# Select a different model from the list
```

Or check the [OpenRouter status page](https://openrouter.io/status) for service updates.

### ❌ "Permission denied"
Ensure the script is executable:
```bash
chmod +x Termux-AI.sh
```

---

## 📊 Chat History Format

Saved conversations are stored as human-readable JSON:

```json
{
  "metadata": {
    "model": "openai/gpt-4o-mini",
    "saved_at": "2026-06-28T12:00:00Z",
    "message_count": 5,
    "total_tokens": 2048
  },
  "messages": [
    {
      "role": "user",
      "content": "Hello! How can you help me?"
    },
    {
      "role": "assistant",
      "content": "Hi there! I'm an AI assistant ready to help with a wide range of tasks..."
    }
  ]
}
```

You can easily parse, share, or archive these files for future reference.

---

## 🤝 Contributing

We welcome contributions! Please feel free to:

- 🐛 **Report bugs** — Open an issue with detailed reproduction steps
- 💡 **Suggest features** — Describe your use case and desired functionality
- 🔄 **Submit pull requests** — Follow our code style and include tests
- 📚 **Improve documentation** — Help us keep the README accurate and clear
- 🔧 **Share improvements** — Any enhancement is appreciated!

For major changes, please open an issue first to discuss the proposed modifications.

---

## 📄 License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for complete terms and conditions.

---

## 🔗 Resources & Links

- **OpenRouter Platform** — https://openrouter.ai
- **Get Your API Key** — https://openrouter.ai/keys
- **Available Models List** — https://openrouter.ai/models
- **Service Status** — https://openrouter.io/status
- **GitHub Repository** — https://github.com/Corrupted-Devil/Termux-AI
- **Report Issues** — https://github.com/Corrupted-Devil/Termux-AI/issues

---

## 💡 Tips & Best Practices

1. **🎯 Maintain Context** — Keep your conversation history for better context-aware AI responses
2. **🔄 Experiment with Models** — Different models excel at different tasks (coding, writing, analysis, etc.)
3. **💾 Archive Important Chats** — Use `/save` to preserve valuable conversations for future reference
4. **⚡ Toggle Markdown** — Disable markdown (`/md`) for simpler, faster output when needed
5. **📤 Share & Parse** — Saved chats are plain JSON—easily shareable, archivable, or scriptable
6. **🔐 Rotate API Keys** — Regularly update your API key for enhanced security
7. **🌐 Check Rate Limits** — Monitor your OpenRouter usage to avoid unexpected limits

---

## 🎬 Getting Started Video & Demos

For step-by-step guidance, check out the [Discussions](https://github.com/Corrupted-Devil/Termux-AI/discussions) section for tutorials and demo videos.

---

<div align="center">

**Made with ❤️ for terminal enthusiasts and AI developers everywhere**

**⭐ If this project helps you, please consider giving it a star on GitHub!**

**Happy chatting! 🚀**

</div>
