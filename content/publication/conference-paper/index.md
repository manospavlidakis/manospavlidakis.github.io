---
title: 'Guardian: Data Isolation for Multi-Tenant GPU Sharing'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin
  - Giorgos Vasiliadis
  - Stelios Mavridis
  - Antony Chazapis
  - Angelos Bilas

# Author notes (optional)
#author_notes:
#  - 'Equal contribution'
#  - 'Equal contribution'

date: ''
doi: ''

# Schedule page publish date (NOT publication's date).
#publishDate: '2017-01-01T00:00:00Z'
publishDate: ''

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.
publication_types: ['paper-conference']

# Publication name and optional abbreviated publication name.
publication: *under submission*
#publication_short: In *ICW*

abstract:Modern applications, such as machine learning frameworks, can only partially utilize beefy GPUs, leading to GPU underutilization in cloud environments. Sharing GPUs across multiple applications from different users can improve resource utilization and consequently cost, energy, and power efficiency. However, GPU sharing creates memory safety concerns because kernels need to share a single GPU address space (common GPU context). Previous GPU memory protection approaches have limited deployability because they require specialized hardware extensions or source code, which is not available in GPU-accelerated libraries heavily used from ML frameworks. 

In this paper, we present Guardian, a PTX-level bound checking approach for GPUs that limits GPU kernels of each application to stay within the memory partition allocated to them. Guardian relies on three mechanisms: (1) It divides the common GPU address space into separate partitions for different applications. (2) It intercepts and checks data transfers, fencing erroneous operations. (3) It instruments all GPU kernels at the PTX level –available in closed GPU libraries– fencing all kernel memory accesses outside application memory bounds. We implement Guardian as an external, dynamically linked library that can be pre-loaded at application startup time. Guardian’s approach is transparent to applications and can support real-life, complex frameworks, such as Caffe and PyTorch, that issue billions of GPU kernels. Our evaluation show that the overhead of Guardian for such frameworks is between 4% and 12% (on average 9%), compared to native. 

# Summary. An optional shortened abstract.
#summary: Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis posuere tellus ac convallis placerat. Proin tincidunt magna sed ex sollicitudin condimentum.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
#  focal_point: ''
#  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
  - example

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: example
---

{{% callout note %}}
Click the _Cite_ button above to demo the feature to enable visitors to import publication metadata into their reference management software.
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the _Slides_ button to check out the example.
{{% /callout %}}

Add the publication's **full text** or **supplementary notes** here. You can use rich formatting such as including [code, math, and images](https://docs.hugoblox.com/content/writing-markdown-latex/).
