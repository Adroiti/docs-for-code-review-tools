Pattern: Use of `flash` before `render` in Rails controller

Issue: -

## Description

Using `flash` assignment before `render` in Rails controllers will persist the message for too long.

## Examples

```ruby
# bad
class HomeController < ApplicationController
  def create
    flash[:alert] = "msg"
    render :index
  end
end

# good
class HomeController < ApplicationController
  def create
    flash.now[:alert] = "msg"
    render :index
  end
end
```

## Further Reading

* [Rails - Rails/ActionControllerFlashBeforeRender](https://docs.rubocop.org/rubocop-rails/cops_rails.html#railsactioncontrollerflashbeforerender)
* https://rails.rubystyle.guide/#flash-before-render
* https://api.rubyonrails.org/classes/ActionController/FlashBeforeRender.html