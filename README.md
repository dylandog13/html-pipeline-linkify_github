# HTML::Pipeline::LinkifyGitHub [![Build Status](https://travis-ci.org/jollygoodcode/html-pipeline-linkify_github.svg)](https://travis-ci.org/jollygoodcode/html-pipeline-linkify_github)

`HTML::Pipeline::LinkifyGitHub` provides a [HTML::Pipeline](https://github.com/jch/html-pipeline)
filter to autolink GitHub urls.

## Installation

Add this line to your application's Gemfile:

```ruby
gem "html-pipeline-linkify_github"
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install html-pipeline-linkify_github

## Usage

**Use `HTML::Pipeline::LinkifyGitHubFilter` filter before your markdown filter.**

```ruby
require "html/pipeline"
require "html/pipeline/linkify_github"

pipeline = HTML::Pipeline.new [
  HTML::Pipeline::LinkifyGitHubFilter,
  HTML::Pipeline::MarkdownFilter
]

result = pipeline.call <<-CODE
  https://github.com/rails/rails/pull/21862
  https://github.com/rails/rails/issues/21843
  https://github.com/rails/rails/commit/67597e1719ec6af7e22964603cc77aa5b085a864
CODE

puts result[:output]
```

prints:

```markdown
  [rails/rails#21862](https://github.com/rails/rails/pull/21862)
  [rails/rails#21843](https://github.com/rails/rails/issues/21843)
  [rails/rails@`67597e1`](https://github.com/rails/rails/commit/67597e1719ec6af7e22964603cc77aa5b085a864)
```

## Notes

This RubyGem requires Ruby 2.0+ because [support for 1.9.3 is officially end](https://www.ruby-lang.org/en/news/2014/01/10/ruby-1-9-3-will-end-on-2015/).

## Contributing

Please see the [CONTRIBUTING.md](/CONTRIBUTING.md) file.

## Credits

A huge THANK YOU to all our [contributors](https://github.com/jollygoodcode/html-pipeline-linkify_github/graphs/contributors)! :heart:

## License

Please see the [LICENSE.md](/LICENSE.md) file.

## Maintained by Jolly Good Code

[![Jolly Good Code](https://cloud.githubusercontent.com/assets/1000669/9362336/72f9c406-46d2-11e5-94de-5060e83fcf83.jpg)](http://www.jollygoodcode.com)

We specialise in Agile practices and Ruby, and we love contributing to open source.
[Speak to us](http://www.jollygoodcode.com/#get-in-touch) about your next big idea, or [check out our projects](http://www.jollygoodcode.com/open-source).