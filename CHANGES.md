1.2.2
-----

* Fixes a bug in sorting abstract classes (Issues #54, #88)

1.2.1
-----

* Fixes a bug in OS detection for JRuby (and newer MRI Rubies, too)

1.2.0
-----

* Fixed bug that prevented generation of diagrams on newer versions of OSX
* Added ability to store CLI configuration options in a config file, both a global version (in the user's home directory) as well as a per-project local versions
* Added a Code of Conduct for the project

1.1.1
-----

* Make edge colours optional (pass in --colour to turn them on)

1.1.0.1
-----

* Skips a relationship where source or destination is nil
* Checking entity by model name
* Checks that a model is not abstract before all
* Correct 'No entities found' error

1.1.0
-----

* Abstract models (with 'self.abstract_class = true') are now considered for
  the domain and will be displayed if 'polymorphism=true'. This should also
  fix errors that could occur if abstract models had any associations.
* Correctly save Graphviz diagrams with spaces in the filename (contributed by
  Neil Chambers).
* Add only/exclude to CLI (contributed by Dru Ibarra).

1.0.0
-----

* The internal API is now stable and will be backwards compatible until
  the next major version.
* Added experimental command line interface (erd). The CLI still requires a
  Rails application to be present, but it may one day support other kinds of
  applications.
* Crow's foot notation (also known as the Information Engineering notation)
  can be used by adding 'notation=crowsfoot' to the 'rake erd' command
  (contributed by Jeremy Holland).
* Filter models by using the only or exclude options (only=ModelOne,ModelTwo
  or exclude=ModelThree,ModelFour) from the command line (contributed by
  Milovan Zogovic).
* Process column types that are unsupported by Rails (contributed by Erik
  Gustavson).
* Ignore custom limit/scale attributes that cannot be converted to an integer
  (reported by Adam St. John).

0.4.5
-----

* Display more helpful error message when the application models could not be
  loaded successfully by the 'rake erd' task (reported by Greg Weber).

0.4.4
-----

* Added the ability to disable HTML markup in node labels (markup=false). This
  causes .dot files to be compatible with OmniGraffle, which otherwise fails
  to import graphs with HTML node labels (issue reported by Lucas Florio,
  implementation based on template by Troy Anderson).
* Prevent models named after Graphviz reserved words (Node, Edge) from causing
  errors in .dot files (reported by gguthrie).
* Improved error messages when Graphviz is throwing errors (reported by
  Michael Irwin).

0.4.3
-----

* Display the scale of decimal attributes when set. A decimal attribute with
  precision 5 and scale 2 is now indicated with (5,2).
* Fixed deprecation warnings for edge Rails (upcoming 3.1).

0.4.1
-----

* Fix processing of associations with class_name set to absolute module paths.
* Adjust model loading process to include models in non-standard paths eagerly.

0.4.0
-----

* Support to optionally display single table inheritance relationships
  (inheritance=true).
* Support to optionally display polymorphic associations (polymorphism=true).
* Adjustments to 'advanced' style so that it matches original Bachman style,
  and therefore now called 'bachman'.
* Ignore models without tables (reported by Mark Chapman).
* Mutual indirect relationships are now combined.
* Changed API for diagram generation.
* Restructured classes and renamed several API properties and methods.
* Added new edge type to describe single table inheritance and polymorphic
  associations: Specialization.
* Added compatibility for Active Record 3.1 (beta), removed dependency on Arel.
* Rubinius compatibility.

0.3.0
-----

* Added the ability to support multiple styles of cardinality notations.
  Currently supported types are 'simple' and 'advanced'.
* Added option to exclude indirect relationships (indirect=false).
* Added option to change or disable the diagram title (title='Custom title').
* Altered the type descriptions of attributes.
* Renamed options for flexibility and clarity.
* Improved internal logic to determine the cardinality of relationships.
* More versatile API that allows you to inspect relationships and their
  cardinalities.
* Changed line widths to 1.0 to avoid invisible node boundaries with older
  versions of Graphviz (reported by Mike McQuinn).
* Bundled examples based on actual applications.

0.2.0
-----

* Added simple way to create your own type of diagrams with a tiny amount of code.
* Improved internal API and documentation.
* Subtle changes in diagram style.
* Fixed error where non-mutual relationships might be inadvertently classified
  as indirect relationships.
* Fixed error where diagrams with a vertical layout might fail to be generated.

0.1.1
-----

* Fixed small errors in Ruby 1.8.7.
* Abort generation of diagrams when there are no models.

0.1.0
-----

* Released on September 20th, 2010.
* First public release.
