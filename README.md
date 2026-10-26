# Dial for Cursor

Give the agent in Cursor a real phone number. Dial connects Cursor to the hosted
[Dial](https://getdial.ai) MCP server, so the agent can text, call, and react to
inbound messages and calls without you writing any HTTP code.

## What the agent can do

- **Phone numbers**: buy a number, including iMessage and WhatsApp lines, and
  configure how it answers calls.
- **Messages**: send and reply to SMS, iMessage and WhatsApp, one-to-one or in
  group conversations, with media, reactions, typing indicators and polls.
- **Voice calls**: place outbound calls handled by an AI voice agent and read
  the transcript when the call ends.
- **Inbound events**: wait for an incoming text (for example a verification
  code) or the end of a call, and screen inbound callers with allow lists.
- **Lookups**: check whether a number can receive iMessage or WhatsApp before
  sending.

## Setup

1. Install the **Dial** plugin from the Cursor Marketplace.
2. The first time the agent uses a Dial tool, Cursor opens a browser window to
   sign in to Dial with your email. New users create an account (including
   verifying a phone number) in the same window.
3. Ask the agent to check your account with `get_account_status`, then buy a
   number with `purchase_number` if you don't have one yet.

There are no API keys or variables to configure: the server uses OAuth, so
Cursor stores your sign-in for you.

## Example prompts

- "Buy me a US phone number and text +14155550123 that the deploy finished."
- "Call the restaurant at +14155550123 and book a table for two at 7pm, then
  tell me what they said."
- "Wait for the verification code that's about to arrive by SMS and paste it
  here."
- "Can +14155550123 receive iMessage?"

## Configuration details

The plugin declares one remote MCP server:

| Setting | Value |
| --- | --- |
| URL | `https://getdial.ai/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.1 (browser sign-in) |

Prefer a local server? Dial also runs over stdio with `npx -y @getdial/cli mcp`.
See the [MCP guide](https://docs.getdial.ai/integrations/tools/mcp).

## Pricing

Dial is pay-as-you-go: phone numbers, messages and call minutes are billed to
your Dial account. See [getdial.ai/pricing](https://getdial.ai/pricing).

## Links

- Documentation: https://docs.getdial.ai
- Privacy policy: https://getdial.ai/privacy
- Terms of service: https://getdial.ai/terms
- Support: support@getdial.ai
