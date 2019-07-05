# Digest generator tool

This application allows to add links to chapters (digest articles) and generate output markup by targets using templates.

ToDo: Add to readme how to install, run etc.

# Common idea and entities

## Common configuration

**name** - name of the digest. This name will be used in episode titles. Example: "MODX Digest".

## Episode

Episode is finished list of links for specified date range. 

**number** - number of episode, usually from 1 to infinite
**from** - start date in date range
**till** - end date in date range
**description** - short custom description of this episode. Should be translatable.
**cover** - cover image. Optional.

## Section

Section is logical part of episode. Sections common for all episodes, but can be skipped in case no links attached to them.

**title** - title or name of section
**order** - order of section, which first and which last.

## Link

Link is basic element of digest. Link means piece of information with description and refferes to external page with full information.

**uri** - link to the article, should be unique to avoid duplicates or at leas, validate and warn when links already exists in storage.
**created** - when link was added. Important field that can be automated but by this field links should be attached to the episode. Also, will be used for sorting.
**title** - title of link. 
**description** - custom description of the link. Auhtor's work.
**section** - section of the digest for attaching link. Example: events, addons, articles, github.
**language** - language of link target (article).

## Target

Target is a place or service where episode is going to be published. Examples: modx.pro, habr.com. Goal of targets provide custom handlers and templates for managing output of each episode. Each episode should be compiled via target. 

Todo: render also fit.

**name** - name of target.
**template** - path to file with a template.


