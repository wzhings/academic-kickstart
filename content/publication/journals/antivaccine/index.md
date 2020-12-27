+++
title = "Detecting Medical Misinformation on Social Media Using Multimodal Deep Learning"
date = 2020-11-10

# Authors. Comma separated list, e.g. `["Bob Smith", "David Jones"]`.
authors = ["**Zuhui Wang**", "Zhaozheng Yin", "Young Anna Argyris"]

# Publication type.
# Legend:
# 0 = Uncategorized
# 1 = Conference paper
# 2 = Journal article
# 3 = Preprint / Working Paper
# 4 = Report
# 5 = Book
# 6 = Book section
# 7 = Thesis
# 8 = Patent
publication_types = ["2"]

# Publication name and optional abbreviated version.
publication = "IEEE journal of biomedical and health informatics"
publication_short = ""

# Abstract.
abstract = ""

# Summary. An optional shortened abstract.
summary = ""

# Digital Object Identifier (DOI)
doi = "10.1109/JBHI.2020.3037027"

# Is this a featured publication? (true/false)
featured = false

# Tags (optional).
#   Set `tags = []` for no tags, or use the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = ["Deep Learning", "Multimedia", "Multimodal", "Antivaccine"]

# Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["deep-learning"]` references 
#   `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects = ["antivaccine"]

# Slides (optional).
#   Associate this page with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references 
#   `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides = ""

# Links (optional).
url_pdf = "https://arxiv.org/submit/3533718/view"
url_code = "https://github.com/wzhings/antivaccine_detection.git"
url_dataset = ""
url_project = ""
url_slides = ""
url_video = ""
url_poster = ""
url_source = ""

image_prevew = ""

# Custom links (optional).
#   Uncomment line below to enable. For multiple links, use the form `[{...}, {...}, {...}]`.
# links = [{name = "Custom Link", url = "http://example.org"}]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Smart"
+++

### Abstract

In 2019, outbreaks of vaccine-preventable diseases reached the highest number in the US since 1992. Medical misinformation, such as antivaccine content propagating through social media, is associated with increases in vaccine delay and refusal. Our overall goal is to develop an automatic detector for antivaccine messages to counteract the negative impact that antivaccine messages have on the public health. Very few extant detection systems have considered multimodality of social media posts (images, texts, and hashtags), and instead focus on
textual components, despite the rapid growth of photo-sharing applications (e.g., Instagram). As a result, existing systems are not sufficient for detecting antivaccine messages with heavy visual components (e.g., images) posted on these newer platforms. To solve this problem, we propose a deep learning network that leverages both visual and textual information. A new semanticand task-level attention mechanism was created to help our model to focus on the essential contents of a post that signal antivaccine messages. The proposed model, which consists of three branches, can generate comprehensive fused features for predictions. Moreover, an ensemble method is proposed to further improve the final prediction accuracy. To evaluate the proposed model’s performance, a real-world social media dataset that consists of more than 30,000 samples was collected from Instagram between January 2016 and October 2019. Our 30 experiment results demonstrate that the final network achieves above 97% testing accuracy and outperforms other relevant models, demonstrating that it can detect a large amount of antivaccine messages posted daily. 