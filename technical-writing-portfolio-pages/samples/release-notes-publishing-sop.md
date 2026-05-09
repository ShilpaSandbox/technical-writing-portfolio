---
layout: default
title: Internal SOP
permalink: /samples/release-notes-publishing-sop/
---

# Standard Operating Procedure: Publishing Release Notes in GitHub and Markdown

<div class="meta-box">
<strong>Sample type:</strong> Internal process documentation<br>
<strong>Focus:</strong> Documentation workflow, review handoff, and publishing quality control<br>
<strong>What this sample demonstrates:</strong> Process clarity, operational structure, and cross-functional alignment
</div>

## Purpose

This procedure explains how to create, review, and publish release notes for the web application after each production release.

## Scope

Use this SOP for all monthly releases and hotfix releases affecting customer-facing features, bug fixes, or UI changes.

## Roles and Responsibilities

The product manager provides the approved list of release items.  
The engineering lead confirms technical accuracy.  
The technical writer drafts, edits, and publishes the final release notes.

## Procedure

### 1. Collect Release Information

Gather the final list of completed tickets from Jira. Confirm which updates are customer-facing and which should remain internal.

### 2. Draft the Content

Create a new Markdown file using the release notes template. Organize content under these headings:

- New features
- Improvements
- Bug fixes
- Known issues, if applicable

### 3. Review for Accuracy

Send the draft to the engineering lead and product manager. Resolve terminology issues, remove internal-only details, and verify feature names.

### 4. Edit for Style and Clarity

Review the content for:

- plain language
- consistent terminology
- concise descriptions
- customer-facing tone

### 5. Publish

Commit the final Markdown file to the documentation repository and publish it to the help center. Confirm formatting, links, and heading structure after deployment.

## Quality Checklist

Before publishing, confirm that:

- dates are correct
- feature names match the product UI
- internal ticket references are removed
- headings are consistent
- links are working
