## JC Daily log 20260524

### Wordpress Studio and using the CLI

https://developer.wordpress.com/docs/developer-tools/studio/cli/

Studio CLI comes bundled with Studio, and it’s also available as a standalone npm module, [wp-studio](https://www.npmjs.com/package/wp-studio).

If you already have Studio installed, the easiest way to try the CLI is to follow the instructions

Studio CLI is a globally available command-line utility that lets you interact with [WordPress Studio](https://developer.wordpress.com/docs/developer-tools/studio/) features from your terminal, regardless of whether Studio is open or not.

It’s especially useful for:

- Managing local Studio sites.
- Creating and updating preview sites on WordPress.com.
- Running WP-CLI commands.
- Integrate with AI coding agents. Every site comes with an AGENTS.md file.
- Integrating Studio into scripts and build steps.

---

### Using MCP with Claude and WordPress.Com and .Org

#### WORDPRESS.COM

here's the full process for anyone else wanting to do it:

**Step 1: Enable MCP on WordPress.com**
Log in to your WordPress.com account, go to your profile, and look for the **MCP** option in the left sidebar. Toggle it on to allow AI tool access.

**Step 2: Connect in Claude.ai**
Open Claude.ai (web or app), go to **Settings → Connectors**, search for **WordPress.com**, and click **Connect**. Approve the OAuth connection when prompted.

That's genuinely it — two steps, no plugins, no config files, no Node.js, no Application Passwords. WordPress.com handles authentication via OAuth 2.1, so the whole thing is a one-click setup compared to the self-hosted process.

**The key difference vs WordPress.org:**

| | WordPress.com | WordPress.org (self-hosted) |
|---|---|---|
| Works in claude.ai | ✅ Yes | ❌ Not yet |
| Works in Claude Desktop | ✅ Yes | ✅ Yes |
| Setup complexity | 2 clicks | ~15 minutes |
| Auth method | OAuth 2.1 | Application Password |
| Plugin required | None | MCP Adapter plugin |

Want me to turn this comparison into a follow-up post on your site to go alongside the WordPress.org guide you just published?

#### WORDPRESS.ORG

Here's the Claude Desktop app to get you started:Once you've installed it, here's the rough setup process:

1. **Install the MCP adapter plugin** on your WordPress.org site — search for `wordpress/mcp-adapter` in the WordPress plugin directory or find it on GitHub.

2. **Generate an Application Password** in your WordPress admin under Users → Profile → Application Passwords.

3. **Configure Claude Desktop** — go to Settings → Connectors (or edit the `claude_desktop_config.json` file) and add your site's MCP endpoint URL along with your credentials.

4. **Test it** — open Claude Desktop, click the `+` button in the chat input, and your WordPress site tools should appear.

Once it's set up, you'll be able to manage posts, pages, settings, and more through conversation — just like you're doing with your WordPress.com site here. Want help with any specific step in the process?
