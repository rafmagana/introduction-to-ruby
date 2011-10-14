!SLIDE

# The **Ruby Core** and <br />**Standard Library**

!SLIDE bullets incremental

# **The Ruby Core**

* Base classes and modules
* Don't need to require them manually
* Written in C

!SLIDE bullets incremental

# **The Ruby Core**

* Strings
* Numbers (integers, floats)
* Arrays
* Hashes
* Regular expressions
* Threads
* Times and date
* ...and many more

!SLIDE bullets incremental

# **The Ruby Standard Library** (StdLib)

* Additional packages
* Included in the standard Ruby distribution
* Need a manual require
* Written mostly in Ruby, C or both

!SLIDE bullets incremental

# **The Ruby Standard Library** (StdLib)

* *Benchmark* <span class='small'>(Used time report)</span>
* *OptionParser* <span class='small'>(Command-line option analysis)</span>
* *Logger* <span class='small'>(Simple logging mechanism)</span>
* *Net::HTTP* <span class='small'>(Access WWW docs via HTTP)</span>
* *YAML* <span class='small'>(human-readable data serialization format)</span>
* *Test::Unit* <span class='small'>(Unit testing framework)</span>
* *WEBrick* <span class='small'>(HTTP web server)</span>

!SLIDE

    @@@ ruby
    require 'yaml'
    require 'benchmark'
    require 'logger'

!SLIDE center bullets incremental

# **RubyGems**
## package management framework

* *APT* (apt-get in Debian linux)
* *PECL* and *PEAR* (PHP)
* *PyPi* (Python)
* *CPAN* (Perl)

!SLIDE bullets incremental

# **Gems**

* *Rake* <span class='small'>(Build tool)</span>
* *Bundler* <span class='small'>(Gem dependency management framework)</span>
* *Rails* <span class='small'>(Web application framework)</span>
* *Unicorn* <span class='small'>(HTTP server)</span>
* *Capistrano* <span class='small'>(Web application deployment framework)</span>

!SLIDE
    @@@ bash
    $ gem install rake

!SLIDE
    @@@ bash
    $ gem install bundler -v 1.0.21

!SLIDE
    @@@ bash
    $ gem install rails -v 3.1.1

!SLIDE

# **Core API**

<a href='http://www.ruby-doc.org/core/' target='_blank'>http://www.ruby-doc.org/core/</a>

# **StdLib API**

<a href='http://www.ruby-doc.org/stdlib/' target='_blank'>http://www.ruby-doc.org/stdlib/</a>

# **RubyGems**

<a href='http://www.rubygems.org' target='_blank'>http://www.rubygems.org</a>
