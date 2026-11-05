# Superagent

Playground repository for the [dsh-superagent](https://github.com/deepseek-ai/dsh-superagent-prototype) prototype: a proactive coding agent that listens to GitHub and works on requests in its own session, branch and pull request.

## Sending a request

The agent acts on its own GitHub account's notifications, so a message written by that same account is ignored. Requests therefore arrive through the `agent-request` workflow:

1. Open **Actions → agent-request → Run workflow**.
2. Put the request in the `request` field; leave `issue` empty to open a new issue.
3. The workflow posts a comment mentioning the agent account as `github-actions[bot]`.
4. The agent receives the mention, opens a ticket, works on the branch `agent/<ticket>` and opens a pull request.

Never put secrets, tokens or personal data in a request. The agent never merges on its own.
