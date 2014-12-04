---
layout: page
title: Type Heading - ALPHA
permalink: /
---
[![Gem Version](https://badge.fury.io/rb/type-heading.svg)](http://badge.fury.io/rb/type-heading)

<p class="type-lede">A responsive typography tool for headings.</p>

Type Heading is a lightweight tool that lets you easily control heading sizing
accross multiple breakpoints.

<a href="https://github.com/ellioseven/type-heading" class="button">View on Github</a>

---

## Get Started With Type Heading

It's easy and is designed to make you life easier:

{% highlight sass %}
$th-headings: ( 
  h1: (32px 42px, 36px 48px 20px 768px),
  h2: (24px 32px, 30px 38px 20px 768px),
  h3: (18, 24px)
);

$th-defaults: (
  font-size: $base-font-size,
  line-height: $base-line-height,
  margin-top: $base-vertical-margin,
  margin-bottom: $base-vertical-margin
);

h1 { @include th-headings(h1); }
h2 { @include th-headings(h2); }
h3 { @include th-headings(h3); }
{% endhighlight %}

Get up and running quickly with the [Getting Started Guide](getting-started).

---

## Timeline

**4.12.2014:** Initial beta build published