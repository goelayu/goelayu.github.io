---
title: 'Overcoming Barriers to Information Exchange on the
Web'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin

# Author notes (optional)
# author_notes:
#   - 'Equal contribution'
#   - 'Equal contribution'

date: '2023-10-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2023-10-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['thesis']

# Publication name and optional abbreviated publication name.
publication: <b> Ph.D. Dissertation</b>
# publication_short: In <b>*NSDI'24*</b>

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

url_pdf: ''
url_code: ''
url_dataset: ''
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

We are increasingly relying on the internet and specifically the world wide web (WWW) to
exchange information and access services. Despite its ubiquitous use, there are two key
barriers to accessing information that is shared on the web: 1) Many web pages suffer from
poor performance with respect to both end-user loading latency and crawling throughput as
observed by large-scale web crawlers. 2) Many web pages cease to exist over time causing a
significant fraction of published information to no longer be available.
My dissertation addresses these issues by employing fine-grained data-flow and controlflow analysis of web computations, specifically JavaScript execution. Using this analysis, I am
able to extract and modify JavaScript runtime behavior during web page loads and leverage
this ability to build a number of web systems. First, I propose a client-side computation
caching system that stores results of JavaScript (JS) execution to reduce compute delays
and improve web page load times. I show that up to 85% of JavaScript runtime can be
skipped by using such a computation cache. Second, I demonstrate that legacy JavaScript
code has untapped potential for parallelization across multiple cores of modern smartphones
to improve page load times. I show that 88% speedup in JS execution can be achieved
by parallelizing execution on 8 cores of a given mobile device. Third, I built Sprinter, a
distributed web crawler that crawls the web at 5 times the rate of traditional browser-based
crawlers while preserving perfect fidelity. Sprinter accomplishes this by carefully selecting a
subset of pages on any site to be crawled which it crawls using a browser, and caches the
corresponding compute. It then performs browser-less crawling of the remaining pages on
that site using those cached computations. Finally, I built Jawa, a web archival crawler that
reduces the storage overhead of web archives by 41% while eliminating all fidelity issues.
Jawa accomplishes this by exploiting the differences between live and archived pages, and
accurately identifying and patching the sources of non-determinism that impair JavaScript
execution on archived pages