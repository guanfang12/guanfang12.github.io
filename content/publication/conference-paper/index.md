---
title: '
Fine-Grained Cross-View Geo-Localization Using a Correlation-Aware Homography Estimator'

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors: 
  - admin
  - Runsen Xu
  - Zuofan Cui
  - Zeyu Wan
  - Yu Zhang

# Author notes (optional)
author_notes:
  - 
  - 
  -
  -
  - Corresponding author.

date: '2023-09-21T00:00:00Z'
doi: ''

# Schedule page publish date (NOT publication's date).
publishDate: '2023-01-01T00:00:00Z'

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ['1']

# Publication name and optional abbreviated publication name.
publication: Neural Information Processing Systems, NeurIPS 2023
publication_short: Neural Information Processing Systems, NeurIPS 2023

abstract: Accurately localizing ground cameras is crucial for applications like autonomous driving and geospatial analysis. Current works focus on comparing features extracted from ground and satellite images to estimate the ground camera's 3-DoF pose (GPS location and orientation). However, they often involve significant time or space complexity due to the need to traverse candidate poses or generate multiple possible pose representations simultaneously. We propose to align a warped ground image with a corresponding GPS-tagged satellite image covering the same area using homography estimation. We leverage a differentiable spherical transform module to project ground images onto an aerial perspective, simplifying the problem to 2D image alignment. We introduce a correlation-aware homography estimation method to attain sub-pixel resolution and meter-level localization accuracy and achieve real-time performance at 30 FPS. Extensive experiments demonstrate significant improvements over previous state-of-the-arts, reducing the mean metric localization error by 21.3\% and 34.4\% in same-area generalization tasks on the VIGOR and KITTI benchmark, respectively.


# Summary. An optional shortened abstract.
summary: Reducing the cross-view geo-localization problem to a 2D image alignment problem by utilizing BEV transformation, and completing the alignment process with a correlation-aware homography estimator.

tags: []

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: 'https://arxiv.org/pdf/2308.16906.pdf'
url_code: 'https://github.com/xlwangDev/HC-Net'
# url_dataset: 'https://github.com/wowchemy/wowchemy-hugo-themes'
# url_poster: ''
# url_project: ''
# url_slides: ''
# url_source: 'https://github.com/wowchemy/wowchemy-hugo-themes'
# url_video: 'https://youtube.com'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  # caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
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
{{% /callout %}}

{{% callout note %}}
Create your slides in Markdown - click the _Slides_ button to check out the example.
{{% /callout %}}

Supplementary notes can be added here, including [code, math, and images](https://wowchemy.com/docs/writing-markdown-latex/). -->
