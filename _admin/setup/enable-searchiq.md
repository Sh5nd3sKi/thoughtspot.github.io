---
title: ["Enable SearchIQ"]
keywords: SearchIQ,introduction,"search bar","natural language","best practices"
last_updated: tbd
summary: "Enable SearchIQ to provide natural language search for some or all of your users."
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---

SearchIQ is a different search experience that understands more natural, speech-like search language than [the original ThoughtSpot search or **Search+**]({{ site.baseurl }}/end-user/search/about-starting-a-new-search.html). For example, you can search for `What was my top selling product last month?`, instead of having to type `top 1 product by sales last month`. You can also speak your search using the voice-to-text capability of your operating system.

{% include note.html content="SearchIQ is turned off by default, you can have ThoughtSpot Support enable it for you." %}

Users can easily [teach SearchIQ their language]({{ site.baseurl }}/end-user/search/teach-searchiq.html) as they use it. Over time, SearchIQ gets smarter about how to interpret terms that don’t come directly from keywords, column names, or data values. In order to give it time to learn, the best practice recommendation is to enable SearchIQ for a small group of users initially. Over time you can roll it out to larger groups as SearchIQ learns what your users search for the most.

To enable SearchIQ on a ThoughtSpot instance:

1. Call ThoughtSpot Support and ask them to turn on SearchIQ for your ThoughtSpot instance.

2. Grant the **Can use experimental features** privilege to any group that should have access to the SearchIQ search experience.

   ![]({{ site.baseurl }}/images/searchiq_privilege.png "SearchIQ privilege")

{% include note.html content="Because the SearchIQ search experience is very different from the original ThoughtSpot search experience, you should give your new users some orientation on it, so they know what to expect." %}

## Related information

-   [About SearchIQ]({{ site.baseurl }}/end-user/search/about-searchiq.html)
-   [Use SearchIQ]({{ site.baseurl }}/end-user/search/use-searchiq.html)
-   [Teach SearchIQ your language]({{ site.baseurl }}/end-user/search/teach-searchiq.html)