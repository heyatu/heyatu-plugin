---
name: connect-my-computer
description: Set up Hey Atu so that this AI app can use the user's own computer, or fix the connection. Use when the user asks how to connect a computer, or when a Hey Atu tool is missing or fails.
---

# Connect my computer

Hey Atu has three parts. Setup needs all three, in this order:

1. **The computer.** The user opens https://heyatu.com/start/mcp on the
   computer, not on a phone, and runs the install command there:

   ```sh
   curl -fsSL https://heyatu.com/install | sh -s -- --for=mcp
   ```

2. **The account.** Setup opens a page in the computer's browser. The user
   signs in with Google, checks that the page shows the same code as Terminal,
   and selects **Link this computer**. A new account can start the free trial
   on the next page. An account holds up to 3 computers.
3. **This AI app.** The user connects Hey Atu in this app and signs in with
   the same Google account. The app shows a code. The user approves the app
   where the same code shows: the dialog on the computer, or the Hey Atu app
   on a paired phone. On the computer, `pi-remote mcp approve <code>` works too.

Then the user can try: "List the folders in my home folder."

## Fix a problem

| Message or symptom | Tell the user |
|---|---|
| The Hey Atu tools are missing | Connect Hey Atu in this app again, and approve it |
| "The computer is offline" | Wake or start the computer. Hey Atu runs after the user logs in |
| "no active plan" | Start the trial or renew the plan at https://heyatu.com/account |
| "Hey Atu is off for AI apps" | On the computer, run `pi-remote mcp on` |
| The sign-in page waits for a computer | Do step 1 on the computer. If Hey Atu is installed, run `pi-remote account link` |
| The account has 3 computers | Remove one at https://heyatu.com/account |

## Tell the user before they approve

- An approved app can read and change files and run commands on the
  computer, as the user. Approve only apps that the user trusts.
- The app's requests pass the Hey Atu relay without end-to-end encryption.
  The relay forwards them and keeps no copy.
- A person who controls the AI app account can use the computer. Protect it
  with 2-step verification.
- To stop all access: remove the computer at https://heyatu.com/account, or
  run `pi-remote mcp off` on the computer.
