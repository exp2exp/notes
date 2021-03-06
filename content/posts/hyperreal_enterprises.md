+++
title = "Hyperreal Enterprises: Roadmap"
author = ["Joe Corneli"]
lastmod = 2020-09-12T21:07:42+01:00
slug = "hyperreal_enterprises"
draft = false
+++

## Hyperreal Enterprises: Roadmap {#hyperreal-enterprises-roadmap}


### Introduction {#introduction}


#### We see a massive opportunity that will connect AI and human learning. {#we-see-a-massive-opportunity-that-will-connect-ai-and-human-learning-dot}

We are pursuing a novel programme of technical research and development based on two linked insights:

-   The process of programming can be made more efficient by using AI to automate many tasks; and,
-   People will need to continuously re-skill as technological change accelerates.

Over the last decade, AI systems achieved clear predominance in board games, and made a surprising amount of progress in areas like text processing.  Over the next decade, AI could eat software engineering too. On the way to full-blown AI for programming, we can imagine an AI system that integrates with code editors, issue trackers, Slack, Github, and Stack Exchange — and that supports upskilling, productivity, and automation, all in one platform — significantly augmenting the ability of human programmers.


#### The time is now. {#the-time-is-now-dot}

The basic research agenda was already set by Alan Turing in the late 1940s.  However, it is only recently that we have two necessary assets: massive amounts of relevant data, and the tools needed to process it into a usable form.  Code completion, code generation, and automated testing are already available to software developers.  They represent a variety of partial solutions that suggest that there’s something more substantial here.


#### Open source is the way forward. {#open-source-is-the-way-forward-dot}

Our team brings together applied experience in Natural Language Processing (NLP), computational modelling, reasoning, and natural science.  Having known each other for years, we have banded together around realising serious AI systems.  We see this as a revolutionary task.  Other institutes may be better funded, but our unique experience with building open source products is what’s needed to build a genuinely transformative community around this effort.


#### The steps progress from data, to models, to AI agents. {#the-steps-progress-from-data-to-models-to-ai-agents-dot}

On this blog, we will document our progress.  Presently we are all working on this sub-part-time. Future posts in this series will expand the agenda outlined here, and provide tutorial material that can help turn readers into contributors.

-   Beginning from the data, we plan to use contemporary information extraction methods to derive computationally meaningful material from Stack Exchange Q&A, Github Issues, and programmers’ discussions, along with code. To do this, we will combine general purpose language models, like BERT, and a knowledge graph approach.

-   At this level, we will use category theoretic methods as a glue that can hold together a range of computational models, including models of programs and the process of computer programming. Monocl is an existing process modelling language that has been used to create an abstraction layer over a collection of data science programs. We plan to generalise this considerably.

-   Ultimately we plan to install these models in computational agents who can then “converse with each other to sharpen their wits,” as Turing anticipated, mirroring contemporary developments in self-play.  The design of the agents remains an open issue at the moment.  We are aware of interesting related work in proof generation and program synthesis, but so far this work only addresses part of the problem. We plan to bring in techniques from Bayesian learning, logic programming, and reinforcement learning.


#### This work can contribute significant economic value over reasonably short time scales. {#this-work-can-contribute-significant-economic-value-over-reasonably-short-time-scales-dot}

We will progress by producing ever-better models of human behaviour in computer-mediated communications around technical topics.  We anticipate potential routes-to-market focused on service provision for upskilling, lightweight automation, and support for custom model development.  We speculate that improved learning materials and tools will become the basis for a future community of highly skilled technical workers.

Looking ahead to the next months, we intend to create small demos across the pipeline, following a regular release schedule.  As time goes by, short blog posts will become inputs to research papers and usable tools. We will eventually pursue funding, ideally either in the form of direct revenue or grants, in order to allow us to work full time on these issues.


#### TL;DR {#tl-dr}

We are creating AI tools that will read the things people have written about computer programming and draw on these to find ways that computers can automatically create software.


### Method {#method}

This document synthesises a [Roadmap](http://www.peeragogy.org/pattern-roadmap.html) (more specifically, a [Product Roadmap](http://scrumbook.org/value-stream/product-roadmap.html)) for Hyperreal Enterprises, Ltd.  The Roadmap is being written inside [Org Roam](https://github.com/org-roam/org-roam) (an [Emacs](https://www.gnu.org/software/emacs/) package), and shared via Git on repo.or.cz.  It can be thought of and edited as a wiki, from which other downstream formats can be derived.  (The rest of this section provides technical details that can be skipped on a first read.)


### Setup {#setup}

Install Org Roam if needed (`M-x package-install RET org-roam RET`).

Clone the repo, using these instructions to switch to the mob branch
(which avoids the need for further permissioning). Details are here:
<https://bit.ly/2EQRHEF>

Subsequently, add this to your Emacs configuration:

```elisp
(require 'org-roam)
(setq org-roam-directory (concat "/home/"
                          (getenv "USER")
                          "/arxana/org-roam/"))
(setq org-roam-completion-system 'helm)
(define-key org-roam-mode-map (kbd "C-c n l") #'org-roam)
(define-key org-roam-mode-map (kbd "C-c n f") #'org-roam-find-file)
(define-key org-roam-mode-map (kbd "C-c n b") #'org-roam-switch-to-buffer)
(define-key org-roam-mode-map (kbd "C-c n g") #'org-roam-graph)
(define-key org-mode-map (kbd "C-c n i") #'org-roam-insert)
(org-roam-mode +1)
```


#### <span class="org-todo todo TODO">TODO</span> Update the repo instructions to references to this file {#update-the-repo-instructions-to-references-to-this-file}


### Interaction {#interaction}

Use the `C-c n f` keyboard command to add new disconnected nodes to
the graph, or use `C-c n i` to create a page and insert a wiki-style
link, like `[[New Page]]`. Follow links with `C-c C-o`. Display the
graph structure with `C-c n g`.  It may be necessary to run `M-x
org-roam-db-build-cache` to get the graph to match reality.  Add and
commit new or modified files with git, along with `org-roam.db`, and
push them to the repo.


### Log {#log}

You can review commits to the mob branch here:
<https://repo.or.cz/arxana.git/shortlog/refs/heads/mob>


### Tags {#tags}

Some of the nodes have `#+roam_tags:` set:

| **code** | **meaning**      |
|----------|------------------|
| HL       | High level       |
| CDN      | Can do now       |
| LRD      | Longer R&D cycle |
| HD       | Has dependencies |
| RR       | Research Review  |
| RO       | Research Output  |

Some of the files also have a `#+CATEGORY:` set.


### Pairing {#pairing}

```nil
ssh pair@178.79.174.58
PW: <ASK JOE FOR THE PASSWORD>
emacsclient -a '' -t
M-x lockstep
```


### Linearizing {#linearizing}

To turn this map into something we can reliably use, let’s try to
linearize it.

To downsample from Org Roam (save as `~/bin/roam2org.sh` and make it
executable):

```bash
#! /bin/bash

emacs --batch -l ~/bin/downsample-org-roam.el --eval "(combine-files)" "$@"
```

Here are the working parts (save as `~/bin/downsample-org-roam.el`):

```elisp
(defun downsample ()
  (if (looking-at "^#\\+TITLE:")
      (replace-match "*"))
  (forward-line 1)
  (if (looking-at "^#\\+roam_tags:\\(.*\\)")
      (replace-match ":PROPERTIES:
:tag:\\1
:END:"))
  (while (re-search-forward "^\\*" nil t)
    (replace-match "**"))
  (goto-char (point-min))
  (while (re-search-forward "\\[\\[file:\\([^]]*\\)\\]\\[\\([^]]*\\)\\]\\]" nil t)
    (replace-match "[[*\\2][\\2]]"))
  (buffer-substring-no-properties (point-min) (point-max)))

(defun combine-files (&rest args)
  (apply #'concat
         (mapcar (lambda (file)
                   (save-window-excursion
                     (find-file (concat "~/arxana/org-roam/" file))
                     (let ((contents (buffer-substring-no-properties (point-min)
                                                                     (point-max))))
                       (with-temp-buffer (insert contents)
                                         (goto-char (point-min))
                                         (downsample)))))
                 (or (car args) (nthcdr 5 command-line-args)))))
```


### Backlog {#backlog}

The idea of a backlog is to go from most-doable, starting with work in
progress, to least-doable and potentially vague.  Here, then, is one
possible linearization that may or may not meet that description!

```elisp
(setq files-to-combine
'("hyperreal_enterprises.org"
"top.org"
"organisational_infrastructure.org"
 "discord_server.org"
 "blog.org"
 "obs_recordings.org"
 "code_sharing_platform.org"
"construct_critique_improve_models.org"
 "emacs_hyper_notebook.org"
 "visual_interfaces.org"
 "arxana_2020.org"
"underlying_foundation.org"
 "category_theoretic_glue.org"
 "generating_small_graphs.org"
 "visual_code_walk_through.org"
 "probabilistic_programming_for_scientific_modelling.org"
"technical_experiments_become_easier.org"
 "gpt_trained_on_so_data.org"
 "display_so_with_similarity_graph.org"
 "recommender_system.org"
"which_model_construction_process_works_as_a_whole.org"
 "information_extraction_from_so_q_a_items.org"
 "knowledge_graph.org"
"why_not_what.org"
 "teach_basic_coding.org"
"for_the_sake_of_advancing_ai.org"
 "production_system.org"
 "agent_model.org"
"data_course.org"
"business_development.org"
 "paperspace_do_nj_etc_collaboratory.org"
"research_outputs.org"
 "advances_in_tutoring_systems_for_programming.org"
 "advances_in_knowledge_mining_from_technical_documents.org"
 "an_abm_of_the_computer_programming_domain.org"
"bottom.org"))
```

To combine the files, run:

```elisp
(combine-files files-to-combine)
```

To get the indicative nesting (shown by spaces above) at the org level, run:

```elisp
(org-map-entries (lambda ()
                   ;; don’t demote the top level items and their sub-items
                   (if (string= (org-entry-get nil "tag") "HL")
                       (progn (org-end-of-subtree)
                              (setq org-map-continue-from (point)))
                     ;; demote everything else
                     (org-do-demote)))
                 nil 'file)
```


### Reviewing progress {#reviewing-progress}

Something like the following should be all that’s get a high-level
overview of progress on active tasks, sourcing information directly
from the Org Roam files.  Add the following to your emacs
initialisation script (e.g., `~/.emacs`), evaluate it, and then run
`C-c r` to load up the fun.  This may not be the perfect presentation
yet but it gives an idea.

```elisp
(setq org-todo-keywords
      '((sequence "TODO" "STARTED" "BLOCKED" "|" "DONE" "DEFERRED")))

(setq org-agenda-sorting-strategy '((todo todo-state-down category-down)))

(setq org-agenda-files '("~/arxana/org-roam/"))

(defun org-scrum-board ()
  (interactive)
  (org-todo-list "TODO|STARTED|BLOCKED|DONE|DEFERRED"))

(global-set-key (kbd "C-c r") 'org-scrum-board)
```


### Next Steps {#next-steps}


#### <span class="org-todo todo TODO">TODO</span> Package downsamping code separately {#package-downsamping-code-separately}


### Subgoals: {#subgoals}

-   [Top]({{< relref "top" >}})
