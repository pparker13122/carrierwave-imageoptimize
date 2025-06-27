# Carrierwave Imageoptimize [![CircleCI](https://dl.circleci.com/status-badge/img/gh/pparker13122/carrierwave-imageoptimize/tree/main.svg?style=svg)](https://dl.circleci.com/status-badge/redirect/gh/pparker13122/carrierwave-imageoptimize/tree/main)
This gem allows you to optimize [CarrierWave](https://github.com/carrierwaveuploader/carrierwave) images using the [image_optim](https://github.com/toy/image_optim) gem.


## What about carrierwave-imageoptim?

This is a **community-maintained fork** of the original [`carrierwave-imageoptim`](https://github.com/nifuramu/carrierwave-imageoptim), which appears to be no longer maintained.

## Installation
Add this line to your application's Gemfile:

```ruby
gem 'carrierwave-imageoptimize'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install carrierwave-imageoptimize

## Usage
To add image optimization to your CarrierWave uploader, first include the module:

```ruby
class MyUploader < CarrierWave::Uploader::Base
  include CarrierWave::ImageOptimize
  ...
end
```

Then apply to all versions via:

```ruby
class MyUploader < CarrierWave::Uploader::Base
  include CarrierWave::ImageOptimize

  process optimize: [{
    jpegoptim: true,
    optipng: true,
    gifsicle: true
  }]
end
```

Or to a single image version via:

```ruby
class MyUploader < CarrierWave::Uploader::Base
  include CarrierWave::ImageOptimize

  version :thumbnail do
    process optimize: [{
      jpegoptim: true,
      optipng: true,
      gifsicle: true
    }]
  end
end
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
