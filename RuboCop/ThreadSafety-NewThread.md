Pattern: Starting new thread

Issue: -

## Description

Avoid starting new threads. Let a framework like Sidekiq handle the threads.

## Examples

```ruby
# bad
Thread.new { do_work }
```

## Further Reading

* [RuboCop - ThreadSafety/NewThread](https://github.com/covermymeds/rubocop-thread_safety/blob/master/lib/rubocop/cop/thread_safety/new_thread.rb)
