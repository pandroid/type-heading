---
layout: page
title: Variables
permalink: /variables/
menu: true
---
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

1. Not defining the property value:

{% highlight sass %}
// Default heading property values by exclusion

$th-headings: ( h3: (18px) );

$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 30px,
  margin-bottom: 20px
  );

// is the same as writing
// $th-headings: ( h3: (18px 24px (30px 20px)) );
{% endhighlight %}

2. Defining a property value with a `default` keyword:

{% highlight sass %}
// Default heading property value with the default keyword

$th-headings: ( h3: (18px default (20px 10px)) );

$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 30px,
  margin-bottom: 20px
  );

// is the same as writing
// $th-headings: ( h3: (18px 24px (20px 10px)) );
{% endhighlight %}

<div class="info">Be careful when defining a heading's margin top property value:</div>

{% highlight sass %}
// Margin bottom outputs as 22px
$th-headings: ( h1: ( 32px, 42px 48px (20px,) 768px ) );
$th-defaults: ( margin-bottom: 22px );
@debug th-property-get(h1, margin-bottom, 768px);

// Margin bottom outputs as 22px
$th-headings: ( h1: ( 32px, 42px 48px (20px, default) 768px ) );
$th-defaults: ( margin-top: 18px, margin-bottom: 22px );
@debug th-property-get(h1, margin-bottom, 768px);

// Margin bottom outputs as 20px
$th-headings: ( h1: ( 32px, 42px 48px (20px) 768px ) );
$th-defaults: ( margin-top: 18px, margin-bottom: 22px );
@debug th-property-get(h1, margin-bottom, 768px);
{% endhighlight %}

---

#### $th-defaults

**Type:** Map

**Description:** Define default heading property values.

**Example:**

{% highlight sass %}
// Define default heading property values.

$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 24px,
  margin-bottom: 24px
  );
{% endhighlight %}

Default heading property values will be used for any heading list value that uses
the `default` keyword or if not included within the list.