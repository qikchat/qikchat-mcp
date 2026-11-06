# QikChat for Claude

Ask Claude about your QikChat lead numbers:

- How many leads did I get today?
- How many came in this month, by rep or by source?
- How many leads clicked through to the booking page, and how many booked?

The plugin only reads. It can't create, change or delete anything in QikChat, and it never sees lead names, emails, phone numbers or messages.

You need a [QikChat](https://qik-chat.com) account.

## Install in Claude Code

Install the plugin into a folder of its own:

```bash
mkdir ~/qikchat && cd ~/qikchat
claude plugin marketplace add qikchat/qikchat-mcp
claude plugin install qikchat@qikchat --scope project
claude
```

Then, connect your QikChat account:

1. Run `/mcp`.
2. Pick `plugin:qikchat:qikchat` and choose Authenticate.
3. Sign in to QikChat in the browser window that opens, and click Allow.

Use `--scope project` in a folder of its own. The plugin runs the whole Claude Code session as a QikChat agent that has the three QikChat tools and nothing else, so it can't run commands, edit files or browse. At user scope, every other Claude Code session would lose those tools too.

On claude.ai and Claude Desktop, the plugin's skill works with the QikChat connector. The agent and session settings apply to Claude Code only.

## What you can ask about

| Tool | What it answers |
| :- | :- |
| `whoami` | Which QikChat account and team you're connected as, and which client teams an agency admin can see |
| `lead_counts` | How many leads came in over a period, broken down by day, week, month, rep or source |
| `lead_funnel` | Of the leads captured in a period, how many clicked through to the booking page and how many booked a meeting |

Periods are `today`, `yesterday`, `this_week`, `last_week`, `this_month`, `last_month`, `last_7_days`, `last_30_days`, or a custom range of up to 400 days. QikChat works out the days in your own timezone, and weeks start on Monday.

Team leaders see their whole team. Team members see the leads assigned to them. Agency admins can ask about any client team in their agency.

## What QikChat shares with Claude

- Totals: lead counts, click-throughs and bookings.
- A few names: your first name, your team names, reps' names when you group by rep, and source names such as Webform or Zapier.

Lead details stay in QikChat. To see who a lead is, open the QikChat dashboard.

## Disconnect

In QikChat, open Settings, go to the Connected apps tab, and click Disconnect next to Claude Code. Claude loses access straight away.

## Privacy and support

- Privacy policy: https://app.qik-chat.com/privacy-policy
- Questions: use the chat on [qik-chat.com](https://qik-chat.com), or book a call there.

## License

MIT, see [LICENSE](LICENSE).
