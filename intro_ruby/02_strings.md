!SLIDE subsection

# Strings

!SLIDE
    @@@ ruby
    'lorem'.capitalize # => 'Lorem'

!SLIDE
    @@@ ruby	
    'Ruby on Rails'.include? 'Ruby' # => true

!SLIDE
    @@@ ruby
    'Ruby on Rails'[8..12] # => 'Rails'

!SLIDE

## Strings without interpolation (single quote)

    @@@ ruby
    'my string without interpolation'

!SLIDE

## Strings with interpolation (double quote)

    @@@ ruby
    var = 'interpolation'

    "my string with #{var}"

    # => "my string with interpolation"

!SLIDE

## Strings with interpolation (double quote)

    @@@ ruby
    "This is year #{2000 + 11}"

    # => "This is year 2011"

!SLIDE
    @@@ ruby
    'Ruby'.class # => String

!SLIDE
    @@@ ruby
    language = String.new 'Ruby'

!SLIDE
    @@@ ruby
    language = String.new 'Ruby'

    language # => 'Ruby'

!SLIDE
    @@@ ruby
     String.instance_methods

    [:reverse, :capitalize, :upcase, :downcase]

!SLIDE

## *String* is a class

    @@@ ruby
    'string'.class # => String

!SLIDE

## *String* is an object too, a class object

    @@@ ruby
    String.class # => Class (instance of...)

!SLIDE
    @@@ ruby
    String = Class.new

!SLIDE

    @@@ruby
    Class.instance_methods

    # => [:new, :class, :superclass, ...]

!SLIDE
    @@@ ruby
    class Class < Object

      ...

    end

!SLIDE


# **Class class API**

<a href='http://www.ruby-doc.org/core-1.9.2/Class.html'
target='_blank'>http://www.ruby-doc.org/core-1.9.2/Class.html</a>

# **String class API**

<a href='http://www.ruby-doc.org/core-1.9.2/String.html'
target='_blank'>http://www.ruby-doc.org/core-1.9.2/String.html</a>
