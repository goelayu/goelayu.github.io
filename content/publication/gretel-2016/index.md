---
title: 'Gretel: Lightweight Fault Localization for Openstack'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Sukrit Kalra
  - Mohan Dhawan

# Author notes (optional)
author_notes:
  - 'Equal contribution'
  - 'Equal contribution'

date: '2016-12-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2016-12-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *CoNEXT'16*
publication_short: In <b>*CoNEXT'16*</b>

# abstract: Crawling the web at scale forms the basis of many important systems web search engines, smart assistants, generative AI, web archives, and so on. Yet, the research community
# has paid little attention to this workload in the last decade. In
# this paper, we highlight the need to revisit the notion that web
# crawling is a solved problem. Specifically, to discover and fetch
# all page resources dependent on JavaScript and modern web
# APIs, crawlers today have to employ compute-intensive web
# browsers. This significantly inflates the scale of the infrastructure necessary to crawl pages at high throughput.
# To make web crawling more efficient without any loss of
# fidelity, we present Sprinter, which combines browser-based
# and browserless crawling to get the best of both. The key to
# Sprinter’s design is our observation that crawling workloads
# typically include many pages per site and, unlike in traditional
# user-facing page loads, there is significant potential to reuse
# client-side computations across pages. Taking advantage of this
# property, Sprinter crawls a small, carefully chosen, subset of
# pages on each site using a browser, and then efficiently identifies
# and exploits opportunities to reuse the browser’s computations
# on other pages. Sprinter was able to crawl a corpus of 50,000
# pages 5x faster than browser-based crawling, while still closely
# matching a browser in the set of resources fetched.

# Summary. An optional shortened abstract.
# summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags: []

# Display this page in the Featured widget?
featured: false

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'uploads/gretel.pdf'
# url_code: 'https://github.com/goelayu/Sprinter'
# url_dataset: 'https://github.com/goelayu/Sprinter'
url_poster: ''
url_project: ''
# url_slides: ''
# url_source: 'uploads/sprinter-2024.pdf'
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
  focal_point: ''
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
# projects:
#   - example

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
# slides: example
---

<!-- {{% callout note %}}
Click the _Cite_ button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}} -->

<!-- {{% callout note %}}
Create your slides in Markdown - click the _Slides_ button to check out the example.
{{% /callout %}} -->

Like any other distributed system, cloud management stacks
such as OpenStack, are susceptible to faults whose root
cause is often hard to diagnose and may take hours or days
to fix. We present GRETEL, a system that leverages nonintrusive system monitoring, to expedite root cause analysis
of both operational and performance faults manifesting in
OpenStack operations. GRETEL uses unique operational
fingerprints to quickly identify faulty operations at runtime.
GRETEL is accurate in its diagnosis, and achieves >98%
precision in identifying the faulty operation with very few
false positives even under conditions of stress. GRETEL is
lightweight and orders of magnitude faster than prior work,
sustaining a throughput of ∼77 Mbps.