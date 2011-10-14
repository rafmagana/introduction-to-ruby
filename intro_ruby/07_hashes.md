!SLIDE subsection

#Hashes

!SLIDE bullets incremental

# Hashes

* key-based
* dictionaries, maps

!SLIDE
    @@@ ruby
    ages = {"marie" => 17, :hellen => 20}

!SLIDE

    @@@ruby
    ages = Hash[:marie, 17, :hellen, 20]
    
    # => {:marie => 17, :hellen => 20}
    
!SLIDE
    @@@ ruby
    ages[:marie] # => 17

!SLIDE

## Creating empty hashes
    @@@ ruby
    
    languages = {}

!SLIDE
    @@@ ruby
    
    languages[:compiled] = %w{Java Smalltalk}


    languages[:interpreted] = %w{Perl Ruby}

!SLIDE
    @@@ ruby
    languages[:compiled]
    
    # =>  ["Java", "Smalltalk"]

!SLIDE
    @@@ ruby
    languages[:interpreted]
    
    # => ["Perl", "Ruby"]

!SLIDE
# Hashes can be used as keyword arguments

!SLIDE
    @@@ ruby
    def my_method(params = {})

      params[:key1]

      params[:key2]

    end

!SLIDE
    @@@ ruby
    my_method({:key1 => :value1, :key2 => []})

!SLIDE
    @@@ ruby
    my_method :key1 => :value1, :key2 => []


!SLIDE
# You can use *any object as key*, <br />not only strings or symbols

!SLIDE

    @@@ ruby
    
    foo = [1, 2, 3]

!SLIDE
    @@@ ruby
    foo = [1, 2, 3]
    
    bar = Hash[foo, :lorem]

!SLIDE
    @@@ ruby
    foo = [1, 2, 3]
    
    bar = Hash[foo, :lorem]

    # => {[1, 2, 3]=>:lorem}

!SLIDE
    @@@ ruby
    bar[foo] # => :lorem

!SLIDE
    @@@ ruby
    bar[foo] # => :lorem

NOTE: Make sure you read about the *Hash*#rehash method

!SLIDE
    @@@ ruby
    bar.class # => Hash

!SLIDE
    @@@ ruby
    Hash.instance_methods

    ["[]", "[]=", "has_key?", "each", ...]

!SLIDE

# **Hash class API**

<a href="http://www.ruby-doc.org/core-1.9.2/Hash.html" target="_blank">http://www.ruby-doc.org/core-1.9.2/Hash.html</a>
