# nil_buster
Add an unseen level of discipline to your Ruby classes.

# What?

```ruby
module NilBuster
  def send(*args)
    freak_out if args.include?(nil)
    result = super
    freak_out if super.nil?
    result
  end
  
  def freak_out
    abort 'You passed or returned nil. Shame on you!'
  end
end
```

How about an example?

```ruby
class Parrot
  include NilBuster
  def say(phrase)
    puts phrase
    return phrase
  end
  
  def sit
    return nil
  end
end

Parrot.new.say(nil)
# => Dumps you to the terminal.
Parrot.sit
# => Dumps you to the terminal.
```
