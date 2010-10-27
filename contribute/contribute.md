!SLIDE

# Contribute #

## As you have a brief about mongoid, you can try to fix bugs or add features to mongoid ##

!SLIDE

# My work #

## mongoid-eager-loading ##

* as a [pull request][0] originally
* as a [gem][1] temporarily now

!SLIDE

# Eager Loading #

    @@@Ruby
    Post.includes(:user)
    Comment.includes(:post, :user)
    
!SLIDE

# Benchmark #

Starting benchmark...
                                                                  user     system      total        real
Finding 10 posts with person, without eager loading           0.010000   0.000000   0.010000 (  0.006538)
Finding 10 posts with person, with eager loading              0.000000   0.000000   0.000000 (  0.005235)
Finding 50 posts with person, without eager loading           0.020000   0.000000   0.020000 (  0.027912)
Finding 50 posts with person, with eager loading              0.020000   0.000000   0.020000 (  0.020103)
Finding 100 posts with person, without eager loading          0.040000   0.000000   0.040000 (  0.055197)
Finding 100 posts with person, with eager loading             0.030000   0.010000   0.040000 (  0.040644)

!SLIDE

# Fork it! #

[0]: https://github.com/mongoid/mongoid/pull/391
[1]: http://github.com/flyerhzm/mongoid-eager-loading