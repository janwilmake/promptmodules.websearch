# Scaling MCP - Achieving Scalable MCP Capabilities by dynamicly enabling them (only when relevant)

[A lot of LLMs started going downhill when websearch was added](https://x.com/EastlondonDev/status/1954229810600804604). I think the [search api](https://docs.parallel.ai/search-api/search-quickstart.md) is mainly beneficial to be used as additional context when the prompt from the user requires context that falls outside of the scope of what the model should know and be able to recall. When the model DOES know something, it's best to not clutter up the context at all with any MCP, tools, or context with searched information.

Generally for top-tier models, it's useful to add web search if:

- the prompt requests something that requires information after the cut-off date
- the prompt requests very specific facts that ought to be verified
- the prompt specifically requests to verify information or provide confidence level for certain facts.

This [prompt_module](https://promptmodules.com) aims to suggest the [Parallel Search MCP tool](https://docs.parallel.ai/features/remote-mcp) only if it seems beneficial to answer to the user prompt (based on above guidelines).

TODO:

- Wait for [prior art research](https://tasks.gptideas.com/task/43ce637c-dcb1-4539-8da3-bf1d850896e3)
- Ask audience about this routing thing posing the problem; there may be other MCP OSS routers
- Create a Cerebras "relevance prompt" targeting [gpt-5](https://simonwillison.net/2025/Aug/7/gpt-5/)
- Integrate this with LMPIFY through the prompt_modules protocol to demonstrate the power of this.
- Use it in conjunction with many other MCPs to show scaling MCP is possible

BACKLOG:

- Figure out the best way to make this cross-model compatible
