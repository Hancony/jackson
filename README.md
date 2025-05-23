<a href="CONTRIBUTING.md" alt="Hacktoberfest"><img src="https://badgen.net/badge/hacktoberfest/friendly/pink" /></a>
 [![Open Source](https://badges.frapsoft.com/os/v3/open-source.svg?v=103)](https://opensource.org/)

# Jackson Project Home @github

This is the home page of the Jackson Project.

## What is New?

* Apr 8, 2025: Minor updates wrt Jackson 3.x
* Sep 26, 2024: Jackson 2.18(.0) (latest stable major) released
* Mar 12, 2024: Jackson 2.17 released
* Feb 19, 2024: Another OSTIF/AdaLogics Security Audit -- on jackson-dataformat-xxx's and jackson-datatype-xxx's -- released: https://ostif.org/dataformatsdatatypes-audit-complete/
* Dec 17, 2023: contributing/[Jackson Coding Style Guide](contribution/jackson-coding-style-guide.md)
* Nov 15, 2023: Jackson 2.16 released
* Apr 23, 2023: Jackson 2.15 released
* Nov 5, 2022: Jackson 2.14 released
* Nov 2, 2022: AdaLogics Security Audit for Jackson released -- see Document/Reports
* Sep 30, 2021: Jackson 2.13 released
* Oct 1, 2020: Jackson participates in [Hacktoberfest2020](https://hacktoberfest.digitalocean.com/) and we have a [Jackson/Hacktoberfest](https://github.com/FasterXML/Hacktoberfest2020) repo too!
* Oct 9, 2020: Added [Contributing](CONTRIBUTING.md)

(note: for up-to-date release info, see [Jackson Releases](../../wiki/Jackson-Releases))

## What is Jackson?

Jackson has been known as "the Java JSON library"
or "the best JSON parser for Java". Or simply as "JSON for Java".

More than that, Jackson is a suite of data-processing tools for Java (and the JVM platform),
including the flagship streaming [JSON](https://en.wikipedia.org/wiki/JSON) parser / generator library,
matching data-binding library (POJOs to and from JSON)
and additional data format modules to process data encoded in
[Avro](https://github.com/FasterXML/jackson-dataformats-binary/blob/2.19/avro),
[BSON](https://github.com/michel-kraemer/bson4jackson),
[CBOR](https://github.com/FasterXML/jackson-dataformats-binary/blob/2.19/cbor),
[CSV](https://github.com/FasterXML/jackson-dataformats-text/blob/2.19/csv),
[Smile](https://github.com/FasterXML/jackson-dataformats-binary/tree/2.19/smile),
[(Java) Properties](https://github.com/FasterXML/jackson-dataformats-text/blob/2.19/properties),
[Protobuf](https://github.com/FasterXML/jackson-dataformats-binary/tree/2.19/protobuf),
[TOML](https://github.com/FasterXML/jackson-dataformats-text/blob/2.19/toml),
[XML](https://github.com/FasterXML/jackson-dataformat-xml)
or [YAML](https://github.com/FasterXML/jackson-dataformats-text/blob/2.19/yaml);
and even the large set of data format modules to support data types of widely used
data types such as
[Guava](../../../jackson-datatypes-collections),
[Joda](../../../jackson-datatype-joda),
[PCollections](../../../jackson-datatypes-collections)
and many, many more (see below).

While the actual core components live under their own projects -- including the three core packages
([streaming](../../../jackson-core), [databind](../../../jackson-databind), [annotations](../../../jackson-annotations));
data format libraries; data type libraries; [JAX-RS provider](../../../jackson-jaxrs-providers);
and a miscellaneous set of other extension modules -- this project act as the central hub
for linking all the pieces together.

A good companion to this README is the [Jackson Project FAQ](../../wiki/FAQ).

## Actively developed versions

Jackson suite has three major versions: 1.x is deprecated and no versions are released;
2.x is the actively developed version; and 3.x is the next major version being developed (as of April 2025).
These major versions use different Java packages and Maven artifact ids, so they are not mutually compatible, but can peacefully co-exist: a project can depend on both Jackson 1.x and 2.x (and eventually 3.x), without conflicts.
This is by design and was chosen as the strategy to allow smoother migration from 1.x to 2.x (and from 2.x to 3.x, eventually).

The latest stable versions from these branches are:

* [2.18.3](../../wiki/Jackson-Release-2.18.3), released on 28-Feb-2025
    * [2.17.3](../../wiki/Jackson-Release-2.17.3) is the latest patch from previous stable branch
* [1.9.13](../../wiki/JacksonRelease1.9), released 14-Jul-2013

Recommended way to use Jackson is through Maven repositories; releases are made to Central Maven Repository (CMR).
Individual projects' wiki pages sometimes also contain direct download links, pointing to CMR.

Release notes for 2.x releases are found from [Jackson Releases](../../wiki/Jackson-Releases) page.

## Active Jackson projects

Most projects listed below are lead by Jackson development team; but some by
other at-large Jackson community members.
We try to keep versioning of modules compatible to reduce confusion regarding which versions work together.

### Core modules

Core modules are the foundation on which extensions (modules) build upon.
There are 3 such modules currently (as of Jackson 2.x):

* [Streaming](../../../jackson-core) ([docs](../../../jackson-core/wiki)) ("jackson-core") defines low-level streaming API, and includes JSON-specific implementations
* [Annotations](../../../jackson-annotations) ([docs](../../../jackson-annotations/wiki)) ("jackson-annotations") contains standard Jackson annotations
* [Databind](../../../jackson-databind) ([docs](../../../jackson-databind/wiki)) ("jackson-databind") implements data-binding (and object serialization) support on `streaming` package; it depends both on `streaming` and `annotations` packages

### Third-party datatype modules

These extensions are plug-in Jackson `Module`s (registered with `ObjectMapper.registerModule()`),
and add support for datatypes of various commonly used Java libraries, by adding
serializers and deserializers so that Jackson `databind` package (`ObjectMapper` / `ObjectReader` / `ObjectWriter`) can read and write these types.

Datatype modules directly maintained by Jackson team are under the following Github repositories:

* Standard [Collections](../../../jackson-datatypes-collections) datatype modules:
    * [jackson-datatype-eclipse-collections](../../../jackson-datatypes-collections/tree/2.19/eclipse-collections): support for [Eclipse Collections](https://www.eclipse.org/collections/) (NEW in Jackson 2.10!)
    * [jackson-datatype-guava](../../../jackson-datatypes-collections/tree/2.19/guava): support for many of [Guava](http://code.google.com/p/guava-libraries/) datatypes
    * [jackson-datatype-hppc](../../../jackson-datatypes-collections/tree/2.19/hppc): support for [High-Performance Primitive Containers](http://labs.carrotsearch.com/hppc.html) containers
    * [jackson-datatype-pcollections](../../../jackson-datatypes-collections/tree/2.19/pcollections): support for [PCollections](http://pcollections.org/) datatypes (since Jackson 2.7)
* [Hibernate](../../../jackson-datatype-hibernate): support for Hibernate features (lazy-loading, proxies)
* [Java 8 Modules](../../../jackson-modules-java8): support or JDK 8 features and datatypes through 3 separate modules
    * `jackson-module-parameter-names`: Module that adds support for using a new JDK8 feature, ability to access names of constructor and method parameters, to allow omitting `@JsonProperty`.
    * `jackson-datatype-jsr310`: support for "Java 8 Dates" (ones added in JDK 8)
        * Also, for pre-Java8 users can use one of alternate pre-Java8 backports:
            * [joschi/jackson-datatype-threetenbp](https://github.com/joschi/jackson-datatype-threetenbp)
            * [lldata/jackson-datatype-threetenbp](https://github.com/lldata/jackson-datatype-threetenbp)
    * `jackson-datatype-jdk8`: support for JDK 8 data types other than date/time types, including `Optional`
* Joda datatypes:
    * [jackson-datatype-joda](../../../jackson-datatype-joda): support for types of [Joda-Time](https://www.joda.org/joda-time/) date/time library datatypes
    * [jackson-datatype-joda-money](../../../jackson-datatypes-misc/tree/2.19/joda-money): support types of [Joda-Money](https://www.joda.org/joda-money/) datatypes (`Money`, `CurrencyUnit`)
* JSON-P ("json processing"): two datatype modules for "old" (`javax.json`) and "new" (`jakarta.json`):
    * [jackson-datatype-jakarta-jsonp](../../../jackson-datatypes-misc/tree/2.19/jakarta-jsonp): support for "new" JSON-P types in `jakarta.json` (*added in Jackson 2.12.2*)
    * [jackson-datatype-jsr353](../../../jackson-datatypes-misc/tree/2.19/jsr-353): support for "old" JSON-P types in `javax.json`
* [jackson-datatype-json-org](../../../jackson-datatypes-misc/tree/2.19/json-org): support for [org.json](https://github.com/stleary/JSON-java) library types like `JSONObject`, `JSONArray`

In addition, we are aware of additional modules that are not directly maintained by core Jackson team:

* [jackson-datatype-bolts](https://github.com/v1ctor/jackson-datatype-bolts) support for reading/writing types defined by [Yandex Bolts](https://bitbucket.org/stepancheg/bolts/wiki/Home) collection types (Functional Programming inspired immutable collections)
* [jackson-datatype-commons-lang3](https://github.com/bramp/jackson-datatype-commons-lang3) for types of [Apache Commons Lang v3](https://commons.apache.org/proper/commons-lang/)
* [jackson-datatype-money](https://github.com/zalando/jackson-datatype-money) for "Java Money", see [javax.money](http://javamoney.github.io/api.html)
* [vavr-jackson](https://github.com/vavr-io/vavr-jackson) for [VAVR](https://github.com/vavr-io/vavr) support (Feature-rich & self-contained functional programming in Java™ 8 and above)
* [jackson-datatype-json-lib](https://github.com/swquinn/jackson-datatype-json-lib) for supporting types defined by "net.sf.json" library (aka "json-lib")
* [jackson-datatype-jts](https://github.com/bedatadriven/jackson-datatype-jts) (JTS Geometry) for [GeoJSON](https://en.wikipedia.org/wiki/GeoJSON) support
* [jackson-lombok](https://github.com/xebia/jackson-lombok) for better support of [Lombok](http://projectlombok.org/) classes
* [jackson-datatype-mongo](https://github.com/commercehub-oss/jackson-datatype-mongo) for MongoDB types
    * NOTE: there are a few alternatives to handling MongoDB datatypes
* [jackson-module-objectify](https://github.com/tburch/jackson-module-objectify) for datatypes of [Objectify](https://github.com/objectify/objectify)
* [jackson-datatype-protobuf](https://github.com/HubSpot/jackson-datatype-protobuf) for handling datatypes defined by the standard Java protobuf library, developed by [HubSpot](http://www.hubspot.com/)
    * NOTE! This is different from `jackson-dataformat-protobuf` which adds support for encoding/decoding protobuf content but which does NOT depend on standard Java protobuf library
* [TinyTypes](https://github.com/caligin/tinytypes) includes Jackson module (group id `com.github.caligin.tinytypes`, artifact `tinytypes-jackson`)
* [jackson-datatype-vertx](https://github.com/Crunc/jackson-datatype-vertx) for reading/writing [Vert.x](http://vertx.io/) `org.vertx.java.core.json.JsonObject` objects (repackaged `org.json` node types)

### Providers for JAX-RS

[Jackson JAX-RS Providers](../../../jackson-jaxrs-providers) has handlers to add dataformat
support for JAX-RS implementations (like Jersey, RESTeasy, CXF).
Providers implement `MessageBodyReader` and `MessageBodyWriter`.
Supported formats currently include `JSON`, `Smile`, `XML`, `YAML` and `CBOR`.

### Data format modules

Data format modules offer support for data formats other than JSON.
Most of them simply implement `streaming` API abstractions, so that databinding component can be used as is; some offer (and few require) additional `databind` level functionality for handling things like schemas.

Currently following data format modules are fully usable and supported (version number in parenthesis, if included, is the
first Jackson 2.x version to include module; if missing, included from 2.0)

* [Avro](../../../jackson-dataformats-binary/tree/2.19/avro): supports [Avro](http://en.wikipedia.org/wiki/Apache_Avro) data format, with `streaming` implementation plus additional `databind`-level support for Avro Schemas
* [CBOR](../../../jackson-dataformats-binary/tree/2.19/cbor): supports [CBOR](http://tools.ietf.org/search/rfc7049) data format (a binary JSON variant).
* [CSV](../../../jackson-dataformats-text/blob/2.19/csv): supports [Comma-separated values](http://en.wikipedia.org/wiki/Comma-separated_values) format -- `streaming` api, with optional convenience `databind` additions
* [Ion](../../../jackson-dataformats-binary/tree/2.19/ion) (2.9): support for [Amazon Ion](https://amznlabs.github.io/ion-docs/) binary data format (similar to CBOR, Smile, i.e. binary JSON - like)
* [(Java) Properties](../../../jackson-dataformats-text/blob/2.19/properties) (2.8): creating nested structure out of implied notation (dotted by default, configurable), flattening similarly on serialization
* [Protobuf](../../../jackson-dataformats-binary/tree/2.19/protobuf) (2.6): supported similar to `Avro`
* [Smile](../../../jackson-dataformats-binary/tree/2.19/smile): supports [Smile (binary JSON)](https://github.com/FasterXML/smile-format-specification) -- 100% API/logical model compatible via `streaming` API, no changes for `databind`
* [TOML](../../../jackson-dataformats-text/blob/2.13/toml): (NEW in upcoming 2.13) supports [TOML](http://en.wikipedia.org/wiki/TOML), supported with both `streaming` and `databind` implementations
* [XML](../../../jackson-dataformat-xml): supports XML; provides both `streaming` and `databind` implementations. Similar to JAXB' "code-first" mode (no support for "XML Schema first", but can use JAXB beans)
* [YAML](../../../jackson-dataformats-text/blob/2.19/yaml): supports [YAML](http://en.wikipedia.org/wiki/Yaml), which being similar to JSON is fully supported with simple `streaming` implementation

There are also other data format modules, provided by developers outside Jackson core team:

* [BEncode](https://github.com/zsoltm/jackson-dataformat-bencode): support for reading/writing [BEncode](https://en.wikipedia.org/wiki/Bencode) (BitTorrent format) encoded data
* [bson4jackson](https://github.com/michel-kraemer/bson4jackson): adds support for [BSON](http://en.wikipedia.org/wiki/BSON) data format (by Mongo project).
    * Implemented as full streaming implementation, which allows full access (streaming, data-binding, tree-model)
    * Also see [MongoJack] library below; while not a dataformat module, it allows access to BSON data as well.
* [EXIficient](https://github.com/EXIficient/exificient-for-json) supports [Efficient XML Interchange](https://en.wikipedia.org/wiki/Efficient_XML_Interchange)
* [jackson-dataformat-msgpack](https://github.com/msgpack/msgpack-java/tree/develop/msgpack-jackson) adds support [MessagePack](http://en.wikipedia.org/wiki/MessagePack) (aka `MsgPack`) format
    * Implemented as full streaming implementation, which allows full access (streaming, data-binding, tree-model)
* [HOCON](https://github.com/jclawson/jackson-dataformat-hocon): experimental, partial implementation to support [HOCON](https://github.com/typesafehub/config) format -- work in progress
* [Rison](https://github.com/Hronom/jackson-dataformat-rison): Jackson backend to support [Rison](https://github.com/Nanonid/rison)

### JVM Language modules

* [Kotlin](https://github.com/FasterXML/jackson-module-kotlin) to handle native types of [Kotlin](http://kotlinlang.org/)
* [Scala](https://github.com/FasterXML/jackson-module-scala) to handle native Scala types (including but not limited to Scala collection/map types, case classes)
    * Currently (October 2022) Scala 2.11, 2.12, 2.13 and 3 are supported (2.9 was supported up to Jackson 2.3 and 2.10 up to Jackson 2.11)

### Support for Schemas

Jackson annotations define intended properties and expected handling for POJOs, and in addition to Jackson itself
using this for reading/writing JSON and other formats, it also allows generation of external schemas.
Some of this functionality is included in above-mentioned data-format extensions; but there are also
many stand-alone Schema tools, such as:

#### JSON Schema

* Build tool plug-ins
    * [Ant Task for JSON Schema Generation](https://github.com/xdarklight/jackson-jsonschema-ant-task): Generate JSON Schemas from your Java classes with Apache Ant using the Jackson library and extension modules.
* Stand-alone JSON Schema generators
    * [Java JSON Schema Generator](https://github.com/victools/jsonschema-generator) (supports json schema draft v7!)
    * [Jackson jsonSchema Generator (Scala)](https://github.com/mbknor/mbknor-jackson-jsonSchema)
    * [JSON Schema generator module](../../../jackson-module-jsonSchema): programmatically generate JSON Schema, based on Jackson POJO introspection, including annotations (ONLY SUPPORTS json schema v3!!!)
* Code generators based on JSON Schema
    * [jsonschema2pojo](https://github.com/joelittlejohn/jsonschema2pojo) - Generate Java types from JSON or JSON Schema
* JSON Schema validators
    * [Java JSON Schema validator](https://github.com/java-json-tools/json-schema-validator)

#### Other schema languages

* [Ember Schema Generator](../../../../marcus-nl/ember-schema-generator): Generate schemas for [Ember.js](https://github.com/emberjs/ember.js)

### Other modules, stable

Other fully usable modules by FasterXML team include:

* [Base](../../../jackson-modules-base) modules:
    * [Afterburner](../../../jackson-modules-base/tree/2.19/afterburner): speed up databinding by 30-40% with bytecode generation to replace use of Reflection for field access, method/constructor calls
    * [Guice](../../../jackson-modules-base/tree/2.19/guice): extension that allows injection values from Guice injectors (and basic Guice annotations), instead of standard `@JacksonInject` (or in addition to)
    * [JAXB Annotations](../../../jackson-modules-base/tree/2.19/jaxb): allow use of `JAXB` annotations as an alternative (in addition to or instead of) standard Jackson annotations
    * [Mr Bean](../../../jackson-modules-base/tree/2.19/mrbean): "type materialization" -- let Mr Bean generate implementation classes on-the-fly (NO source code generation), to avoid monkey code
    * [OSGi](../../../jackson-modules-base/tree/2.19/osgi): allows injection of values from OSGi registry, via standard Jackson `@JacksonInject` annotation
    * [Paranamer](../../../jackson-modules-base/tree/2.19/paranamer): tiny extension for automatically figuring out creator (constructor, factory method) parameter names, to avoid having to specify `@JsonProperty`.

### Jackson jr

While [Jackson databind](../../../jackson-databind) is a good choice for general-purpose data-binding, its
footprint and startup overhead may be problematic in some domains, such as mobile phones; and especially
for light usage (couple of reads or writes). In addition, some developers find full Jackson API overwhelming.

For all these reasons, we decided to create a much simpler, smaller library, which supports a subset of
functionality, called [Jackson jr](../../../jackson-jr).
It builds on [Jackson Streaming API](../../../jackson-core), but does not depend on databind. As a result
its size (both jar, and runtime memory usage) is considerably smaller; and its API is very compact.

### Third-party non-module libraries based on Jackson

#### Jackson helper libraries

* [Jackson Ant path filter](https://github.com/Antibrumm/jackson-antpathfilter) adds powerful filtering of properties to serialize, using Ant Path notation for hierarchic filtering

#### Support for datatypes

* [MongoJack](http://mongojack.org/) supports efficient handling of [BSON](http://en.wikipedia.org/wiki/BSON) encoded data store in [MongoDB](http://en.wikipedia.org/wiki/MongoDB).

#### Other things related to or inspired by Jackson 

* [Jackson-js](https://github.com/pichillilorenzo/jackson-js) is a Javascript/Node object serialization/deserialization library with API inspired by Jackson
* [Pyckson](https://github.com/antidot/Pyckson) is a Python library that aims for same goals as Java Jackson, such as Convention over Configuration 
* [Rackson](https://github.com/griffindy/rackson) is a Ruby library that offers Jackson-like functionality on Ruby platform

## Contributing

If you would like to help with Jackson project, please check out [Contributing](CONTRIBUTING.md).

You may also want to check out:

* [Jackson Coding Style](contribution/jackson-coding-style-guide.md)

## Support 

### Community support

Jackson components are supported by the Jackson community through mailing lists, Gitter forum, Github issues. See [Contributing](CONTRIBUTING.md) for full details.

### Enterprise support

In addition to free (for all) community support, enterprise support—starting with version 2.10—is available as part of the [Tidelift Subscription](https://tidelift.com?utm_source=maven-com-fasterxml-jackson-core-jackson-core&utm_medium=referral&utm_campaign=enterprise&utm_term=repo) for (most) Jackson components.

The maintainers of `Jackson` and thousands of other packages are working with Tidelift to deliver commercial support and maintenance for the open source dependencies you use to build your applications. Save time, reduce risk, and improve code health, while paying the maintainers of the exact dependencies you use. [Learn more.](https://tidelift.com/subscription/pkg/maven-com-fasterxml-jackson-core-jackson-core?utm_source=maven-com-fasterxml-jackson-core-jackson-core&utm_medium=referral&utm_campaign=enterprise&utm_term=repo)

### Reporting security vulnerabilities

The recommended mechanism for reporting possible security vulnerabilities follows
so-called "Coordinated Disclosure Plan" (see [definition of DCP](https://vuls.cert.org/confluence/display/Wiki/Coordinated+Vulnerability+Disclosure+Guidance)
for general idea). The first step is to file a [Tidelift security contact](https://tidelift.com/security):
Tidelift will route all reports via their system to maintainers of relevant package(s), and start the
process that will evaluate concern and issue possible fixes, send update notices and so on.
Note that you do not need to be a Tidelift subscriber to file a security contact.

Alternatively you may also report possible vulnerabilities to `info` at fasterxml dot com
mailing address. Note that filing an issue to go with report is fine, but if you do that please
DO NOT include details of security problem in the issue but only in email contact.
This is important to give us time to provide a patch, if necessary, for the problem.

### Note on reporting Bugs

Jackson bugs need to be reported against component they affect: for this reason, issue tracker
is not enabled for this project.
If you are unsure which specific project issue affects, the most likely component
is `jackson-databind`, so you would use
[Jackson Databind Issue Tracker](https://github.com/FasterXML/jackson-databind/issues).

For suggestions and new ideas, try [Jackson Future Ideas](../../../jackson-future-ideas)

## Documentation

### Web sites

* [jackson-docs](../../../jackson-docs) is our Github Jackson documentation hub
* [Wiki](https://github.com/FasterXML/jackson/wiki/) of this repo contains:
    * [Jackson Releases](../../wiki/Jackson-Releases)
    * [FAQ](../../wiki/FAQ)
* Blogs
    * [CowTalk](http://cowtowncoder.com/blog/blog.html) (deprecated) -- Blog with lots of Jackson-specific content. Not updated since 2013.
    * [Cowtowncoder@medium](http://medium.com/@cowtowncoder/) -- More recent blogging about Jackson

### Tutorials

For first-time users there are many good Jackson usage tutorials, 
including general usage / JSON tutorials:

* [Baeldung Jackson JSON Tutorial](https://www.baeldung.com/jackson)
* [Javarevisited Jackson JSON Tutorial](https://javarevisited.blogspot.com/search/label/Java%20JSON%20tutorial)
* [Jenkov.com Jackson Tutorial](http://tutorials.jenkov.com/java-json/index.html)
* [JournalDev Jackson Tutorial](https://www.journaldev.com/2324/jackson-json-java-parser-api-example-tutorial)
* [LogicBig.com Jackson Tutorial](https://www.logicbig.com/tutorials/misc/jackson.html)
* [StudyTrails Jackson Introduction](http://www.studytrails.com/java/json/java-jackson-introduction/)

and more specific tutorials:

* [Java67 Javakcson CSV Tutorial](https://www.java67.com/2019/05/how-to-read-csv-file-in-java-using-jackson-library.html) (CSV)

### Reports

Following reports have been published about Jackson components

* [AdaLogics Jackson Security Audit (2022)](../../blob/master/docs/AdaLogics-Security-Audit-Jackson-2022.pdf) (jackson-core, jackson-databind)

### Java JSON library comparisons

Since you probably want opinions by Java developers NOT related to Jackson project, regarding which library to use,
here are links to some of existing independent comparisons:

* [Top 7 Open-Source JSON-binding providers](http://www.developer.com/lang/jscript/top-7-open-source-json-binding-providers-available-today.html) (April 2014)
* [Be a Lazy but a Productive Android Developer, Part 3: JSON Parsing Library](http://java.dzone.com/articles/be-lazy-productive-android) (April 2014)
* ["Can anyone recommend a good Java JSON library"](https://www.linkedin.com/groups/Can-anyone-recommend-good-Java-50472.S.226644043) (Linked-In group) (March 2013)
* ["Which JSON library to use on Android?"](http://thetarah.com/2012/09/21/which-json-library-should-i-use-in-my-android-and-java-projects/) (September 2012) 
