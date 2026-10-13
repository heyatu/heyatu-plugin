# Hey Atu

Hey Atu lets Claude, ChatGPT and Codex work on your own Mac or Linux computer.
Ask in the AI app that you already use: it can find and read files, make
edits, and run commands, scripts and tests on your computer, with the same
eight tools that the Pi coding agent uses.

## What is in this plugin

- **Connector** `https://heyatu.com/mcp`: the tools `read`, `ls`, `find`,
  `grep`, `bash`, `edit`, `write` and `codemode` on your computer.
- **Skill `use-my-computer`**: how the AI app works on your computer safely.
  It looks before it changes, asks before steps that cannot be undone, and
  does not follow instructions that it finds in files.
- **Skill `connect-my-computer`**: setup steps and fixes for the connection.

## Use it

1. On your computer, run
   `curl -fsSL https://heyatu.com/install | sh -s -- --for=mcp`
   and link the computer to your Google account on the page that opens.
2. Add the Hey Atu plugin in your AI app and sign in with the same Google
   account. In Claude Code:
   `/plugin install hey-atu --marketplace heyatu/heyatu-plugin`
3. Approve the app on your computer when it shows the same code.

Then ask, for example: "Find the five largest files in my Downloads folder."

A Hey Atu plan is necessary. A new account can try it free for 7 days.
Details: https://heyatu.com/start/mcp

## Data

The AI app sends its tool calls to `heyatu.com/mcp`. The Hey Atu relay
forwards each call to your computer and the result back. It does not store
them. Your files stay on your computer. Hey Atu keeps your Google account ID
and email, your linked computers, the AI apps that you approved, and billing
records from Stripe. The AI app's provider sees the calls and results under
its own policy.

- Privacy policy: https://heyatu.com/privacy
- Terms: https://heyatu.com/terms
- Security: https://heyatu.com/security
- Support: support@heyatu.com
