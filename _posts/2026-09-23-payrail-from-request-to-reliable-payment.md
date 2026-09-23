---
layout: post
title: "Payrail: from a payment request to a system I can trust"
description: "Why I started Payrail, what the first prototype actually does, and the reliability questions I am working through."
date: 2026-09-23
---

Payrail is my attempt to go deeper into payment systems. The ambition is to build something that treats a payment as more than a successful HTTP response: a clear, verifiable change of state that a person or business can trust. I am still at an early stage, and I want to show the work as it really is rather than present a prototype as a finished payment rail.

## What exists today

The first local prototype is a small Flask service with a `POST /payments` endpoint. It accepts a sender, a receiver, and an amount. It checks that those fields are present, rejects amounts that are not numeric or are nonpositive, and returns a JSON response with elapsed processing time.

That is useful as a first exercise in defining the shape of a payment request, but it does not move money or record a transfer. There is no ledger, balance change, or settlement behind the current success response. Recognizing that gap is part of the project, not something to hide.

## The problems in front of me

The first challenge is correctness at the API boundary. A payment endpoint needs to handle malformed JSON, incomplete account details, and invalid amounts without crashing or pretending a request succeeded. The current prototype gives me a starting point, but its validation and error handling need to become stricter.

Money also needs a precise representation. Ordinary floating-point values are a convenient input type for a first sketch, but rounding is not a detail I can ignore in a real payment flow. From there, I have to think about the state model: how a request becomes pending, succeeds, fails, or is retried, and how every transition can be explained later.

Duplicate requests are another question I want to solve deliberately. A timeout or network retry should not create two transfers. I want Payrail's next iterations to make idempotency, durable records, and testable failure paths part of the design rather than afterthoughts.

## Why I am building it

Payment infrastructure interests me because it forces careful engineering. The happy path is only one part of the problem. The harder work is making the system understandable when an input is wrong, a dependency fails, a request is repeated, or a user asks what happened to their money.

For now, Payrail is a learning build with an ambitious standard: move from a minimal HTTP endpoint toward a payment workflow whose behavior I can reason about, test, and explain. I will write about what I implement and what breaks as the project grows.
