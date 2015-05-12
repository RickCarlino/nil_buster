# nil_buster
Add an unseen level of discipline to your Ruby classes.

# What?

```ruby
module NilSanitizer
  def send(*args)
    freak_out if args.include?(nil)
    result = super
    freak_out if super.nil?
    result
  end

  def freak_out
    raise 'You passed or returned nil. Shame on you!'
  end
end
```
