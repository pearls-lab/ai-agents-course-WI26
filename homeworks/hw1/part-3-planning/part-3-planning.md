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

This HW will look at a classical planning algorithms that use a language for defining plans called PDDL (Planning Domain Definition Language).  PDDL and classic planning are all defined in the Russell and Norvig textbook AI A Modern Approach, in chapter 11.  I also recommend this tutorial by Kory Becker: [Artificial Intelligence Planning with STRIPS, A Gentle Introduction](http://www.primaryobjects.com/2015/11/06/artificial-intelligence-planning-with-strips-a-gentle-introduction/).  She has an [online demo](https://stripsfiddle.herokuapp.com) that lets you upload your own PDDL-specified problems, and find solutions to them.  


We will use this Python library:
* [PDDL Parser](https://github.com/pucrs-automated-planning/pddl-parser)

In PDDL, we can define **action schema** to represent actions.  Here is an example of an action schema for flying a plane from one location to another: 
```
(:action fly
     :parameters (?p - plane ?from - airport ?to - airport)
     :precondition (and (plane ?p) (airport ?from) (airport ?to) (at ?p ?from))
     :effect (and (at ?p ?to)) (not (at ?p ?from)))
)
```

This defines an action called **fly**, which takes 3 arguments: a plane **p**, a starting airport **from** and a destination airport **to**.  In order for this action to be applied, several *preonditions* must be satisified:
1. **p** must be a plane
2. **from** must be be an airport
3. **to** must be be an airport
4. **p** must initially be located at **from**.



Once the action is applied, then it has the *effect* of changing several states in the world.
1. **p** is no longer located at **from** 
1. **p** is now located at **to** 

In general, a schema consists of:
* an action name
* a list of all the variables use in the schema
* a precondition - a conjunction of literals (positive or negated atomic logical sentences)
* an effect - a conjunction of literals

_Note: The enforcement of argument types like `(plane ?p)` can be left out of the action schema if we specify types in the domain PDDL file._


### What to do 

1. Open [{{page.materials[0].name}}]({{page.materials[0].url}}).
2. Unzip it (or `git clone`)
3. open hw1/part-3-planning/planning.ipynb
4. Create pairs of PDDL files for the following problems:
* `move-item-to-location`
* `go-fishing`
* `feed-troll`

If you've got extra time, you're welcome to work on PDDL definitions for other parts of the Action Castle game.

Please submit your `planning.ipynb` file to "HW 1 - Part 3 Planning" on the [Gradescope]({{page.submission_link}}). 
