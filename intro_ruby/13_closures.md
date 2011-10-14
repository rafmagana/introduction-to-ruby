!SLIDE supersection

# Closures

!SLIDE center

# Do you remember 
# what blocks are?

!SLIDE center

# **Blocks are** 
# *nameless* **functions**

!SLIDE
    @@@ ruby
    do |param1, param2|

      # code here

    end

!SLIDE
    @@@ ruby
    def name(param1, param2)

      # code here

    end

!SLIDE
    @@@ ruby
    def (param1, param2)

      # code here

    end

!SLIDE center

# **Almost**
# *Everything is an object*

!SLIDE

# *Blocks are* **not** *objects*

!SLIDE center small

# **A block become an object**
# *when we bound it to a variable*

!SLIDE
    @@@ ruby
    my_object = { |params| ... }

!SLIDE
    @@@ ruby
    my_object = { |params| ... }

    # => Syntax error

!SLIDE center

# How do we create
# closures out of blocks?

!SLIDE
    @@@ ruby
    closure = Proc.new { |params|  ... }

!SLIDE
    @@@ ruby
    closure = Proc.new { |params|  ... }

    closure.call 'arg'

!SLIDE
    @@@ ruby
    closure = Proc.new { |param|  ... }

    closure.call 'arg'

    # => result of executing ...

!SLIDE center

# **Blocks are** 
# *nameless* **functions**

!SLIDE center

# **Closures are**
# **nameless function** *objects*

!SLIDE

    @@@ ruby
    closure = Proc.new { |params|  ... }

    closure.class # => Proc

!SLIDE

    @@@ ruby
    Proc.instance_methods

    # => [:call, :binding, :yield,
    # =>  :parameters, :lambda?, ...]

!SLIDE center small

# Closures can be **passed** around 
# as **parameters** and called **later**

!SLIDE center small

# They can refer to **variables** from
# the **context** (binding) in which 
# they were **created** 

!SLIDE center
# Different ways
# to create a closure

!SLIDE
    @@@ ruby
    Proc.new { |params| ... }

!SLIDE
    @@@ ruby
    Proc.new { |params| ... }

    proc { |params| ... }

!SLIDE
    @@@ ruby
    Proc.new { |params| ... }

    proc { |params| ... }

    lambda { |params| ... }

!SLIDE
    @@@ ruby
    Proc.new { |params| ... }.class # => Proc

    proc { |params| ... }.class    # => Proc

    lambda { |params| ... }.class  # => Proc

!SLIDE center

# **Proc.new**/**proc**
## *Closures with optional parameters*

!SLIDE
    @@@ ruby
    closure = proc { |param| param }

!SLIDE
    @@@ ruby
    closure = proc { |param| param }

    closure.call

!SLIDE
    @@@ ruby
    closure = proc { |param| param }

    closure.call # => nil

!SLIDE center

# **lambda**
## *Closures with required parameters*

!SLIDE
    @@@ ruby
    closure = lambda { |param| param }

!SLIDE
    @@@ ruby
    closure = lambda { |param| param }

    closure.call

!SLIDE
    @@@ ruby
    closure = lambda { |param| param }

    closure.call

    # => wrong number of arguments (0 for 1)

!SLIDE
    @@@ ruby
    closure = lambda { |param| param }

    closure.call 'arg' # => 'arg'

!SLIDE center

# Converting closures
# back to blocks

!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

    (3..5).reduce { |p, n| p * n }


!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

    (3..5).reduce { |p, n| p * n }

    # => 60

!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

    (3..5).reduce multiplier

!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

    (3..5).reduce multiplier

    # => wrong number of arguments(1 for 0)

!SLIDE center

# Let's turn it into a **block**
# The **&** to the rescue

!SLIDE
    @@@ ruby
    multiplier = lambda { |p, n| p * n }

    (3..5).reduce &multiplier

    # => 60

!SLIDE
    @@@ ruby
    (1..9).reduce &multiplier # => 362880

    multiplier.call 'b', 5 # => 'bbbbb'

!SLIDE
    @@@ ruby
    ('a'..'c').collect &:capitalize

!SLIDE
    @@@ ruby
    ('a'..'c').collect &:capitalize

    # => ['A', 'B', 'C']

!SLIDE
    @@@ ruby
    :capitalize.class # => Symbol


!SLIDE
    @@@ ruby
    :capitalize.class # => Symbol

    :capitalize.methods # => [:to_proc, ...]

!SLIDE
# **&** calls the *to_proc* method

!SLIDE
    @@@ ruby
    class Symbol

      def to_proc

        proc { |obj| obj.send self }

      end

    end

!SLIDE
    @@@ ruby
    :capitalize.to_proc

!SLIDE
    @@@ ruby
    :capitalize.to_proc

    { |obj| obj.send :capitalize }

!SLIDE
    @@@ ruby
    :capitalize.to_proc

    { |obj| obj.send :capitalize }

    'ruby'.send :capitalize # => 'Ruby'

!SLIDE center

# Working with closures
# in your own methods

!SLIDE
    @@@ ruby
    class MySQL

        private
        def connect
        end

        def disconnect
        end

        public
        def when_connected
          conn = connect
          yield conn if block_given?
          disconnect
        end

    end

!SLIDE
    @@@ ruby
    class MySQL

        private
        def connect
        end

        def disconnect
        end

        public
        def when_connected(&closure)
          conn = connect
          closure.call conn if closure
          disconnect
        end

    end

!SLIDE
    @@@ ruby
    sql = MySQL.new :database => :my_project

!SLIDE
    @@@ ruby
    sql.when_connected do |connection|

      now = connection.query "SELECT NOW();"

      ...

    end
