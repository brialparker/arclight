[![Build Status](https://travis-ci.org/sul-dlss/arclight.svg?branch=master)](https://travis-ci.org/sul-dlss/arclight)
[![Code Climate Test Coverage](https://codeclimate.com/github/sul-dlss/arclight/badges/coverage.svg)](https://codeclimate.com/github/sul-dlss/arclight/coverage)

# Arclight

A Rails engine supporting discovery of archival materials.

During April - June 2017, ArcLight underwent its initial development as a Minimally Viable Product (MVP). The MVP is targeted for content that is described in the [Encoded Archival Description](http://eadiva.com/2/) (EAD) format. Future development is in the planning phase with no definitive timeline as yet.

## Requirements

* [Ruby](https://www.ruby-lang.org/en/) 2.2 or later
* [Rails](http://rubyonrails.org) 5.0 or later

## Installation

[Installing ArcLight](https://github.com/sul-dlss/arclight/wiki/Creating,-installing,-and-running-your-ArcLight-application) is straightforward in a Rails environment.

Basically, add this line to your application's `Gemfile`:

```ruby
gem 'arclight'
```

And then execute:

```sh
$ bundle
```

Or install it yourself as:

```sh
$ gem install arclight
```

For further details, see our [Installing ArcLight](https://github.com/sul-dlss/arclight/wiki/Creating,-installing,-and-running-your-ArcLight-application) documentation.

## Usage

Arclight is a Ruby gem designed to work with archival data. It can be installed on a server or virtual server. Once running, finding aids in the form of archival collection data can be imported into Arclight through an indexing process. Institutional and repositories data can also be added to Arclight (Currently this requires a developer. Configuration pages will be added for this in future versions). Additional finding aids can be added at any time.

After data indexing, Arclight can to be used to search, browse, and display the repositories (sets of collections), collections, and components within collections. Globally available search allows filtering on several types of terms (Keyword, Name, Place, etc.). Once a search is begun, it can be further narrowed using facets on the left side of the search page. Selecting a search result goes directly to that results show or display page. Also global available are buttons for Repositories and Collections which can be used an any time.

Browsing allows you to view the Overview or Contents (when it exists) of a collection. The Overview tab displays top level metadata about the collection. The Contents tab displays an outline view of a next level of the collection. You can expand each level by selecting (clicking). Selecting a component in the Contents views goes to a component page which shows the metadata for it.

Some pages include an inline view tab to the right of an item which will expand the Contents further.

See the [ArcLight demo](https://arclight-demo.projectblacklight.org/) and [ArcLight MVP Wiki](https://github.com/sul-dlss/arclight/wiki) for usage.

See [Arclight Major Features](https://github.com/sul-dlss/arclight/wiki/Arclight-Major-Features) for a list of features.

## Resources

* General
  * [ArcLight team wiki](https://wiki.duraspace.org/display/hydra/ArcLight): includes design process documentation
  * Use the [ArcLight Google Group](http://groups.google.com/d/forum/arclight-community) to contact us with questions
* MVP Implementation:
  * [ArcLight demo site](https://arclight-demo.projectblacklight.org/)
  * [YouTube channel](https://www.youtube.com/channel/UCbSaP93HdypsW6hXy7V1nFQ): MVP sprint demo videos
  * [ArcLight MVP Wiki](https://github.com/sul-dlss/arclight/wiki)
  * [Blacklight wiki](https://github.com/projectblacklight/blacklight/wiki)

## ArcLight MVP Development team

* Stanford University
  * [Camille Villa](https://github.com/camillevilla)
  * [Darren Hardy](https://github.com/drh-stanford)
  * [Gary Geisler](https://github.com/ggeisler)
  * [Jack Reed](https://github.com/mejackreed)
  * [Jennifer Vine](https://github.com/jvine)
  * [Jessie Keck](https://github.com/jkeck)
  * [Mark Matienzo](https://github.com/anarchivist)
* University of Michigan
  * [Gordon Leacock](https://github.com/gordonleacock)

## Development

ArcLight development uses [`solr_wrapper`](https://rubygems.org/gems/solr_wrapper/versions/0.18.1) and [`engine_cart`](https://rubygems.org/gems/engine_cart) to host development instances of Solr and Rails server on your local machine.

### Run the test suite

Ensure Solr and Rails are _not_ running (ports 8983 and 3000 respectively), then:

```sh
$ bundle exec rake
```

### Run a development server

```sh
$ bundle exec rake arclight:server
```

Then visit http://localhost:3000. It will also start a Solr instance on port 8983.

### Run a console

You can also run `bin/console` for an interactive prompt that will allow you to experiment.

### Release a new version of the gem

To release a new version:

1. Update the version number in `lib/arclight/version.rb`
2. Run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, build the gem file (e.g., `gem build arclight.gemspec`) and push the `.gem` file to [rubygems.org](https://rubygems.org) (e.g., `gem push arclight-x.y.z.gem`).

## Contributing

[Bug reports](https://github.com/sul-dlss/arclight/issues) and [pull requests](https://github.com/sul-dlss/arclight/pulls) are welcome on ArcLight -- see [CONTRIBUTING.md](https://github.com/sul-dlss/arclight/blob/master/CONTRIBUTING.md) for details.
## License

The gem is available as open source under the terms of the [Apache 2 License](https://opensource.org/licenses/Apache-2.0).
