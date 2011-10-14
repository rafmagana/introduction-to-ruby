!SLIDE subsection

# Arrays

!SLIDE bullets center

# **Arrays**

## *Ordered, integer-indexed collections of any object*

!SLIDE small

    @@@ ruby
    colors = ["cyan", "magenta", "yellow", "black"]

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    # => ["cyan", "magenta", "yellow", "black"]

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors[0] # => "cyan"

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors.first # = > "cyan"
        
!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors[1,2] # => ["magenta", "yellow"]

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors[-1] # => "black"

!SLIDE

    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors.last # => "black"

!SLIDE

    @@@ ruby    
    colors = %w/cyan magenta yellow black/

    colors[1..2] # => ["magenta", "yellow"]

!SLIDE
    @@@ ruby
    colors = %w(cyan magenta yellow black)

    colors[2..-1] # => ["yellow", "black"]

!SLIDE
    @@@ ruby
    colors = %w[cyan magenta yellow black]

    colors[2...-1] # => ["yellow"]

!SLIDE
    @@@ ruby
    colors.class # => Array

!SLIDE
    @@@ ruby
    Array.instance_methods
    
    [:[], :[]=, :*, :+, :-, :<<, :each, ...]

!SLIDE

## Square brackets are methods, nothing more!

!SLIDE
    @@@ ruby
    colors = %w/cyan magenta yellow black/
    
    colors[1..2] # => "black"

!SLIDE
    @@@ ruby
    colors = %w/cyan magenta yellow black/
    
    colors.[](1..2) # => "black"

!SLIDE
    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors[1] = 'white'

!SLIDE
    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors.[]=(1, 'white')

!SLIDE
    @@@ ruby
    colors = %w/cyan magenta yellow black/

    colors.[]=(1, 'white')
    
    ["cyan", "white", "yellow", "black"]

!SLIDE
    @@@ ruby
    cmyk = %w(cyan magenta yellow black)
    
    rgb = %w{red green black}

!SLIDE
    @@@ ruby
    rgb * 2
    
    ["red", "green", "black",
     "red", "green", "black"]

!SLIDE
    @@@ ruby
    rgb_and_cmyk = rgb + cmyk
    
    ["red", "green", "black", 
     "cyan", "magenta", "yellow", "black"]

!SLIDE
    @@@ ruby
    rgb_and_cmyk.uniq
    
    ["red", "green", "black", 
     "cyan", "magenta", "yellow"]

!SLIDE
    @@@ ruby
    http = %w{hyper text transfer protocol}

!SLIDE
    @@@ ruby
    http = %w{hyper text transfer protocol}

    http.collect { |w| w[0].capitalize }

!SLIDE
    @@@ ruby
    http = %w{hyper text transfer protocol}

    http.collect { |w| w[0].capitalize }

    # => ["H", "T", "T", "P"]

!SLIDE
    @@@ ruby
    http = %w{hyper text transfer protocol}

    http.collect { |w| w[0].capitalize }.join

    # => "HTTP"

!SLIDE
    @@@ ruby
    known_people = %w{marie hellen yen}
    
    excluded = %w{yen}

!SLIDE
    @@@ ruby    
    invitees = known_people - excluded
    
    # => ["marie", "hellen"]

!SLIDE
    @@@ ruby    
    invitees << "alejandra"

    # => ["marie", "hellen", "alejandra"]

!SLIDE

    @@@ ruby
    
    invitees.each do |friend|
      
       friend.invite()

    end

!SLIDE

    @@@ ruby
    
    invitees.each { |f| f.invite }

!SLIDE

# **Array class API**

<a href='http://www.ruby-doc.org/core-1.9.2/Array.html'>http://www.ruby-doc.org/core-1.9.2/Array.html</a>
