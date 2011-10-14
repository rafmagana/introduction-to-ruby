!SLIDE subsection

#Numbers

!SLIDE
    @@@ ruby
    1.odd? # => true

!SLIDE
    @@@ ruby
    1.even? # => false

!SLIDE
    @@@ ruby
    1.next # => 2

!SLIDE
    @@@ ruby
    1.next.next # => 3

!SLIDE
    @@@ ruby
	  1 + 9 # => 10

!SLIDE
    @@@ ruby
      1.+ 9 # => 10

!SLIDE

## **There are no operators in Ruby**

!SLIDE center

# **Operators are methods!**

![Amazed](../_images/surprised_baby.jpg)

!SLIDE
    @@@ ruby
    1.class # => Fixnum

!SLIDE

    @@@ ruby
    Fixnum.instance_methods

    # => [:*, :+, :-, :/, :**,...]

!SLIDE
    @@@ ruby
    0.0025.class # => Float

!SLIDE

    @@@ ruby
    Float.instance_methods

    # => [:*, :+, :-, :/, :**,...]

!SLIDE

# Type conversions

!SLIDE

    @@@ ruby
    2.5.to_i # => 2

!SLIDE

    @@@ ruby
    2.5.to_i # => 2

    2.5.to_i.class # => Fixnum

!SLIDE

    @@@ ruby
    2.to_f # => 2.0

!SLIDE

    @@@ ruby
    2.to_f # => 2.0

    2.to_f.class # => Float

!SLIDE

# **Fixnum class API**

<a href='http://www.ruby-doc.org/core-1.9.2/Fixnum.html'
target='_blank'>http://www.ruby-doc.org/core-1.9.2/Fixnum.html</a>

# **Float class API**

<a href='http://www.ruby-doc.org/core-1.9.2/Float.html'
target='_blank'>http://www.ruby-doc.org/core-1.9.2/Float.html</a>
