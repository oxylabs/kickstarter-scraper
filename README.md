# Kickstarter Scraper API

[![Oxylabs promo code](https://user-images.githubusercontent.com/129506779/250792357-8289e25e-9c36-4dc0-a5e2-2706db797bb5.png)](https://oxylabs.go2cloud.org/aff_c?offer_id=7&aff_id=877&url_id=112)

Oxylabs’ [Kickstarter Scraper](https://oxylabs.io/products/scraper-api/web/kickstarter?utm_source=github&utm_medium=repositories&utm_campaign=product) is a data gathering solution allowing you to extract real-time information from an Kickstarter website effortlessly. This brief guide explains how an Kickstarter Scraper works and provides code examples to understand better how you can use it hassle-free.

### How it works

You can get Kickstarter results by providing your own URLs to our service. We can return the HTML for any Kickstarter page you like.

#### Python code example

The example below illustrates how you can get HTML of Kickstarter page.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal',
    'url': 'https://www.kickstarter.com/design-tech?ref=section-homepage-nav-click-design-tech'
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```
Find code examples for other programming languages [**here**](https://github.com/oxylabs/kickstarter-scraper/tree/main/code%20examples)

#### Output Example
```json
{
  "results": [
    {
      "content": "<!DOCTYPE html>\n<html class=\"pages_show fontface no-js\" data-request-id=\"3ad6b269-c0e3-4cb5-9462-6de ... </html>",
      "created_at": "2023-12-18 11:14:51",
      "updated_at": "2023-12-18 11:14:53",
      "page": 1,
      "url": "https://www.kickstarter.com/design-tech?ref=section-homepage-nav-click-design-tech",
      "job_id": "7142472277798496257",
      "status_code": 200
    }
  ]
}
```
With our Kickstarter Scraper, you can effortlessly extract public data from any Kickstarter web page. This includes gathering essential campaign information such as funding goal, backers' data, updates, and comments to strategically understand market trends and get a leg up on your competitors. If you need any help, don't hesitate to reach out to our support team via live chat or email us at hello@oxylabs.io.