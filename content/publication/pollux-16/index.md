---
title: 'POLLUX: Safely Upgrading Dependent Application Libraries'

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

date: '2016-03-01T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2016-03-01T00:00:00Z'

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: In *FSE'16*
publication_short: In <b>*FSE'16*</b>

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

url_pdf: 'uploads/pollux.pdf'
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

Software evolution in third-party libraries across version upgrades
can result in addition of new functionalities or change in existing
APIs. As a result, there is a real danger of impairment of
backward compatibility. Application developers, therefore, must
keep constant vigil over library enhancements to ensure application
consistency, i.e., application retains its semantic behavior across
library upgrades. In this paper, we present the design and
implementation of POLLUX, a framework to detect applicationaffecting changes across two versions of the same dependent nonadversarial library binary, and provide feedback on whether the
application developer should link to the newer version or not.
POLLUX leverages relevant application test cases to drive execution
through both versions of the concerned library binary, records
all concrete effects on the environment, and compares them to
determine semantic similarity across the same API invocation for
the two library versions. Our evaluation with 16 popular, opensource library binaries shows that POLLUX is accurate with no false
positives and works across compiler optimizations.