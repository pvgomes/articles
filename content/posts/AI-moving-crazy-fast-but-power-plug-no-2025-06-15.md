+++
date = '2025-07-01T12:07:38+02:00'
draft = false
title = 'AI Moving Crazy Fast but Power Plug No 2025 06 15'
+++
Everyday we see tons of articles about how fast AI is running and growing, fast app setups and incredibly performance savings on all kinds of industry. There’s also a huge discussion over regulating AI and the copyright data the models are getting. But how about the VERY basics? The foundation that is base for computers to run? Thats right, energy ⚡️.

Zoom image will be displayed

![](https://miro.medium.com/v2/resize:fit:700/1*Mu1NaW8reupEX4jryHkm2w.png)

## 1\. A growth curve that now feels vertical

* *   In just eight months we jumped from GPT-4o to GPT-4.1, which can swallow **a full million-token context** — roughly the text of _War and Peace_ twice over — and still answer in real time ([OpenAI](https://openai.com/index/gpt-4-1/)).
* *   OpenAI’s “o3” reasoning model, released in May and repriced in June, cut its list price by **\-80 %** overnight while bumping reasoning depth, making yesterday’s premium capability today’s default ([InfoWorld](https://www.infoworld.com/article/4008535/openais-o3-price-plunge-changes-everything-for-vibe-coders.html)).
* *   Anthropic’s Claude Sonnet 4 followed within weeks, pushing 200 K-token windows into mainstream production work ([docs.anthropic.com](https://docs.anthropic.com/en/docs/about-claude/models/overview)).

That’s break-neck evolution by any historic tech standard — but each step up the ladder devours more silicon cycles and, crucially, more electrons.

## 2\. The uncomfortable physics: we’re running out of grid 🪫

Data-point What it tells us Source **+100 %** projected jump in data-center electricity use by 2030 (→ 945 TWh, > Japan’s consumption) AI is _the_ dominant driver. ([IEA](https://www.iea.org/news/ai-is-set-to-drive-surging-electricity-demand-from-data-centres-while-offering-the-potential-to-transform-how-the-energy-sector-works?utm_source=chatgpt.com)) Microsoft has **canceled or deferred 2 GW** of planned capacity in the last six months Even trillion-dollar firms hit power limits. ([Reuters](https://www.reuters.com/technology/microsoft-pulls-back-more-data-center-leases-us-europe-analysts-say-2025-03-26/?utm_source=chatgpt.com)) Developers now pick sites on “access to power” first, not land price or fiber Utility-queue delays are the #1 risk. ([pv magazine USA](https://pv-magazine-usa.com/2025/06/17/access-to-power-is-the-key-driver-behind-data-center-siting-decisions/?utm_source=chatgpt.com)) Vacancy in U.S. hyperscale markets at a **record-low 0.7 %** Projects are stuck waiting for megawatts. ([The Register](https://www.theregister.com/2025/03/19/datacenter_vacancy_record_low/?utm_source=chatgpt.com)) Typical ChatGPT-style prompt ≈ 0.3 Wh; a short video generation can hit **110 Wh** Per-request energy is small but scales with billions of calls. ([Epoch AI](https://epoch.ai/gradient-updates/how-much-energy-does-chatgpt-use?utm_source=chatgpt.com), [Wall Street Journal](https://www.wsj.com/tech/ai/ai-prompt-video-energy-electricity-use-046766d6?utm_source=chatgpt.com))

Add it up and you get the picture TechXplore summed up this week: _“AI depends entirely on data centers, which could consume 3 % of the world’s electricity by 2030.”_ ([Tech Xplore](https://techxplore.com/news/2025-07-tech-giants-scramble-ai-looming.html?utm_source=chatgpt.com))

## 3\. Why “autonomous agents” multiply the load

A classic chat exchange might run a few hundred tokens round-trip. An autonomous agent:

1. 1.  Reads the user brief (1 K tokens).
1. 2.  Plans in detail (adds 3–5 K).
1. 3.  Searches the web & ingests docs (10–50 K).
1. 4.  Iterates tool calls until success (another 20–100 K).

Barclays puts the multiplier at **≈ 25× more tokens per user task** than interactive chatbots ([Business Insider](https://www.businessinsider.com/ai-super-agents-enough-computing-power-openai-deepseek-2025-3?utm_source=chatgpt.com)). More tokens → more GPU time → more electricity and dollar cost. Even if models get cheaper per token, agents _explode_ the token count.

Energy researchers are sounding the same alarm on the hardware side, proposing “energy-per-token” as a first-class benchmark ([ACM Digital Library](https://dl.acm.org/doi/abs/10.1145/3721146.3721953?utm_source=chatgpt.com)).

## 4\. Model economics today

_Prices are public list rates as of July 2025._

Model Context window **Input $/M tokens** **Output $/M tokens** 10 K-token chat\* 100 K-token agent\* **OpenAI o3** 128 K $2.00 $8.00 **$0.05** **$0.50** **GPT-4.1** 1 M $2.00 $8.00 **$0.05** **$0.50** **Claude Sonnet 4** 200 K $3.00 $15.00 **$0.09** **$0.90**

\*Assumes a 50 / 50 split between input and output tokens.  
Sources: OpenAI pricing table ([OpenAI](https://openai.com/index/gpt-4-1/)), Infoworld o3 update ([InfoWorld](https://www.infoworld.com/article/4008535/openais-o3-price-plunge-changes-everything-for-vibe-coders.html)), Anthropic model overview ([docs.anthropic.com](https://docs.anthropic.com/en/docs/about-claude/models/overview)).

**Take-away:** o3 and GPT-4.1 are cost-parity on paper, but both still double-charge Sonnet on large agent runs. The real sticker shock comes from the _token volume_, not the per-token rate.

## 5\. So… is there enough juice?

* *   **Short term:** Cloud providers are racing to bolt GPUs onto nuclear plants (AWS-Talen in Pennsylvania) ([Finance & Commerce](https://finance-commerce.com/2025/06/amazon-data-centers-pennsylvania-nuclear-power/?utm_source=chatgpt.com)) and to revive mothballed reactors ([Reuters](https://www.reuters.com/sustainability/boards-policy-regulation/trump-joins-tech-energy-executives-amid-ai-push-2025-07-15/?utm_source=chatgpt.com)).
* *   **Medium term:** Expect more on-site renewables, behind-the-meter gas turbines, and workload shifting to regions with spare capacity.
* *   **Long term:** Without a serious grid build-out or a breakthrough in model efficiency (think sparse mixture-of-experts everywhere), fully autonomous “super agents” at global scale will hit a hard energy ceiling.

# Bottom line

AI capabilities are compounding **exponentially**, but electricity infrastructure moves in **decades**. Unless the energy curve bends up — or the token curve bends down — 2025’s marvels risk stalling in a very old-fashioned bottleneck: not enough power outlets.

# References

* *   [https://openai.com/index/gpt-4-1/](https://openai.com/index/gpt-4-1/)
* *   [https://www.infoworld.com/article/4008535/openais-o3-price-plunge-changes-everything-for-vibe-coders.html](https://www.infoworld.com/article/4008535/openais-o3-price-plunge-changes-everything-for-vibe-coders.html)
* *   [https://docs.anthropic.com/en/docs/about-claude/models/overview](https://docs.anthropic.com/en/docs/about-claude/models/overview)
* *   [https://www.iea.org/news/ai-is-set-to-drive-surging-electricity-demand-from-data-centres-while-offering-the-potential-to-transform-how-the-energy-sector-works?utm\_source=chatgpt.com](https://www.iea.org/news/ai-is-set-to-drive-surging-electricity-demand-from-data-centres-while-offering-the-potential-to-transform-how-the-energy-sector-works?utm_source=chatgpt.com)
* *   [https://www.reuters.com/technology/microsoft-pulls-back-more-data-center-leases-us-europe-analysts-say-2025-03-26/?utm\_source=chatgpt.com](https://www.reuters.com/technology/microsoft-pulls-back-more-data-center-leases-us-europe-analysts-say-2025-03-26/?utm_source=chatgpt.com)
* *   [https://pv-magazine-usa.com/2025/06/17/access-to-power-is-the-key-driver-behind-data-center-siting-decisions/?utm\_source=chatgpt.com](https://pv-magazine-usa.com/2025/06/17/access-to-power-is-the-key-driver-behind-data-center-siting-decisions/?utm_source=chatgpt.com)