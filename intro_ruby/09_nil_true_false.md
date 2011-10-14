!SLIDE subsection

# nil, true, false

!SLIDE bullets incremental
 
* **nil** evaluates to **false**
* **false** evaluates to **false**
* **true** and everything else evaluates to **true**

!SLIDE

# **nil** represents nullity, nothing

!SLIDE center

# and again, remember...

!SLIDE center

# **Everything is an object**

!SLIDE center

# yes, **nil** is an object

!SLIDE center

    @@@ ruby
    nil.class # => NilClass

!SLIDE

    @@@ ruby    
    my_object = nil

    my_object.nil? # => true

!SLIDE
    @@@ ruby
    foo = nil

!SLIDE
    @@@ ruby
    foo = nil

    puts "nil evaluates to false" unless foo

!SLIDE
    @@@ ruby
    foo = nil

    puts "nil evaluates to false" unless foo

    # => "nil evaluates to false"

!SLIDE center

# yes, **true** is an object

!SLIDE center

    @@@ ruby
    true.class # => TrueClass
  
!SLIDE

# and, yes, **false** is an object too

!SLIDE center

    @@@ ruby
    false.class # => FalseClass

!SLIDE center

## *NilClass*, *FalseClass* and *TrueClass*
## are singleton classes

!SLIDE center

## *NilClass*, *FalseClass* and *TrueClass*
## are singleton classes

## **cannot be instantiated more than once**

!SLIDE center

# *nil*, *false* and *true* 
# are the unique instances of
# its parent classes

!SLIDE
    @@@ ruby
    my_nil = NilClass.new 

    # => undefined method `new'
