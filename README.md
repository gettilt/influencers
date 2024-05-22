<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Influencers
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
Influencers are the new global brands and will dictate where consumers spend their money. Companies that host influencers, support influencers, or build on behalf of influencers will win.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| ADBE | Adobe provides creative software tools that influencers use to produce high-quality content. | chat_gpt,claude |
| AMZN | Amazon (Twitch) hosts gaming influencers and offers affiliate marketing opportunities for influencers. | chat_gpt,claude,twitter,google |
| BABA | Alibaba (Taobao Live) supports e-commerce influencers in China, enabling live-streaming sales. | chat_gpt |
| BIDU | Baidu (iQIYI) is a key platform for video influencers in China, providing content creation and distribution opportunities. | chat_gpt |
| CRM | Salesforce offers marketing tools that help influencers manage and grow their audience. | chat_gpt |
| ETSY | Etsy allows influencers to sell unique, handmade products directly to their followers. | chat_gpt,claude |
| GOOGL | Alphabet (YouTube) is a major platform for video influencers, providing monetization opportunities and a large audience. | chat_gpt,claude,twitter |
| META | Meta Platforms (Facebook, Instagram) is a primary platform for influencers to reach their audience and monetize content. | chat_gpt,claude,twitter,google |
| MSFT | Microsoft (LinkedIn) is a platform for professional influencers to share content and grow their network. | chat_gpt,twitter |
| NFLX | Netflix is increasingly collaborating with influencers for content creation and promotion. | chat_gpt |
| PINS | Pinterest is used by influencers to share visual content and drive traffic to their own platforms. | chat_gpt,claude |
| ROKU | Roku provides a platform for video content creators and influencers to reach a broader audience through streaming. | chat_gpt,claude |
| SHOP | Shopify enables influencers to create their own e-commerce stores, capitalizing on their personal brands. | chat_gpt,claude |
| SNAP | Snap Inc. (Snapchat) is popular among younger demographics and influencers, offering unique content creation tools. | chat_gpt,claude |
| SPOT | Spotify is expanding into podcasting, providing a platform for audio influencers to reach their audience. | chat_gpt,claude |
| SQ | Square (Cash App) provides financial tools that influencers use for transactions and monetization. | chat_gpt |
| EB | Eventbrite's event management platform could benefit from influencers hosting workshops, meetups, and other events, giving the company exposure to influencer-driven live experiences. | claude |
| FVRR | Fiverr's freelance marketplace could benefit from influencers offering their services, such as sponsored content creation, positioning the company to capitalize on the influencer gig economy. | claude |
| RBLX | Roblox's gaming platform allows users to create and monetize their own games, attracting gaming influencers and positioning the company to benefit from the influencer-driven gaming trend. | claude |
| SQSP | Squarespace's website builder and e-commerce tools are used by many influencers and content creators, making it a key player in the influencer-driven digital presence market. | claude |
| WIX | Wix's website builder platform enables influencers to create their own websites and portfolios, positioning the company to benefit from the growing influencer economy. | claude |
| AMD |  | twitter |
| IBM |  | twitter |
| INTC |  | twitter |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/influencers/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/influencers" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
