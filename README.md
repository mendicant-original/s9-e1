# Integration Exercise: Java Library Wrapper

_written by Shane Emmons for Mendicant University core skills session #9_

The world is full of Java. Chances are pretty good if you walk into a
corporate IT department you'll find Java. So, what do we as Ruby developers do
when forced to work with Java? We turn to JRuby and it's Java integration. Your
assignment, should you choose to accept it, is to use JRuby to wrap an existing
Java library into a new Ruby gem. You can choose any Java library you like.
However, if there already existing a functional and active gem, you should look
at wrapping a different library unless you plan on taking a different route.
Either way, please have Greg or Shane approve your chosen library before
starting work in earnest. 

Oh, and one more thing. We don't just want this to be
a straight API copy of the existing library. Abstract things away from the
programmer so that working with your gem is easier than working directly with
the library via JRuby. The code below is an example of what *not* to do.

```ruby
session   = CrystalEnterprise.getSessionManager.logon(user, password, cms, authtype)
infostore = session.getService('', 'InfoStore')
```

With a little bit of effort, this interaction could be made to feel a lot more
natural to a native Rubyist. The code shown below is much closer to what you
should be aiming for.

```ruby
session   = Enterprise.connect(user: "shane", password: "password")
infostore = session.infostore
```
For a more complete example, see Shane's [bosdk wrapper](https://github.com/semmons99/bosdk).

## Exercise Summary

- You should create a gem using JRuby that wraps an existing Java library.
- Your gem should work with a Java library that doesn't already have
  a good wrapper.
- You should make the API for your library look and feel like Ruby, not Java.

## Submission Guidelines

If you plan to work on this exercise, you should fork this repository 
and push code early and often during the course. The course 
guidelines PDF explains the submission process in detail, but please 
contact an instructor if you have any questions.
