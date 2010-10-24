!SLIDE

# Querying #

!SLIDE smaller

# Finders #

    @@@Ruby
    Person.all(:conditions => { :name => "Syd" })
    Person.find(:all, 
                :conditions => { :name => "Syd" })

    Person.first(:conditions => { :name => "Syd" })
    Person.find(:first, 
                :conditions => { :name => "Syd" })

    Person.last(:conditions => { :name => "Syd" })
    Person.find(:last, 
                :conditions => { :name => "Syd" })

!SLIDE smaller

# Finders #

    @@@Ruby
    Person.all_in(:aliases => [ "Jeffrey", "The Dude" ])
    Person.any_in(:status => ["Single", "Divorced", "Separated"])
    Person.any_of({ :status => "Single" }, { :preference => "Open" })
    Person.and(:age.gt => 18, :gender => "Male")
    Person.where(:status => "Married").count
    Person.excludes(:status => "Married")
    Person.criteria.id("4b2fe28ee2dc9b5f7b000029")
    Address.near(:position => [ 37.7, -122.4, 10 ])
    Person.not_in(:status => ["Divorced", "Single"])
    Person.only(:first_name, :last_name)

!SLIDE smaller

# Finders #

    @@@Ruby
    Person.desc(:last_name).asc(:first_name)
    Person.descending(:last_name).ascending(:first_name)
    Person.order_by(:last_name.desc, :first_name.asc, :city.desc)
    Person.order_by([[:last_name, :desc], [:first_name, :asc]])

!SLIDE smaller

# Finders #

    @@@Ruby
    Person.limit(20)
    Person.skip(100)

!SLIDE smaller

# Finders #

    @@@Ruby
    Person.where(:age.gt => 18, :gender => "Male")
    Person.where(:last_name => /^Jord/)
    Person.where(:age.gt => 18, :age.lt => 30)

!SLIDE bullets

# Criteria #

* core for finders
* lazy finders
* chainable scope

!SLIDE center

![Criteria](criteria1.png)

!SLIDE

Person.find(:all, :conditions => { :name => "Syd" })

selector: { :name => "Syd" }
options: nil

!SLIDE

Person.any_in(:status => ["Single", "Divorced", "Separated"])

selector: {:status=>{"$in"=>["Single", "Divorced", "Separated"]}}
options: nil

!SLIDE

Person.any_of({:status => "Single"}, {:preference => "Open"})

selector: {"$or"=>[{:status=>"Single"}, {:preference=>"Open"}]}
options: nil

!SLIDE

Person.desc(:last_name).asc(:first_name)

selector: nil
options: {:sort=>[[:last_name, :desc], [:first_name, :desc]]}

!SLIDE

Person.limit(20).skip(100)

selector: nil
options: {:limit=>20, :skip=> 100}

!SLIDE

Person.where(:age.gt => 18, :age.lt => 30)

selector: nil
options: { :age => [{"$gt" => 18}, { "$lt" => 30 }] }
