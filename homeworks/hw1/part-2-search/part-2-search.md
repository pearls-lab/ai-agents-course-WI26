---
layout: default
img: LISP.png
img_link: https://xkcd.com/224/
caption: God Created the Universe in LISP 
title: Planning and PDDL
type: in-class
active_tab: homework
release_date:
due_date:
materials:
    - 
        name: hw1
        url: https://github.com/pearls-lab/ai-agents-course-WI26/tree/main/homeworks/hw1
submission_link: https://www.gradescope.com
---

{% if page.materials %}
<div class="alert alert-info">
The materials that you will need for this homework are:
<ul>
{% for item in page.materials %}
<li><a href="{{item.url}}">{{ item.name }}</a></li>
{% endfor %}
</ul>
</div>
{% endif %}

Follow the instruction in the `Search Algorithms for Action Castle.ipynb` file.

### Submission

Please submit your `Search Algorithms for Action Castle.ipynb` file to "HW 1 - Part 2 Search" on [Gradescope]({{page.submission_link}}).

Do not remove `# export` comments. The grading script uses these comments to evaluate your functions. We will NOT audit submissions to add these. If the autograder failes to run due to your modification of these comments, you will not receive credit.
