Source code for Hadoop in Practice, Second Edition
==================================================

This project contains the source code that accompanies the book "Hadoop in Practice, Second Edition".

The book is currently in [MEAP](http://www.manning.com/about/meap.html) form, which gives you early access to chapters
as they are being completed. I'll add a link to the book once it's up on Manning's site.

## License

Apache version 2.0 (for more details look at the [license](LICENSE)).

## Usage

### Tarball

The easiest way to start working with the examples is to download a tarball distribution of this project.
Doing so will mean that running your first example is just three steps away:

1. Click on "releases" and download the most recent tarball.
2. Extract the contents ot the tarball, i.e. `tar -xzvf hip-<version>-package.tar.gz`
3. Run the "hello world" example, which is

```bash
$ cd hip-<version>

# create two input files in HDFS
$ hadoop fs -mkdir -p hip1/input
$ echo "cat sat mat" | hadoop fs -put - hip1/input/1.txt
$ echo "dog lay mat" | hadoop fs -put - hip1/input/2.txt

# run the inverted index example
$ ./hip hip.ch1.InvertedIndexJob --input hip1/input --output hip1/output

# examine the results in HDFS
$ hadoop fs -cat hip1/output/part*
```

Done! The tarball also includes the sources and JavaDocs.

### Building your own distribution

Here you're going to checkout the trunk and then use Maven to run a build.

1. Checkout the code.

```bash
$ git co git@github.com:alexholmes/hiped2.git
```

2. Build the code and distribution tarball.

```bash
$ cd hiped2
$ mvn package
```

The JAR's and tarball will be under the `target` directory.

## What's next?

At this point check out the book for more examples and how you can execute them. Or if you find any issues then
please post them here - click on "Issues".