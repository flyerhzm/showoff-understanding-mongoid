!SLIDE 

# Understanding Mongoid #

!SLIDE

# Me #

!SLIDE center bullets

# Richard Huang (黄志敏) #

![Richard Huang](richard.png)

* <http://github.com/flyerhzm>
* <http://twitter.com/flyerhzm>

!SLIDE bullets

* author of <a href="http://github.com/flyerhzm/bullet">bullet</a> and <a href="http://github.com/flyerhzm/rails_best_practices">rails_best_practices</a>
* founder of <http://rails-bestpractices.com>

!SLIDE

# Mongodb #

## The Best Features of Document Databases, Key-Value Stores, and RDBMSes. ##

!SLIDE

# Mongoid #

## Mongoid provides an elegant way to persist and query Ruby objects to documents in MongoDB. ##

!SLIDE center

![Compare with ActiveRecord](comparison.png)

!SLIDE

# Document #

    @@@ Ruby
    class Person
      include Mongoid::Document
      field :first_name
      field :middle_initial
      field :last_name
      field :birthday, :type => Date
      field :blood_alcohol_level,
            :type => Float, 
            :default => 0.0
    end

!SLIDE
include
  ActiveModel
    Conversion
    Naming
    Serialization
    MassAssignmentSecurity
    Serializers::JSON
    Serializers::Xml
  Mongoid
    Associations
    Atomicity
    Attributes
    Collections
    Dirty
    Extras
    Fields
    Hierarchy
    Indexes
    JSON
    Keys
    Matchers
    Memoization
    Modifiers
    MultiParameterAttributes
    Paths
    Persistence
    Safety
    Validations
extend
  ActiveModel
    Translation
  Mongoid
    Finders
    NamedScope