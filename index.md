---
layout: page
title: Type Heading - Alpha
permalink: /
---
[![Gem Version](https://badge.fury.io/rb/type-heading.svg)](http://badge.fury.io/rb/type-heading)

<p class="type-lede">A responsive typography tool for headings.</p>

Type Heading is a lightweight tool that lets you easily control heading sizing
accross multiple breakpoints.

<a href="https://github.com/ellioseven/type-heading" class="button">View on Github</a>

---

<div class="info">
Type heading is currently in <a href="http://en.wikipedia.org/wiki/Software_release_life_cycle#Alpha">Alpha</a>.
Currently, Type Heading should only be used for testing and/or development, not
production work.
</div>

---

## Get Started With Type Heading

Type Heading is built to be as easy as possible:

### Sass Input:

{% highlight sass %}
$th-headings: ( 
  h1: (32px 42px, 36px 48px 30px 768px),
  h2: (24px 32px),
);

$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 20px,
  margin-bottom: 20px
  );

h1 { @include th-headings(h1); }
h2 { @include th-headings(h2); }
{% endhighlight %}

### Compiles to:

{% highlight sass %}
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 32px;
  line-height: 42px;
}

h2 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 24px;
  line-height: 32px;
}

@media screen and (min-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 36px;
    line-height: 48px;
  }
}
{% endhighlight %}

Get up and running quickly with the [Getting Started Guide]({{site.url}}/getting-started).

---

## Timeline

* **12.12.2014:** 0.0.10 released - <a href="{{site.url}}/change-log">Change Log</a>
* **05.12.2014:** 0.0.9 released - <a href="{{site.url}}/change-log">Change Log</a>
* **04.12.2014:** Initial alpha published