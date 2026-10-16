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
   checks that the page shows the same code as Terminal, and selects
   **Continue with Google**. The computer is then linked. An account holds up
   to 3 computers.
3. **This AI app.** The user connects Hey Atu in this app and signs in with
   the same Google account. The sign-in page shows a code, and the computer
   shows a Hey Atu window with the same code. The user selects **Allow** in
   that window. On the computer, `heyatu mcp approve <code>` works too.
   When this app waited for a computer during setup, the link allows it, and
   the sign-in goes on by itself.

Then the user can try: "List the folders in my home folder."

## Another computer

One connection of this app uses one computer. To use another computer:

1. On that computer, do steps 1 and 2 with the same Google account.
2. Connect Hey Atu again in this app. The sign-in page lists the linked
   computers. The user chooses the other one and selects **Allow** on it.

## Fix a problem

| Message or symptom | Tell the user |
|---|---|
| The Hey Atu tools are missing | Connect Hey Atu in this app again, and approve it |
| "The computer is offline" | Wake or start the computer. Hey Atu runs after the user logs in |
| "no active plan" | Start the trial or renew the plan at https://heyatu.com/account |
| "Hey Atu is off for AI apps" | On the computer, run `heyatu mcp on` |
| The sign-in page waits for a computer | Do step 1 on the computer, with the same Google account. If Hey Atu is installed, run `heyatu account link`. The page goes on by itself |
| The sign-in page shows the wrong Google account | Select **Use another Google account** on that page |
| No Hey Atu window on the computer | On the computer, run `heyatu mcp approve <code>` with the code from the sign-in page |
| The account has 3 computers | Remove one at https://heyatu.com/account |

## Tell the user before they approve

- An approved app can read and change files and run commands on the
  computer, as the user. Approve only apps that the user trusts.
- The app's requests pass the Hey Atu relay without end-to-end encryption.
  The relay forwards them and keeps no copy.
- A person who controls the AI app account can use the computer. Protect it
  with 2-step verification.
- To stop all access: remove the computer at https://heyatu.com/account, or
  run `heyatu mcp off` on the computer.
