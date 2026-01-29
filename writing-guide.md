# Guide for Authors: Creating AI Quickstarts That Publish Faster (And Protect Red Hat)

This document provides guidance to help you create, edit, and publish AI quickstart content faster by aligning with Red Hat’s corporate standards. Following these practices ensures your content is legally compliant, accessible, and optimized for search. In each section you will find bullet points with recommendations. These are top recommendations and are not an exhaustive checklist for creating compliant content.

## 1. Naming and Branding Consistency

Improper product naming is the most common reason for editorial delays. Accurate naming protects our trademarks and ensures a professional brand presence.
* **Use the Official List:** Always cross-reference the [Official Red Hat Product Names List](https://docs.google.com/spreadsheets/d/1DLS_lS3VKidgZIvcLmLp9BoiqptkvqHWfe1D5FD2kfk/edit?gid=1259317633#gid=1259317633) (OPL).
* **The "First Mention" Rule:** Use the full product name with the appropriate trademark symbol (e.g., **Red Hat® OpenShift®**) on the first mention. Subsequent mentions can use approved short names (e.g., **OpenShift**). Always refer to the OPL for the latest information on short names.
* **Abbreviations:** Ensure the product name is stylized correctly. If a trademark or registered mark is required, include it. Avoid unauthorized abbreviations like "RHAI" or "RAI." For more information, always refer to the OPL.

## 2. The Content Toolbox (VPN Required)

The [BX Content Toolbox](https://red.ht/content-toolbox) is your primary resource for self-editing. Using these tools before submission will reduce speed up the publishing process and save Red Hat money.

### Key Focus Areas:
* **Style Guide:** Check for Red Hat-specific grammar, punctuation, and "voice and tone" (conversational yet professional).
* **Accessibility Analyzer:** Ensure your quickstart meets WCAG 2.2 AA standards.
  * **Headings:** Use logical nesting (H2 > H3).
  * **Alt Text:** All images must have descriptive alt text that explains the function or meaning of the image, not just a literal description. AI tools can help generate alt text. Consider using a prompt asking for accessibility alt text for your image.
    * For example, markdown image links should be descriptive: `[Architectural diagram for document ingestion](path to image)`, NOT `[image1](path to image1)`
* **Inclusive Language:** Use the analyzer to flag non-inclusive terms (e.g., replace "master/slave" with "primary/secondary" or "blacklist" with "blocklist").

## 3. SEO and Legal Guidance

To ensure your quickstart is discoverable and legally sound, follow these requirements:

### SEO Best Practices

* **Short Descriptions:** Every guide must start with a concise, 1-2 sentence abstract that summarizes the value proposition.
* **Keywords:** Include "AI," "quickstart," and the specific product name in the first paragraph.
* **Link Text:** Use descriptive link text. Avoid "Click here" or "Read more." Use "Download the Red Hat Enterprise Linux installation guide."

### Legal & AI Compliance

* **Disclosure:** If any part of the quickstart was generated using AI, consult legal on whether a disclosure (e.g., "Assisted-by: AI") is required.
* **No Guarantees:** Avoid language that "guarantees" specific performance metrics or outcomes, as AI results can vary based on user data.
* **Copyright:** Do not use copyrighted third-party material or logos within your examples.


