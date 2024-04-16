---
title: 'Horcrux: Automatic JavaScript Parallelism for Resource-Efficient Web Computation'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - Shaghayegh Mardani
  - admin
  - Ronny Ko
  - Harsha V. Madhyastha
  - Ravi Netravali

# Author notes (optional)
# author_notes:
#   - 'Equal contribution'
#   - 'Equal contribution'

date: '2021-07-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2021-07-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *OSDI'21*
publication_short: In <b>*OSDI'21*</b>

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
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://www.usenix.org/system/files/osdi21-mardani.pdf'
url_code: 'https://github.com/ShaghayeghMrdn/horcrux-osdi21'
# url_dataset: 'https://www.github.com/goelayu/Jawa.git'
# url_poster: 'https://goelayu.github.io/files/jawa-poster.pdf'
url_project: ''
url_slides: 'https://www.usenix.org/system/files/osdi21_slides_mardani.pdf'
# url_source: 'https://webresearch.eecs.umich.edu/jawa/f'
# url_video: 'https://www.youtube.com/watch?v=WdxWpGJ-gUs'

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

Web pages today commonly include large amounts of
JavaScript code in order to offer users a dynamic experience.
These scripts often make pages slow to load, partly due to a
fundamental inefficiency in how browsers process JavaScript
content: browsers make it easy for web developers to reason
about page state by serially executing all scripts on any frame
in a page, but as a result, fail to leverage the multiple CPU
cores that are readily available even on low-end phones.
In this paper, we show how to address this inefficiency
without requiring pages to be rewritten or browsers to be
modified. The key to our solution, Horcrux, is to account
for the non-determinism intrinsic to web page loads and
the constraints placed by the browser’s API for parallelism.
Horcrux-compliant web servers perform offline analysis of
all the JavaScript code on any frame they serve to conservatively identify, for every JavaScript function, the union of the
page state that the function could access across all loads of
that page. Horcrux’s JavaScript scheduler then uses this information to judiciously parallelize JavaScript execution on
the client-side so that the end-state is identical to that of a serial execution, while minimizing coordination and offloading
overheads. Across a wide range of pages, phones, and mobile networks covering web workloads in both developed and
emerging regions, Horcrux reduces median browser computation delays by 31-44% and page load times by 18-37%.