---
layout: post
title:  "Ada Ada Bindigs"
category: binding
tags: ["Ada", "binding"]
version: 0.0.1-wip
---

Why make Ada bindings to Ada libraries ?
To make a facade specifically for the project at hand.
Impedance mismatch correction.

Example
----
We have a fixed library for TOML files. Let us call it Tombling. This
library may at one hand not be perfect, or on then other har is much
to big og complicated for out need. By creating a facade binding the
library is adapted for our specific project. 
