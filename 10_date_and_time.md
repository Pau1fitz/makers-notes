# Date and Time

Date and time are painful to work with. Ruby's built-in Time and Date classes help.

## Testing time

How do you test a method which requires a wait (such as charging the user when renting a Boris bike and returning it half an hour later)?

Use [timecop](https://github.com/travisjeffery/timecop).

For example, in your test you can write 

```ruby
Timecop.freeze(Time.local(2014))
```

Now, every time you (or your code) requests ```Time.now```, it will return

```ruby
=> 2014-01-01 00:00:00 +0000
```

In the Boris bike example, you can jump forward in time (which saves you having to wait in real-time for your method to run).