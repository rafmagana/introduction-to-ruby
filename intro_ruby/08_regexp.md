!SLIDE subsection

#Regular Expressions

!SLIDE
    @@@ ruby
    text = <<MESSAGE
      Hey dude, here is my alternative
      email address: john@doe.com
    MESSAGE

!SLIDE small
    @@@ ruby
    pattern = /(?<name>([\w-]+))@[\w-]+\.+[\w-]+/

!SLIDE small
    @@@ ruby
    text = <<MESSAGE
      Hey dude, here is my alternative
      email address: john@doe.com
    MESSAGE

    matches = pattern.match text

!SLIDE small
    @@@ ruby
    text = <<MESSAGE
      Hey dude, here is my alternative
      email address: john@doe.com
    MESSAGE

    matches = pattern.match text

    # => #<MatchData "john@doe.com" name:"john">

!SLIDE
    @@@ ruby
    matches[:name] # => "john"

!SLIDE
    @@@ ruby
    text = <<MESSAGE
      Hey dude, here is my alternative
      email address: john@doe.com
    MESSAGE

    pattern = /([\w-]+)@[\w-]+\.+[\w-]+/

!SLIDE
    @@@ ruby
    text.scan pattern

    # => [["john"]]

!SLIDE
    @@@ ruby
    text.scan(pattern).flatten

    # => ["john"]

!SLIDE
    @@@ ruby
    text.scan(pattern).flatten.first

    # => "john"

!SLIDE
    @@@ ruby
    /pattern/.class # => Regexp

!SLIDE

# **Regexp class API**

<a href="http://www.ruby-doc.org/core-1.9.2/Regexp.html">http://www.ruby-doc.org/core-1.9.2/Regexp.html</a>

# **MatchData class API**

<a href="http://www.ruby-doc.org/core-1.9.2/MatchData.html">http://www.ruby-doc.org/core-1.9.2/MatchData.html</a>
