!SLIDE

# Validations #
## Inherited from ActiveModel ##

!SLIDE

    @@@Ruby
    validates_acceptance_of
    validates_confirmation_of
    validates_exclusion_of
    validates_format_of
    validates_inclusion_of
    validates_length_of
    validates_numericality_of
    validates_presence_of

!SLIDE

# customized validations #

    @@@Ruby
    validates_associated
    validates_uniqueness_of

!SLIDE smallest

# Implementation #

    @@@Ruby
    def validates_associated(*args)
      validates_with(AssociatedValidator, _merge_attributes(args))
    end

!SLIDE smallest

# Implementation of customized validations #

    @@@Ruby
    module Mongoid
      module Validations
        class AssociatedValidator < ActiveModel::EachValidator
          def validate_each(document, attribute, value)
            values = value.is_a?(Array) ? value : [ value ]
            return if values.collect { |doc| 
              doc.nil? || doc.valid? 
            }.all?
            document.errors.add(attribute, 
                                :invalid, 
                                options.merge(:value => value))
          end
        end
      end
    end
    
