---
name: connect-my-computer
description: Set up Hey Atu so that this AI app can use the user's own computer, or fix the connection. Use when the user asks how to connect their computer, Mac or Linux machine, when the Hey Atu tools are not available, or when they fail with "offline", "no active plan", "not linked" or an authorisation error.
---

# Connect my computer

Hey Atu has three parts:

- The **agent** on the user's Mac or Linux computer. It runs the tools.
- The user's **Hey Atu account**: a Google sign-in. The computer is linked to it.
- This **AI app**. It connects to `https://heyatu.com/mcp` and the user
  approves it on the computer.

## First setup

Give the user these steps. They run them on the computer, not on a phone.

1. **Install.** In Terminal on the computer, run:

   ```sh
   curl -fsSL https://heyatu.com/install | sh -s -- --for=mcp
   ```

   It checks the computer, installs Pi if the user agrees, and installs the
   Hey Atu agent.
2. **Link the account.** Setup opens a page in the browser. The user signs in
   with Google and checks that the page shows the same code as Terminal, then
   selects **Link this computer**. An account can have up to 3 computers.
3. **Start the plan.** A new account can start a free trial on the same page.
   Stripe asks for a card; nothing is charged during the trial.
4. **Connect this app.** The user connects Hey Atu in this app and signs in
   with the same Google account. The computer then asks to approve the app,
   with a code. The user approves only if the codes match.

Then try a small request, for example: "List the folders in my home folder."

Details: https://heyatu.com/start/mcp

## Fix a problem

| Symptom | Fix |
|---|---|
| The tools do not show | Connect Hey Atu in the app again, and approve it on the computer |
| "The computer is offline" | Wake or start the computer. Check with `pi-remote status` |
| "no active plan" | Start the trial or renew the plan at https://heyatu.com/account |
| The sign-in page waits for a computer | Run the install command on the computer, or `pi-remote account link` if Hey Atu is installed |
| "The MCP gateway is off" | Run `pi-remote mcp on` on the computer |
| The account has 3 computers | Remove one at https://heyatu.com/account |
| The approval does not show | Run `pi-remote mcp approve <code>` on the computer with the code from the page |

## Tell the user these facts when they decide

- An approved app can read and change files and run commands on the computer,
  as the user's account. Approve only apps that they trust.
- The app's requests pass the Hey Atu relay without end-to-end encryption. The
  relay forwards them and does not store them.
- Protect the AI app account with 2-step verification: a person who controls
  it can use the connected computer.
- To stop all access: remove the computer at https://heyatu.com/account, or
  run `pi-remote mcp off` on the computer.
