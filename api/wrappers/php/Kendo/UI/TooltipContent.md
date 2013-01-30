---
title: TooltipContent
slug: php-TooltipContent
tags: api, php
publish: true
---

# \Kendo\UI\TooltipContent

A PHP class representing the content setting of Tooltip.


## Methods

### url
Specifies a URL or request options that the tooltip should load its content from.Note: For URLs starting with a protocol (e.g. http://),
a container iframe element is automatically created. This behavior may change in future
versions, so it is advisable to always use the iframe configuration option.
#### Parameters

##### $value `string`



#### Example 
    $content = new \Kendo\UI\TooltipContent();
    $content->url('value');
