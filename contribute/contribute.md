!SLIDE

# Mongoid is still evolving #

!SLIDE

# Contribute #

## Try to fix bugs or add features to mongoid ##

!SLIDE bullets

# My work #

## mongoid-eager-loading ##

* as a <a href="https://github.com/mongoid/mongoid/pull/391">pull request</a> originally
* as a <a href="http://github.com/flyerhzm/mongoid-eager-loading">gem</a> temporarily now

!SLIDE

# Eager Loading #

    @@@Ruby
    Post.includes(:user)
    Comment.includes(:post, :user)
    
!SLIDE code

# Benchmark #

<p style="line-height:24px">
Finding 10 posts with person, without eager loading       0.010000   0.000000   0.010000 (  0.006538)
Finding 10 posts with person, with eager loading          0.000000   0.000000   0.000000 (  0.005235)
Finding 50 posts with person, without eager loading       0.020000   0.000000   0.020000 (  0.027912)
Finding 50 posts with person, with eager loading          0.020000   0.000000   0.020000 (  0.020103)
Finding 100 posts with person, without eager loading      0.040000   0.000000   0.040000 (  0.055197)
Finding 100 posts with person, with eager loading         0.030000   0.010000   0.040000 (  0.040644)
</p>

!SLIDE

# Fork it! #

