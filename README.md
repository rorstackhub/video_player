# Video player for Youtube, Vimeo, İzlesene and  Wistia
[![Gem Version](https://badge.fury.io/rb/video_player.svg)](http://badge.fury.io/rb/video_player)

Create video player for Youtube, Vimeo, İzlesene and Wistia videos for Ruby.

And it may support more video hoster with your [contributions](#contributing).

## Installation

Add it to your Gemfile:

```ruby
gem 'video_player'
```

and run on terminal:

    $ bundle

or install the gem on terminal.

    $ gem install video_player

## Parameters

**url**

> Youtube, Vimeo, İzlesene and Wistia video link
>
> http://www.youtube.com/watch?v=iEPTlhBmwRg
>
> or
>
> http://vimeo.com/101419884
>
> or
>
> http://www.izlesene.com/video/feder-goodbye-feat-lyse/7886121
>
> or
>
> https://<subdomain>.wistia.com/medias/9ub91enoph

**width** *(default  = 420)*

**height** *(default  = 315)*

**autoplay** *(default  = true)* - works only on Youtube


## Usage

```ruby
require 'video_player' # if you're not use Rails 4
VideoPlayer::player("http://vimeo.com/101419884")
# returns iframe player from Vimeo video
#   <iframe width=\"420\" height=\"315\"
#           src=\"//player.vimeo.com/video/101419884\"
#           frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

VideoPlayer::player("http://www.youtube.com/watch?v=iEPTlhBmwRg", "1200", "800", true)
# returns iframe player which has 1200px width and 800px height with autoplay from Youtube video
#   <iframe width=\"1200\" height=\"800\"
#           src=\"//www.youtube.com/embed/iEPTlhBmwRg?autoplay=1&rel=0\"
#           frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

VideoPlayer::player("http://www.izlesene.com/video/feder-goodbye-feat-lyse/7886121")
# returns iframe player from İzlesene video
#   <iframe width=\"420\" height=\"315\"
#           src=\"//www.izlesene.com/embedplayer/7886121/?autoplay=1&showrel=0&showinfo=0\"
#           frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

VideoPlayer::player("https://example.wistia.com/medias/9ub91enoph")
# returns iframe player from Wistia video
#   <iframe width=\"420\" height=\"315\"
#           src=\"//fast.wistia.net/embed/iframe/9ub91enoph/?autoplay=1&showrel=0&showinfo=0\"
#           frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
```

It gets you only raw data. You must handle it on erb, haml, slim, etc for output without HTML escaping.

```ruby
video = VideoPlayer::player("http://vimeo.com/101419884")

# erb
<%= video.html_safe %>

# haml, slim
= video.html_safe
# or
== video
```


<a name="contributing"></a>
## Contributing
1. Fork it ( https://github.com/tgezginis/video_player/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Extend the specs, run with `rake`
4. Commit your changes (`git commit -am 'Add some feature'`)
5. Push to the branch (`git push origin my-new-feature`)
6. Create a new Pull Request

**Thanks**
[mikel](https://github.com/mikel)
[foxgaocn](https://github.com/foxgaocn)
