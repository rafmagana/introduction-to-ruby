!SLIDE subsection

#Ranges

!SLIDE bullets incremental

#Ranges

* Represents an interval
* A set of values with a **start** and an **end**

!SLIDE
    @@@ ruby
    1..10

!SLIDE
    @@@ ruby
    (1..10).to_a 
    
    # => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

!SLIDE
    @@@ ruby
    1...10

!SLIDE
    @@@ ruby
    (1...10).to_a 
    
    # => [1, 2, 3, 4, 5, 6, 7, 8, 9]

!SLIDE
    @@@ ruby
    'a'..'e'

!SLIDE
    @@@ ruby
    ('a'..'e').to_a

    # => ["a", "b", "c", "d", "e"]

!SLIDE
    @@@ ruby
    ('a'..'e').include? 'c' # => true

!SLIDE
    @@@ruby
    rate = 45

    case rate
      when 0...10   then "Lowest rate"
      when 10...50  then "Low rate"
      when 50...90  then "High rate"
      when 90...100 then "Highest rate"
    end

    # => "Low rate"
    
!SLIDE
    @@@ ruby
    (0...10).class # => Range

!SLIDE
    @@@ ruby
    Range.instance_methods

    [:first, :last, :include?, :step, ...]

!SLIDE

# **Range class API**

<a href="http://www.ruby-doc.org/core-1.9.2/Range.html"
target="_blank">http://www.ruby-doc.org/core-1.9.2/Range.html</a>
