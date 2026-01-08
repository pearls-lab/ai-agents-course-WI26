---
title: CSE 291A - AI Agents - UCSD CSE
layout: default
img: # heroes_journey.png
active_tab: main_page 
---

<!-- Display an alert about upcoming homework assignments -->
{% capture now %}{{'now' | date: '%s'}}{% endcapture %}
{% for page in site.pages %}
{% if page.release_date and page.due_date %}
{% capture release_date %}{{page.release_date | date: '%s'}}{% endcapture %}
{% capture due_date %}{{page.due_date | date: '%s'}}{% endcapture %}
{% if release_date < now and due_date >= now %}
{% if page.type == "in-class" %}
<!-- In class activity -->
<div class="alert alert-danger">
The in-class activity for {{ page.release_date | date: "%A %b %-d" }} will be to <a href="{{page.url}}">{{ page.title }}</a>.  
</div>
<!-- Other participation activity -->
{% elsif page.type == "participation" %}
<div class="alert alert-info">
The participation activity <a href="{{page.url}}">{{ page.title }}</a> is due on {{ page.due_date | date: "%A, %B %-d, %Y" }} before {{ page.due_date | date: "%I:%M%p" }}. 
</div>
{% else %}
<!-- Homework assignment -->
<div class="alert alert-success">
<a href="{{page.url}}">{{page.type}} {{page.number}}: {{page.title}}</a> has been released.  
{% if page.deliverables %}
The assignment has multiple deliverables.
<ul>
{% for deliverable in page.deliverables %}
<li>{{ deliverable.due_date | date: "%b %-d, %Y" }} - {{deliverable.description}}.</li>
{% endfor %}
</ul>
{% else %}
It is due before {{ page.due_date | date: "%I:%M%p" }} on {{ page.due_date | date: "%A, %B %-d, %Y" }}.
{% endif %}
</div>
{% endif %}
{% endif %}
{% endif %}
{% endfor %}
<!-- End alert for upcoming homework assignments -->


<!--
<div class="alert alert-success" markdown="1">
A great example of what you could build if you take this class is the [AI Dungeon](https://play.aidungeon.io/), which is an interactive fiction game  that was developed by a student at BYU using [Open AI's GPT-2](https://openai.com/blog/better-language-models/) large scale language model.
</div>
-->
<!--
<div class="alert alert-success" markdown="1">
First day of class is Thursday, January 13, 2022 at 1:45pm-3:15pm Eastern. It will take place virtually. Here is the [Zoom link](https://upenn.zoom.us/j/95868341588?pwd=a0NvbkhtUEdYTTk5d0Vmc2VvcHJrUT09). We look forward to seeing you there!
</div>
-->

# Course number: CSE 291A - AI Agents

### Course Description
This course will cover the basics of (1) what LLM-based AI Agents actually are; (2) where they can be useful (and where they are not); and (3) how to safely train and deploy an agent for a given virtual domain.

#### Rough Outline

- What are agents? Starting in the 70s to today
- Simulation environments, how they are built
- Search / Planning in simulations
- Monte Carlo Methods
- Basics of Deep RL
- LLM Basics
- Deep RL for language agents
- Other LLM Agents methods – tool use, prompting
- Human AI Collab Basics
- Agent Safety


### Required Knowledge 
Students should be familiar with basic CS concepts such as Search (A*, Monte Carlo Tree Search) and Deep Learning concepts such as Transformers (how self-attention works) and the basics of how Large Language Models are (pre-)trained. Students are expected to come into the class with the ability to implement these concepts from scratch (in Python/numpy) and also be able to use popular libraries such as Huggingface. Basic knowledge of Reinforcement Learning (what is a Markov Decision Process, differences between online and offline RL, RL from Human Feedback) is a plus but not required.

#### Recommended Preparation for Those Without Required Knowledge
Undergrad Intro to AI/RL, and grad level Intro to Deep Learning / NLP types of courses are highly recommended

#### Website [pearls-lab.github.io/ai-agents-course-WI26](http://pearls-lab.github.io/ai-agents-course-WI26)

#### Instructors: [Prithviraj Ammanabrolu](https://prithvirajva.com)

#### TAs: [Bosung Kim](https://bosung.github.io), [Christopher Cui](https://christopherzc.github.io)

#### Time and Place
- Winter 2026, Tuesdays & Thursdays from 3:30 to 4:50 pm PT at CENTR 214
- First day of class is January 06, 2026
- Last day of class is March 12, 2026

Office Hours (see the [Staff]({{ site.baseurl }}/staff) page for office hour locations)

### Course Materials
There is no textbook for this course, but you will be required to puchase a varitey of materials including software and API credits. If any of these are prohibitively expensive for your budget, please let the instructor know.

<!-- Games
: [Labyrinth The Adventure Game](https://www.amazon.com/Jim-Hensons-Labyrinth-Adv-Game/dp/1916011551/) - $35 on Amazon
: [Action Castle](http://www.memento-mori.com/pdf/parsely-preview-n-play-edition) - Free (you can optionally buy it in the rad [Parsley book in print](http://www.memento-mori.com/books/parsely-book) or [PDF](http://www.memento-mori.com/pdf/parsely-pdf)) - $20-30 -->


<!-- Materials 
: [ChatGPT Plus subcription](http://chat.openai.com) - $20/month -->


## Grading

- 40% - 4 Homeworks (including HW 0) - to be done individually
- 40% - Final Project – to be in groups of ~5
- 20% - Class participation - attendence and paper presentations


### Paper Presentations
Over the course of the semester, as part of the class participation each final project group must prepare one or more ~15-20 minute presentations on a research paper relevant to the course. Since these presentation will be a substantial component of the learning experience in the class, slides must be prepared and emailed to us at least 72 hours in advance of the lecture they will be presented in (e.g., by 3PM on the Monday before the presenation date), so that we can provide feedback on them. Failure to send us the slides ahead of time will result in a grade penalty on the presentation. 

### Collaboration Policy
Homeworks are expected to be done individually, and teams of ~5 are needed for the final project.

### LLM Use Policy
You may use LLMs for code completion on coding assignments but must submit a CREDITS.txt file noting the exact LLM you used along with prompt.
All homeworks will also require explanations written of the code which must be done solely without an LLM.
Writing on final projects can be edited but not entirely written with an LLM.
Failure to comply with any of these policies will result in a 0 on that particular assignment.

### Late Day Policy
Each student has five free "late days". Homeworks can be submitted at most two days late. If you are out of late days, then you will not be able to get credit for subsequent late assignments. One "day" is defined as anytime between 1 second and 24 hours after the homework deadline. The intent of the late day policy it to allow you to take extra time due to unforseen circumstances like illnesses or family emergencies, and for forseeable interruptions like on campus interviewing and religious holidays.  You do not need to ask permission to use your late days.  No additional late days are granted. **Late days only apply to the homeworks. They cannot be used on the final project, which must be finished by the final day of class.  Late days may not be used for paper presentations.**
