---
layout: page
title: Usage
permalink: /usage/
menu: true
---
---

## Headings

---

#### th-heading-get()

**Type:** Function

**Description:** Return a heading list from $th-headings.

**Format:** `th-heading-get($heading, $breakpoint)`

**$heading:** mixed | A heading map key or list (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

{% highlight sass %}
// With heading map key example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );
@debug th-heading-get(h1); // 36px 42px 20px
{% endhighlight %}

{% highlight sass %}
// With heading map key and heading list breakpoint example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );
@debug th-heading-get(h1, 768px); // 42px 48px 20px 768px
{% endhighlight %}

---

#### th-heading-get-map()

**Type:** Function

**Description:** Return a heading map from $th-headings.

**Format:** `th-heading-get-map($heading)`

**$heading:** string | A heading map key (required). | `$th-headings`

**Example:**

{% highlight sass %}
// With heading map key example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );
@debug th-heading-get-map(h1); // 36px 42px 20px, 42px 48px 20px 768px
{% endhighlight %}

---

#### th-heading()

**Type:** Mixin

**Description:** Output styles for a heading list.

**Format:** `@include th-heading($heading, $breakpoint)`

**$heading:** string | A heading map key (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

{% highlight sass %}
// With heading map key example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { @include th-heading(h1); }

// Output
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
  font-size: 36px;
  line-height: 42px;
}
{% endhighlight %}

{% highlight sass %}
// With heading list breakpoint example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { @include th-heading(h1, 768px); }

// Output
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

**Format:** `@include th-headings($heading, $breakpoint)`

**$heading:** string | A heading map key (required). | `$th-headings`

**Example:**

{% highlight sass %}
// With heading map key example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { @include th-headings(h1); }

// Output
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

---

#### th-property-get()

**Type:** Function

**Description:** Returns a heading list property value.

**Format:** `th-property-get($heading, $property-name, $breakpoint)`

**$heading:** mixed |  A heading map key or list (required). | `$th-headings`

**$property-name:** string | A heading property name (required).

**$breakpoint:** number | A heading list breakpoint (optional). | `$th-headings`

**Example:**

{% highlight sass %}
// With heading map key and property name example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { font-size: th-property-get(h1, font-size); }

// Output
h1 {
  font-size: 36px;
}
{% endhighlight %}

{% highlight sass %}
// With heading map key, property name and list breakpoint example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { line-height: th-property-get(h1, line-height, 768px); }

// Output
h1 {
  line-height: 48px;
}
{% endhighlight %}

---

#### th-property-get-default()

**Type:** Function

**Description:** Return a default heading property value.

**Format:** `th-property-get-default($property-name)`

**$property-name:** string | A heading property name (required).

**Example:**

{% highlight sass %}
// With heading property name example

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { 
  margin-top: th-property-get-default(margin-top);
  margin-bottom: th-property-get-default(margin-bottom);
}

// Output
h1 {
  margin-top: 20px;
  margin-bottom: 20px;
}
{% endhighlight %}

---

## Breakpoints

---

#### th-breakpoint-heading()

**Type:** Mixin

**Description:** Output styles for a heading list within a media query.

**Format:** `@include th-breakpoint-heading($heading, $breakpoint, $direction)`

**$heading:** string | A heading map key (required). | `$th-headings`

**$breakpoint:** number | A heading list breakpoint (required). | `$th-headings`

**$direction:** string | Media query direction (optional). | `min-width`, `max-width`

**Example:**

{% highlight sass %}
// Output styles for a heading list within a min width media query.

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { @include th-breakpoint-heading(h1, 768px) }

// Output
@media screen and (min-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 42px;
    line-height: 48px;
  }
}
{% endhighlight %}

{% highlight sass %}
// Output styles for a heading list within a max width media query.

$th-headings: ( h1: (36px 42px 20px, 42px 48px 20px 768px) );

// Input
h1 { @include th-breakpoint-heading(h1, 768px, max-width) }

// Output
@media screen and (max-width: 768px) {
  h1 {
    margin-top: 20px;
    margin-bottom: 20px;
    font-size: 42px;
    line-height: 48px;
  }
}
{% endhighlight %}