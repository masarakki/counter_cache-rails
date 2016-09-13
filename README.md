# CounterCacheRails

ActiveRecord child records counter caching on your rails application cache store.

## Installation

Add this line to your rails application's Gemfile:

```ruby
gem 'counter_cache-rails'
```

## Usage

```rb
class Post
  has_many :comments
  counter_cache :comments
end

class Comment
  belong_to :post
end

post = Post.create(title: 'sample title', body: 'post body')
post.comments_count # => 0

post.comments.create(body: 'comment body')
post.comments_count # => 1
```

## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
