I think the [search api](https://docs.parallel.ai/search-api/search-quickstart.md) is mainly beneficial to be used as additional context when the prompt from the user requires context that falls outside of the scope of what the model should know and be able to recall. when the model DOES know something, it's best to not clutter up the context at all with any MCP, tools, or context with searched information.

Generally for top-tier models, it's useful to add search if:

- the prompt requests something that requires information after the cut-off date
- the prompt requests very specific facts that ought to be verified
- the prompt specifically requests to verify information or provide confidence level for certain facts.

This [prompt_module](https://promptmodules.com) aims to suggest the [Parallel Search MCP tool](https://docs.parallel.ai/features/remote-mcp) only if it seems beneficial to answer to the user prompt (based on above guidelines).
