# Prawn::Emoji

[![Gem Version](https://badge.fury.io/rb/prawn-emoji.svg)](https://badge.fury.io/rb/prawn-emoji)
[![Build Status](https://travis-ci.org/hidakatsuya/prawn-emoji.svg)](https://travis-ci.org/hidakatsuya/prawn-emoji)
[![Maintainability](https://api.codeclimate.com/v1/badges/edcd23ef38c2e393513b/maintainability)](https://codeclimate.com/github/hidakatsuya/prawn-emoji/maintainability)

Prawn::Emoji is an extention for [Prawn](https://github.com/prawnpdf/prawn), provides feature for drawing Emoji.

## Fork info

In this fork the emoji images are provided by Noto Color Emoji.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'prawn-emoji', require: false
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install prawn-emoji

## Usage

In order to run the following code, you need to place both [DejaVuSans.ttf](http://sourceforge.net/projects/dejavu/) and [ipag.ttf](http://ipafont.ipa.go.jp/old/ipafont/download.html) in the same directory as the script file.

```ruby
require 'prawn'
require 'prawn/emoji'

Prawn::Document.generate 'foo.pdf' do
  font 'DejaVuSans.ttf'
  text '🐟 + 🔪 = 🍣'

  font 'ipag.ttf'
  text_box '🍣が食べたい', at: [100, 100], width: 300

  draw_text '🍣🍣🍣🍣🍣', at: [100, 200]
end
```


### IMPORTANT

In order to draw emoji, you must use a TTF - True Type Font. I recommend you use a Japanese font.

## Feature

  * Emoji is provided by Noto Color Emoji https://www.google.com/get/noto/help/emoji/
  * Multi-character emoji support
  * RTL support
  * Character spacing support
  * Rotation support
  * Alignment support
  * Font size support

### Known Issues

See [prawn-emoji/issues](https://github.com/hidakatsuya/prawn-emoji/labels/known%20issue)

## Supported versions

See also https://travis-ci.org/hidakatsuya/prawn-emoji.

### Ruby

2.1, 2.2, 2.3, 2.4, 2.5

### Prawn

2.1, 2.2

INFO: Version 1.x supports Prawn 1.3 and 2.0. See [README in 1.0-stable branch](https://github.com/hidakatsuya/prawn-emoji/blob/1.0-stable/README.md).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/hidakatsuya/prawn-emoji.

### How to update `emoji/index.yml`

If you update emoji image in `emoji/images`, you need to update `emoji/index.yml` to run the following task:

```
$ bundle exec rake emoji:generate_index
```

## Credit

### Noto Color Emoji

Emoji provided free by [Noto Color Emoji](https://www.google.com/get/noto/help/emoji/).

### IPA Font

[IPA Font License Agreement v1.0](http://ipafont.ipa.go.jp/ipa_font_license_v1.html)

## License

© 2015 Katsuya HIDAKA. See MIT-LICENSE for further details.
