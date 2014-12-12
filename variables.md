---
layout: page
title: Variables
permalink: /variables/
menu: true
---
#### $th-headings

**Type:** Map

**Description:** Define heading maps, lists and property values.

**Example:**

{% highlight sass %}
// Define heading maps, lists and property values
$th-headings: (
  h1: (30px 38px),
  h2: (24px 30px),
  h3: (18px 24px),
  h4: (16px 22px),
  h5: (14px 20px),
  h6: (12px 18px)
  );
{% endhighlight %}

**Map Structure:**

Heading property values are structured like so:

1. Font Size
2. Line Height
3. Margin Top / Bottom
4. Breakpoint

{% highlight sass %}
key: (font-size line-height (margin-top margin-bottom) breakpoint);
{% endhighlight %}

**Heading Breakpoints:**

Specify a heading list at a breakpoint:

{% highlight sass %}
// Specify a heading list at a breakpoint
$th-headings: ( h1: (30px 38px, 42px 50px 768px) );
{% endhighlight %}

**Heading Margins:**

A heading's margin top and bottom can be defined together by a single number value:

{% highlight sass %}
// Heading margin top and bottom number value
$th-headings: ( h1: (30px 38px 20px) );
{% endhighlight %}

A heading's margin top and bottom can also be defined individually by a list value:

{% highlight sass %}
// Heading margin top and bottom list value
$th-headings: ( h1: (30px 38px (10px 20px)) );
{% endhighlight %}

**Default Heading Property Values:**

Heading property values can be defined based on a default value in two ways:

<span>1.</span> Not defining the property value:

{% highlight sass %}
// Define only some heading list property values
$th-headings: ( h3: (18px) );

// Define default heading property values
$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 30px,
  margin-bottom: 20px
  );

// This is the same as writing:
// $th-headings: ( h3: (18px 24px (30px 20px)) );
// line-height, margin-top and margin-bottom are taken from defaults.
{% endhighlight %}

<span>2.</span> Defining a property value with a `default` keyword:

{% highlight sass %}
// Define a heading list property value as default
$th-headings: ( h3: (18px default (20px 10px)) );

// Define default heading property values
$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 30px,
  margin-bottom: 20px
  );

// This is the same as writing:
// $th-headings: ( h3: (18px 24px (20px 10px)) );
// line-height is taken from defaults.
{% endhighlight %}

---

#### $th-defaults

**Type:** Map

**Description:** Define default heading property values.

**Example:**

{% highlight sass %}
// Define default heading property values
$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 24px,
  margin-bottom: 24px
  );
{% endhighlight %}

Default heading property values will be used for any heading list value that uses
the `default` keyword or if not included within the list.