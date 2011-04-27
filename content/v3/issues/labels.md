---
title: Issue Labels API v3 | dev.github.com
---

# Labels API

## List all Labels for this Repository

    GET /repos/:user/:repo/labels.json

### Response

<%= json(:label) { |h| [h] } %>

## Create a Label

    POST /repos/:user/:repo/labels.json

### Input

<%= json :name => "String", :color => "hex" %>

*Note*: `color` takes a 6 character hex code, without a leading `#`.

### Response

<%= json :label %>

## Get a single Label

    GET /repos/:user/:repo/labels/:id.json

### Response

<%= json :label %>

## Update a Label

    PATCH /repos/:user/:repo/labels/:id.json

### Input

<%= json :name => "String", :color => "hex" %>

*Note*: `color` takes a 6 character hex code, without a leading `#`.

### Response

<%= json :label %>

## Delete a label

    DELETE /repos/:user/:repo/labels/:id.json

### Response

    {}

## List labels on the Issue

    GET /repos/:user/:repo/issues/:id/labels.json

### Response

<%= json(:label) { |h| [h] } %>

## Add Labels to an Issue

    POST /repos/:user/:repo/issues/:id/labels.json

### Input

<%= json({name: "String"}) { |h| [h] } %>

### Response

<%= json(:label) { |h| [h] } %>

## Remove a Label from an Issue

    DELETE /repos/:user/:repo/issues/:id/labels/:id.json

### Response

<%= json(:label) { |h| [h] } %>

## Replace all Labels for an Issue

    PUT /repos/:user/:repo/issues/:id/labels.json

### Input

<%= json({name: "String"}) { |h| [h] } %>

### Response

<%= json(:label) { |h| [h] } %>

## Remove all Labels from an Issue

    DELETE /repos/:user/:repo/issues/:id/labels.json

### Response

    {}

## Get Labels for every Issue in a Milestone

    GET /repos/:user/:repo/milestones/:id/labels.json

### Response

<%= json(:label) { |h| [h] } %>