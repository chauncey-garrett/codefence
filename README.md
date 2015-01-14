# Octopress Codefence

Write beautiful fenced code snippets within any template.

[![Gem Version](https://badge.fury.io/rb/octopress-codefence.png)](http://badge.fury.io/rb/octopress-codefence)
[![Build Status](https://travis-ci.org/octopress/codefence.png?branch=master)](https://travis-ci.org/octopress/codefence)

## Installation

### Using Bundler

Add this gem to your site's Gemfile in the `:jekyll_plugins` group:

    group :jekyll_plugins do
      gem 'octopress-codefence'
    end

Then install the gem with Bundler

    $ bundle

### Manual Installation

    $ gem install octopress-codefence

Then add the gem to your Jekyll configuration.

    gems:
      - octopress-codefence

## Usage

The Octopress codefence has some

### Syntax

    &#96;&#96;&#96;lang [options]
    [code]
    &#96;&#96;&#96;

### Options

Note that order does not matter.

| Options      | Example                | Description                                                           |
|:-------------|:-----------------------|:----------------------------------------------------------------------|
|`lang`        | `ruby`                 | Used by the syntax highlighter. Passing 'plain' disables highlighting.|
|`title`       | `title:"Figure 1.A"`   | Add a figcaption title to your code block. |
|`link_text`   | `link_text:"Download"` | Text for the link, default: `"link"`. |
|`linenos`     | `lineos:false`         | Disable line numbering. |
|`start`       | `start:5`              | Start the line numbering at the given value. |
|`mark`        | `mark:1-4,8`           | Highlight lines of code. This example marks lines 1,2,3,4 and 8 |
|`class`       | `class:"css example"`  | Add CSS class names to the code `<figure>` element |

### Examples

Finally, give it a try. Here's an code snippet sample.

    &#96;``ruby mark:2-4 title:"Testing codefence" url:"https://github.com/octopress/codefence" link_text:"plugin link"
    class Float
      def number_decimal_places
        self.to_s.length-2
      end
      
      def to_fraction
        higher = 10**self.number_decimal_places
        lower = self*higher
    
        gcden = greatest_common_divisor(higher, lower)
    
        return (lower/gcden).round, (higher/gcden).round
      end
      
    private
    
      def greatest_common_divisor(a, b)
         while a%b != 0
           a,b = b.round,(a%b).round
         end 
         return b
      end
    end
    &#96;``

Which renders like this:

<!-- mark:2-4 title:"Testing codefence" url:"https://github.com/octopress/codefence" link_text:"plugin link" -->
```ruby
class Float
  def number_decimal_places
    self.to_s.length-2
  end
  
  def to_fraction
    higher = 10**self.number_decimal_places
    lower = self*higher

    gcden = greatest_common_divisor(higher, lower)

    return (lower/gcden).round, (higher/gcden).round
  end
  
private

  def greatest_common_divisor(a, b)
     while a%b != 0
       a,b = b.round,(a%b).round
     end 
     return b
  end
end
```
Here's a themed sample:

<img src="http://cl.ly/TFCm/content.png" alt='sample screenshot of the code snippet above renderd with the light theme' width="816px">

Here's a look at the dark theme:

<img src="http://cl.ly/TFPX/content.png" alt='sample screenshot of the code snippet above renderd with the dark theme' width="816px">

More documentation coming soon.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License MIT

Copyright (c) 2013 Brandon Mathis

MIT License

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
