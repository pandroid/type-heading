---
layout: page
title: Usage
permalink: /usage/
menu: true
---
## Headings

#### th-heading-get()

**Type:** Function

**Description:** Return a heading list.

**Format:** 

{% highlight sass %}
// Function
th-heading-get($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Output: 36px 42px 20px
@debug th-heading-get(h1);
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Output: 42px 48px 20px 768px
@debug th-heading-get(h1, 768px); 
{% endhighlight %}

---

#### th-heading-get-map()

**Type:** Function

**Description:** Return a heading map.

**Format:** 

{% highlight sass %}
// Function
th-heading-get-map($heading)
{% endhighlight %}

**$heading:** string | A heading map key (required). | `$th-headings`

**Example:**

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Output: 36px 42px 20px, 42px 48px 20px 768px
@debug th-heading-get-map(h1);
{% endhighlight %}

---

#### th-heading()

**Type:** Mixin

**Description:** Output styles for a heading list.

**Format:** 

{% highlight sass %}
// Mixin
@include th-heading($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input:
h1 { @include th-heading(h1); }

// Output:
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 36px;
  line-height: 42px;
}
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input:
h1 { @include th-heading(h1, 768px); }

// Output:
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 42px;
  line-height: 48px;
}
{% endhighlight %}

---

#### th-headings()

**Type:** Mixin

**Description:** Output styles for all heading lists in a heading map.

**Format:** 

{% highlight sass %}
// Mixin
@include th-headings($heading, $breakpoint)
{% endhighlight %}

**$heading:** string | A heading map key (required). | `$th-headings`

**Example:**

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input:
h1 { @include th-headings(h1); }

// Output:
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 36px;
  line-height: 42px;
}

@media screen and (min-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 42px;
    line-height: 48px;
  }
}
{% endhighlight %}

---

## Properties

#### th-property()

**Type:** Function

**Description:** Returns a heading list property value.

**Format:** 

{% highlight sass %}
// Function
th-property($heading, $property-name, $breakpoint)
{% endhighlight %}

**$heading:** mixed |  A heading map key or list (required). | `$th-headings`

**$property-name:** string | A heading property name (required). | `$th-defaults`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

With heading map key and property name:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Output: h1{ font-size: 36px; }
h1 { font-size: th-property(h1, font-size); }
{% endhighlight %}

With heading map key, property name and breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Output: h1 { line-height: 48px; }
h1 { line-height: th-property(h1, line-height, 768px); }
{% endhighlight %}

---

#### th-property-font-size()

**Type:** Function & Mixin

**Description:** Return / output heading list font size property value.

**Format:** 
{% highlight sass %}
// Function
th-property-font-size($heading, $breakpoint)

// Mixin
@include th-property-font-size($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:** 

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { font-size: 36px; }
h1 {  font-size: th-property-font-size(h1); }

// Output: h1 { font-size: 36px; }
h1 {  @include th-property-font-size(h1); }
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { font-size: 42px; }
h1 { font-size: th-property-font-size(h1, 768px); }

// Output: h1 { font-size: 42px; }
h1 { @include th-property-font-size(h1, 768px); }
{% endhighlight %}

---

#### th-property-line-height()

**Type:** Function & Mixin

**Description:** Return / output heading list line height property value.

**Format:** 
{% highlight sass %}
// Function
th-property-line-height($heading, $breakpoint)

// Mixin
@include th-property-line-height($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:** 

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { line-height: 42px; }
h1 { line-height: th-property-line-height(h1); }

// Output: h1 { line-height: 42px; }
h1 { @include th-property-line-height(h1); }
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { line-height: 48px; }
h1 { line-height: th-property-line-height(h1, 768px); }

// Output: h1 { line-height: 48px; }
h1 { @include th-property-line-height(h1, 768px); }
{% endhighlight %}

---

#### th-property-margin-top()

**Type:** Function & Mixin

**Description:** Return / output heading list margin top property value.

**Format:** 
{% highlight sass %}
// Function
th-property-margin-top($heading, $breakpoint)

// Mixin
@include th-property-margin-top($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:** 

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { margin-top: 20px; }
h1 { margin-top: th-property-margin-top(h1); }

// Output: h1 { margin-top: 20px; }
h1 { @include th-property-margin-top(h1); }
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { margin-top: 30px; }
h1 { margin-top: th-property-margin-top(h1, 768px); }

// Output: h1 { margin-top: 30px; }
h1 { @include th-property-margin-top(h1, 768px); }
{% endhighlight %}

---

#### th-property-margin-bottom()

**Type:** Function & Mixin

**Description:** Return / output heading list margin bottom property value.

**Format:** 
{% highlight sass %}
// Function
th-property-margin-bottom($heading, $breakpoint)

// Mixin
@include th-property-margin-bottom($heading, $breakpoint)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:** 

With heading map key:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { margin-bottom: 20px; }
h1 { margin-bottom: th-property-margin-bottom(h1); }

// Output: h1 { margin-bottom: 20px; }
h1 { @include th-property-margin-bottom(h1); }
{% endhighlight %}

With heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px (20px 20px), 42px 48px (30px 30px) 768px) );

// Output: h1 { margin-bottom: 30px; }
h1 { margin-bottom: th-property-margin-bottom(h1, 768px); }

// Output: h1 { margin-bottom: 30px; }
h1 { @include th-property-margin-bottom(h1, 768px); }
{% endhighlight %}

---

#### th-property-default()

**Type:** Function & Mixin

**Description:** Return / output a default heading property value.

**Format:** 

{% highlight sass %}
// Function
th-property-default($property-name)

// Mixin
@include th-property-default($property-name)
{% endhighlight %}

**$property-name:** string | A heading property name (required). | `$th-defaults`

**Example:**

With heading property name:

{% highlight sass %}
// Set heading property value defaults
$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 30px,
  margin-bottom: 20px
  );

// Output: h1 { margin-top: 30px; }
h1 {  margin-top: th-property-default(margin-top); }

// Output: h1 { margin-top: 30px; }
h1 { @include th-property-default(margin-top); }
{% endhighlight %}

---

## Breakpoints

#### th-breakpoint-heading()

**Type:** Mixin

**Description:** Output styles for a heading list within a media query.

**Format:** 

{% highlight sass %}
// Mixin
@include th-breakpoint-heading($heading, $breakpoint, $direction)
{% endhighlight %}

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (required). | `$th-headings`

**$direction:** string | Media query direction (optional). | `min-width`, `max-width`

**Example:**

Min width breakpoint with heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input:
h1 { @include th-breakpoint-heading(h1, 768px) }

// Output:
@media screen and (min-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 42px;
    line-height: 48px;
  }
}
{% endhighlight %}

Max width breakpoint with heading map key and heading list breakpoint:

{% highlight sass %}
// Set heading property values
$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input:
h1 { @include th-breakpoint-heading(h1, 768px, max-width) }

// Output:
@media screen and (max-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 42px;
    line-height: 48px;
  }
}
{% endhighlight %}