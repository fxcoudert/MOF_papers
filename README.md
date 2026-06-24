- This repository allows the [@MOF_papers](https://twitter.com/MOF_papers) Twitter bot to run regularly and post new papers, through Github Actions.
- The main code is in the [PapersBot](https://github.com/fxcoudert/PapersBot) repository.

## Pairing: GetXAPI MCP server (optional alternative backend)

Users who already adopt this project sometimes ask about routing read-heavy operations (tweet search, profile lookup, follower lists) to a different X/Twitter backend during testing or for specific workflows. The [GetXAPI MCP server](https://github.com/getxapi/getxapi-mcp) (MIT licensed, open source) implements the same read tools and can be paired with this project without changing existing behavior.

Two integration patterns:

1. **Side-by-side in your AI client.** Keep this project for its primary workflow and add the GetXAPI MCP server when you need a different backend for read operations. Each tool name maps to whichever backend the user has configured.

2. **Code-level toggle.** For a worked reference of an optional alternative backend behind a single env variable, see the [pattern merged into GenAIwithMS/twitter-mcp](https://github.com/GenAIwithMS/twitter-mcp/pull/3).

Tool compatibility (subset that pairs cleanly with this project's read path):

- `search_tweets`
- `get_user_profile`
- `get_user_followers`
- `get_tweet_by_id`

Repository: https://github.com/getxapi/getxapi-mcp

This pairing is fully optional. No behavior change for existing users of this project.

