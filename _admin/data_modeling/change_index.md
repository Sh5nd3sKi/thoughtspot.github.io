---
title: [Change the index type]
tags:
keywords: tbd
last_updated: tbd
summary: "ThoughtSpot indexes column names and unique column values. The indexes are used to dynamically generate suggestions in the search bar when typing a search."
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---
You can change the way a column is indexed by modifying its **Index** value in the modeling file, to influence the suggestions that will appear for that column. The default behavior of indexing is as follows:

-   All column names are indexed using their **ColumnName** value.
-   Values for columns with the column type of **MEASURE** are not indexed.
-   Values for columns with the data type of **DATE** are not indexed.
-   Columns that contain a large amount of free-form text (i.e. the number of characters in more than a few of the fields is more than 50) are indexed as PREFIX_ONLY by default.
-   Short strings (like a firstname column) are indexed using PREFIX_AND_SUBSTRING by default, which indexes both prefix and substrings.

It is not recommended to change the indexing for columns with very large free text values. These should not to be indexed, because indexing on these values is not useful and may generate confusing suggestions.

You can override the default behavior by editing the modeling file to change the **Index** value for any columns that should be indexed differently. There are several different supported index types:

|Index type|Description|
|----------|-----------|
|`DEFAULT`|This is the default value. The default indexing behavior will apply to the column values, depending on their type. `PREFIX_AND_SUBSTRING` for short values and `PREFIX_ONLY` for long values and free-form text.|
|`DONT_INDEX`|Prevents indexing on the column values.|
|`PREFIX_AND_SUBSTRING`|Allows full indexing such that prefix and sub-string search both work for the column values.|
|`PREFIX_ONLY`|Allows indexing such that only prefix search works for the column values.|
|`PREFIX_AND_WORD_SUBSTRING`|Allows indexing such that only prefix search works for each word of a multi-word string, for the column values.|

1. Find the column whose index type you want to modify, and set its **Index Type**. If you are using the model file, double click in the **Index** cell, and type in the index type you want to use.
2. Save your changes.

Consider a column in which there are four values “ThoughtSpot”, “Thought”, “Spot” and “Thought Spot”. If you search for “sp”, depending on the setting for indexing, the column value search result suggestions will vary:

|**Index** field value|Search bar suggestions|
|---------------------|----------------------|
|`DEFAULT`|“*Thought**Sp**ot*”, “***Sp**ot*” and “*Thought **Sp**ot*”|
|`DONT_INDEX`|No suggestions.|
|`PREFIX_AND_SUBSTRING`|“*Thought**Sp**ot*”, “***Sp**ot*” and “*Thought **Sp***ot”|
|`PREFIX_ONLY`|“***Sp**ot*”|
|`PREFIX_AND_WORD_SUBSTRING`|“***Sp**ot*” and “*Thought **Sp**ot*”|


## Related information  

[Model the data for searching](semantic_modeling.html#)