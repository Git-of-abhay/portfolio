---
layout: post
title: "How I use AI agents as an engineering organization"
description: "My workflow with AO, Hermes, and multiple models for delegating focused work while keeping product direction and quality in my hands."
date: 2026-09-23
---

I like building ambitious things, but a single person still has only so much time and attention. I use AI agents as a small, on-demand engineering organization: I decide what needs to exist, break it into clear jobs, and let different agents and models work on the parts they are suited to. The point is to get to a useful result while keeping the decisions and final quality under my control.

## I start with an outcome, not a vague prompt

Before delegating, I try to define what the work should produce: a working feature, a tested API, a design exploration, or a reviewable change. I give each task its own scope, relevant context, and a way to check whether it is done. When the task is still fuzzy, I use an agent to explore options and trade-offs before asking another to implement.

## AO gives the work a structure

I use AO (Agent Orchestrator) to keep parallel coding work visible. Its separate worker sessions and workspaces make it easier to split a larger goal into focused jobs and inspect what each agent changed. I can see work moving through implementation, review, and follow-up instead of trying to remember which terminal or chat owns which part.

That separation matters when more than one model is involved. A UI task, an API task, and a testing task can move independently, but they still need one product direction and a deliberate integration step.

## Hermes is part of my delegation workflow

I also use Hermes as an assistant for working with agents and models. I use the combination of Hermes and AO to delegate, keep track of progress, and ask for the work I need when I need it. I do not expect one model to be best at every kind of problem, so I can bring in different models for exploration, implementation, or review.

## What stays with me

The agents can draft, code, test, and suggest. I still have to judge whether the result solves the actual problem. I review important choices, run the product, verify the claims, and decide what gets shipped. If two agents produce changes that do not fit together, the answer is better task boundaries and a clearer integration plan—not simply more generated code.

This is how I make room for bigger builds as an individual developer: a clear goal, delegated execution, visible progress, and a final result I can stand behind.
