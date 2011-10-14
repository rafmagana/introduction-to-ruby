!SLIDE subsection

#Symbols

!SLIDE

## Duplicated objects

    @@@ ruby
    
    "ruby".object_id # => 2156749500
    
    "ruby".object_id # => 2156743120

!SLIDE

## Avoiding object duplication

    @@@ ruby
    
    :ruby.object_id # => 399368
    
    :ruby.object_id # => 399368

!SLIDE center small

# A *symbol* can return the
# *string representation* of its name

!SLIDE

    @@@ ruby
    
    :ruby.to_s # => "ruby"

!SLIDE

    @@@ ruby
    
    :"ruby on rails".to_s # => "ruby on rails"

!SLIDE

    @@@ ruby
    :ruby.class # => Symbol
    
!SLIDE

# Important fact

!SLIDE

# There is one **symbol**
# for **every method name**
# (:to\_i, :to\_s, :object\_id, etc.)

