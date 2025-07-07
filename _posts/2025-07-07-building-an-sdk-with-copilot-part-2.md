---
title: "Part 2: OAuth? How hard can that be? (SDK with Copilot Series)"
date: 2025-07-07T21:16:12+01:00
description: "The second video is this streaming series where I lean into Copilot (without falling over, I hope)."
categories:
  - coding
tags:
  - ai
  - php
  - zoho-bigin
# header:
#  video:
#    id: RxZmLM-dE0w
#    provider: youtube
---

After [episode one](/coding/building-an-sdk-with-copilot/) in the series I've not got into some technical parts of setting up OAuth with the library.

I'm continuing to learn more about what Copilot can do — and what it thinks it can, but really can't!

{% include video id="kStbrkRmHgQ" provider="youtube" %}

I also found that the [Zoho Bigin API](https://www.bigin.com/developer/docs/apis/v2/) doesn't do OAuth in the most secure way. Some of the token parameters are sent via query string in the authentication process. This is not ideal (even if running over HTTPS). Tokens in URLs can be logged by:

* Server logs
* Browser history
* Proxy and CDN logs
* Referrer headers if the user clicks a link from the page.

In addtion URLs have length limits in some systems, risking truncation.

Always keep private data out of the query string and send it via POST payloads for security.
