!SLIDE subsection

# Sharing behavior

!SLIDE

# 1. Inheritance

!SLIDE

    @@@ ruby
    class Animal
      
      def walk
        ...
      end
  
    end

!SLIDE

    @@@ ruby
    class Animal < Object
      
      def walk
        ...
      end
  
    end


!SLIDE

    @@@ ruby
    class Dog < Animal
      
    end
    
!SLIDE

    @@@ ruby
    keiser = Dog.new
    
    keiser.walk
    
!SLIDE

# Animals and People can walk, let's share that behavior

!SLIDE

# 2. Mix-ins

!SLIDE

    @@@ ruby
    module Walker
      
      def walk
        'walking...'
      end
      
    end
    
!SLIDE

    @@@ ruby
    
    Walker.class # => Module
    
!SLIDE

# **Modules** are objects too

!SLIDE

## Bringing module methods as instance methods

!SLIDE

    @@@ ruby
    
    class Animal
      
      include Walker
    
    end

    class Person

      include Walker

    end

!SLIDE

    @@@ ruby
    Animal.new.walk # => 'walking...'

!SLIDE

    @@@ ruby
    Person.new.walk # => 'walking...'

!SLIDE

## Bringing module methods as class methods

!SLIDE

    @@@ ruby

    class Animal

      extend Walker

    end

    class Person

      extend Walker

    end

!SLIDE

    @@@ ruby
    Animal.walk # => 'walking...'

!SLIDE

    @@@ ruby
    Person.walk # => 'walking...'

!SLIDE subsection

# Classes can be re-opened

!SLIDE

    @@@ ruby
    "ruby".decorate # => undefined method

!SLIDE
    @@@ ruby
    class String
      
      def decorate

        "**_ #{self} _**"

      end
      
    end

!SLIDE
    
    @@@ ruby
    "ruby".decorate
    
    # => "**_ ruby _**"

!SLIDE
    @@@ ruby
    1000.decorate
    
    # => undefined method 'decorate'
    
!SLIDE

    @@@ ruby
    class Object

      def decorate

        "**_ #{self} _**"

      end

    end

!SLIDE

    @@@ ruby
    "ruby".decorate

    # => "**_ ruby _**"

!SLIDE
    @@@ ruby
    1000.decorate

    # => "**_ 1000 _**"

!SLIDE
    @@@ ruby
    :post.decorate

    # =>  "**_ post _**"

!SLIDE
    @@@ ruby
    %w/ruby on rails/.decorate

    # => "**_ ["ruby", "on", "rails"] _**"

!SLIDE 

#Using *mix-ins* to add features to certain classes

!SLIDE
    @@@ ruby
    module Decorable
      
      def decorate

        "**_ #{self} _**"

      end

    end

!SLIDE

    @@@ ruby
    class String

      include Decorable

    end

!SLIDE

    @@@ ruby
    class Fixnum

      include Decorable

    end
    
!SLIDE

    @@@ ruby
    class ClassOnSteroids

      include TextUtil, Loggeable, MyHelper

      extend Configurable, Loggeable

    end
