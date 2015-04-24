# Preload [![Build Status](https://secure.travis-ci.org/staugaard/preload.png?branch=master)](http://travis-ci.org/staugaard/preload)

Allows you to split your ActiveRecord find calls and your eager loading decisions.

## Installation

Add this line to your application's Gemfile:

    gem 'preload'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install preload

## Usage

Now in your controller you don't have to know which associations should be eager loaded because your views need them.

### In your controller:

```ruby
def index
  @posts = blog.posts.all(:order => 'created_at DESC')
end
```

### in your view:
```
  <% @posts.pre_load(:comments) %>
  ... render posts and their comments ...
```


## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
