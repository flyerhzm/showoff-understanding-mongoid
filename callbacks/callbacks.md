!SLIDE

# Callbacks #

## Inherited from ActiveModel ##

!SLIDE

    @@@Ruby
    before_create
    before_destroy
    before_save
    before_update
    before_validation
    after_create
    after_initialize
    after_destroy
    after_save
    after_update
    after_validation

!SLIDE

# Implementation #

    @@@Ruby
    extend ActiveModel::Callbacks
    
    define_model_callbacks \
      :create,
      :destroy,
      :initialize,
      :save,
      :update,
      :validation

!SLIDE

    @@@Ruby
    run_callbacks(:initialize) do
      document
    end
    
!SLIDE

    @@@Ruby
    @document.run_callbacks(:create) do
      @document.run_callbacks(:save) do
        ......
      end
    end
