!SLIDE

# Mass Assignment Security #

## Inherited from ActiveModel ##

!SLIDE

    @@@Ruby
    attr_protected :_id
    attr_accessible :first_name, 
                    :last_name

!SLIDE code

sanitize_for_mass_assignment(attrs || {}).each_pair do |key, value|
  ......
  write_attribute(key, value)
  ......
end
