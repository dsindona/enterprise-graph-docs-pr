---
title: Using Conversational AI with Enterprise Graph by Microsoft
description: Learn how to use conversational AI with Enterprise Graph by Microsoft
author: sramesh

ms.service: enterprise-graph
ms.topic: tutorial
ms.date: 07/02/2019
ms.author: sramesh
---

# Tutorial: Build Language Models 

In this tutorial, you'll learn to:

> * Rank interpretations 
> * Annotate an utterance
> * Update the language models 


## Prerequisites

- Have completed all the essential steps to build the graph.

## Introduction

The Conversational AI tool, part of Microsoft Enterprise Graph lets users write natural language queries to create and annotate the language models. Annotating means that users can interpret and improve the result of a given query through continual feedback. This document will describe the Conversational AI tool�s main functions. 


The tool is found in the Conversational AI section, pictured below: 

![Location](media/conversationalai-tooling/conversationalai-location.png)

## Language Models

The tool assumes that you already have an ontology and data in place. Behind the scenes, the Conversational AI tool builds language models on top of the ontology. Language models are a set of generated rules that are used to interpret natural language queries. Users can generate the baseline language model by clicking the Bootstrap button.

![Bootstrap](media/conversationalai-tooling/bootstrapping.png)

The language models won't be perfect out of the box and must be improved. The process of improvements is the Annotations aspect of the tool, detailed below. 

## Annotations

Within Annotations, there are two sections: Query Plan Review and Query Plan Tagging. 

### Query Plan Review 

The goal of this section is to help the Conversational AI tool understand the best interpretation of a natural language query. The basic steps are as follows: When a user enters in a query, the result will be several visual interpretations in the order of confidence. The user has the option to rate the interpretations so that the tool can improve its ranking order. 

![OriginalInterprets](media/conversationalai-tooling/interpretations.png)

The interpretations are ordered from most confident to least confident. If there are multiple interpretations, users can judge the interpretations as Perfect, Good, Fair, Bad, or Not Judged. Once the user judges the interpretation, the tool will incorporate the feedback, rerun the query, and provide an updated order of visual interpretations. In this example, the #2 interpretation looks better than the #1 interpretation. California is being seen as a city in the #1 interpretation, and as a state in the #2 interpretation. In this case, the second interpretation is more reasonable. 

By labeling the #1 interpretation as bad and #2 as good, the language models will update and reorder the results.

![GoodInterprets](media/conversationalai-tooling/goodinterpret.png)

###  Query Plan Tagging

There will be queries that the tool does not completely understand, due to the language models missing some type of information. In these instances, users can annotate on a query. The following sections will walk through the process of annotating on queries. To further understand the different annotation types, please review the **Annotations in Conversational AI document**.

In this example, the word �leads� needs to be classified as a synonym of �customers�, which is where the tool can help. 

![GoodInterprets2](media/conversationalai-tooling/unknowntermleads.png)

After clicking on Query Tagging, users can click one or multiple terms in the query and assign them to a part of the ontology. �Leads� needs to be annotated. When the user clicks on �leads�, the Entity Tag Operation automatically opens. 

![Options](media/conversationalai-tooling/taggingoptions.png)

Because �leads� is an entity, the Annotation Type is Entity. In the ontology, there is an entity type for customers, which is what the user finds and selects. The image below shows this operation. 

![Options2](media/conversationalai-tooling/leadstocustomers.PNG)

After selecting the operation, the user can update the model, and the query will rerun. 

![NewInterpret](media/conversationalai-tooling/newinterpret.png)

In summary, we taught the tool to recognize �leads� as a synonym for �customers�. 

The original interpretation was: 

![GoodInterprets2](media/conversationalai-tooling/unknowntermleads.png)

The new interpretation is: 

![NewInterpret](media/conversationalai-tooling/newinterpret.png)

Finally, the tool tracks the precision of the different queries run in the instance. Users can use this feature to track how the Conversational AI is improving. 

## Conclusion

The Conversational AI tooling provides a visual, interpretable mechanism to interpret and improve natural language queries. 