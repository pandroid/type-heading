---
layout: page
title: Getting Started
permalink: /getting-started/
menu: true
---
<p class="type-lede">Type Heading is available accross many sourcing platforms
and is easy to include into your Sass.</p>

## Requirements

To use Type Heading, you will need:

- Ruby: 2.2.2
- Sass 3.4.7
- Compass: 1.0.1

## Installation

To install Type Heading and start using it your Sass, you will need to:

1. Source the extension
2. Import the extension into your Sass
3. Define your own heading settings in your Sass

### Source

Type Heading is a compass extension that can be sourced multiple ways.

#### Gem

{% highlight bash %}
$ gem install type-heading
{% endhighlight %}

#### Bundler

{% highlight ruby %}
# Gemfile
gem 'sass', '~> 3.4.7'
gem 'compass', '~> 1.0.1'
gem 'type-heading', '~> 0.0.7'
{% endhighlight %}

{% highlight ruby %}
# config.rb
require 'type-heading'
{% endhighlight %}

{% highlight bash %}
$ bundle install
{% endhighlight %}

#### Bower

{% highlight bash %}
$ bower install type-heading
{% endhighlight %}

#### Grunt

To use type-heading with Grunt, you must first install the gem locally or with
bundler and include it in your `Gruntfile.js`

{% highlight js %}
// Gruntfile.js
compass: {
    options: {
      require: 'type-heading',
      ...
    }
  }
}
{% endhighlight %}

#### Compass

{% highlight bash %}
$ compass create --using type-heading <project_name>
{% endhighlight %}

### Import

Once you have sourced Type Heading, you will need to import it into your Sass.

{% highlight sass %}
@import "type-heading"
{% endhighlight %}

### Define

To use Type Heading in your Sass, you should define your own headings and default
heading property values.

{% highlight sass %}
$th-headings: (
  h1: (36px 42px),
  h2: (24px 36px),
  h3: (18px 24px),
  h4: (16px 22px),
  h5: (14px 20px),
  h6: (12px 18px)
  );

$th-defaults: (
  font-size: 16px,
  line-height: 24px,
  margin-top: 24px,
  margin-bottom: 24px
  );
{% endhighlight %}

## Basic Usage

You can now start to use Type Heading to build your heading styles:

{% highlight sass %}
h1 { @include th-heading(h1); }
{% endhighlight %}

Once you have managed to get started, you should take a closer look at available
<a href="{{site.url}}/variables">variables</a> and <a href="{{site.url}}/usage">how 
to use Type Heading</a>.
