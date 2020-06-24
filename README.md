Rebuilding artifacts from (Maven) Central Repository
====================================================

As part of [Reproducible Builds efforts for the JVM](https://reproducible-builds.org/docs/jvm/), this "**Reproducible Central**" project is an attempt at:
1. writing [rebuild instructions](BUILDSPEC.md) for the artifacts available in the [Central Repository](https://search.maven.org/),
equivalent to the packaging instructions that are maintained by every Linux distribution
(for example Debian's [debian/rules](https://www.debian.org/doc/debian-policy/ch-source#s-debianrules) or ArchLinux's PKGBUILD), whatever the build tool used (Central Repository is not used by Maven only)
2. show the level of reproducibility obtained using previous instructions: how many output files from the rebuild are strictly equal to reference in Central Repository, how many output files are not yet reproducible and should be improved before the next release?

## What Can I Do?

<details><summary><b>Rebuild Yourself To Check Results</b></summary>

You can rebuild a project release by running:
```
./rebuild.sh content/<path/to/...>/<project>-<version>.buildspec
```
`rebuild.sh` script will use the build specification file (= [`.buildspec` file](BUILDSPEC.md)) to choose a Docker container to rebuild the project and check output against Central Repository reference binaries.

To rebuild every project with build instructions available in this Git repository, just run:
```
find content -name *.buildspec -exec ./rebuild.sh {} \;
```
</details>

<details><summary><b>Contribute A New Build Spec</b></summary>

If you know a project released to Central Repository that is expected to provide Reproducible Builds, please tell us by opening an issue with details. Even better, you can provide a PR containing a [`.buildspec` build specification file](BUILDSPEC.md).

</details>

<details><summary><b>Improve Reproducibility Score Of A Project Release</b></summary>

If a rebuild published here is not fully reproducible (it has some :warning:), there is an issue: please help to improve the situation.

You'll need to rebuild the release yourself (see previous instructions), then use [diffoscope](https://diffoscope.org/) to easily explore precise difference
between reference file from Central Repository and effective rebuild file, then debug up to the root cause of this unwanted difference:
- rebuilder bug: if the improvement has to happen at [buildspec](BUILDSPEC.md) or [rebuild script](rebuild.sh) level, don't hesitate to open an issue or a PR here,
- upstream project reproducibility issue: please contact the upstream project and help them improve the reproducibility for their next release.

</details>

<details><summary><b>Check That My Project Uses Reproducible Dependencies</b></summary>
This is a future objective. But for now, given the very few projects that produce reproducible artifacts, it's a little bit early to try to automate checks of your dependencies: there is a good chance that your dependencies are not reproducible. You should help by reporting to the project owners, and help them make their build reproducible for future releases.
</details>

## Rebuild Results

<!-- BEGIN GENERATED CONTENT -->
| [Central Repository](https://search.maven.org/) groupId:artifactId(s):version | [build spec](BUILDSPEC.md) | [result](https://reproducible-builds.org/docs/jvm/): reproducibility |
| -------------------------------- | --------- | ------ |
| com.io7m.jade:com.io7m.jade:[1.0.1](https://search.maven.org/artifact/com.io7m.jade/com.io7m.jade/1.0.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/com/io7m/jade/com.io7m.jade-1.0.1.buildspec): [:notebook:](https://github.com/io7m/jade.git) mvn jdk-11 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/com/io7m/jade/com.io7m.jade.documentation-1.0.1.buildinfo): [17 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/com/io7m/jade/com.io7m.jade.documentation-1.0.1.buildinfo.compare) |
| com.scalapenos:stamina:[0.1.5](https://search.maven.org/artifact/com.scalapenos/stamina/0.1.5/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/com/scalapenos/stamina/stamina-0.1.5.buildspec): [:notebook:](https://github.com/scalapenos/stamina.git) sbt jdk-8 | [24 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/com/scalapenos/stamina/stamina-0.1.5.buildinfo.compare) |
| io.dropwizard:dropwizard-core:[2.0.10](https://search.maven.org/artifact/io.dropwizard/dropwizard-core/2.0.10/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/dropwizard/core/dropwizard-2.0.10.buildspec): [:notebook:](https://github.com/dropwizard/dropwizard.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/dropwizard/core/java-simple-2.0.10.buildinfo): [27 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/dropwizard/core/java-simple-2.0.10.buildinfo.compare) |
| io.github.derkrischan:jpdftest:[0.8.0](https://search.maven.org/artifact/io.github.derkrischan/jpdftest/0.8.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/github/derkrischan/jpdftest/jpdftest-0.8.0.buildspec): [:notebook:](https://github.com/derKrischan/jpdftest.git) mvn jdk-7 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/github/derkrischan/jpdftest/jpdftest-0.8.0.buildinfo): [1 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/github/derkrischan/jpdftest/jpdftest-0.8.0.buildinfo.compare) |
| io.liftwizard:liftwizard:[0.1.0](https://search.maven.org/artifact/io.liftwizard/liftwizard/0.1.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/liftwizard/liftwizard-0.1.0.buildspec): [:notebook:](https://github.com/motlin/liftwizard.git) mvn jdk-11 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/liftwizard/liftwizard-junit-rule-match-json-0.1.0.buildinfo): [81 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/liftwizard/liftwizard-junit-rule-match-json-0.1.0.buildinfo.compare) |
| io.micronaut:micronaut-maven-plugin:[1.0.0](https://search.maven.org/artifact/io.micronaut/micronaut-maven-plugin/1.0.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.buildspec): [:notebook:](https://github.com/micronaut-projects/micronaut-maven-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.buildinfo): [2 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.buildinfo.compare) |
| io.micronaut:micronaut-maven-plugin:[1.0.0.RC4](https://search.maven.org/artifact/io.micronaut/micronaut-maven-plugin/1.0.0.RC4/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.RC4.buildspec): [:notebook:](https://github.com/micronaut-projects/micronaut-maven-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.RC4.buildinfo): [2 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/io/micronaut/build/micronaut-maven-plugin/micronaut-maven-plugin-1.0.0.RC4.buildinfo.compare) |
| nl.hsac:hsac-fitnesse-fixtures:[4.13.0](https://search.maven.org/artifact/nl.hsac/hsac-fitnesse-fixtures/4.13.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/nl/hsac/hsac-fitnesse-fixtures/hsac-fitnesse-fixtures-4.13.0.buildspec): [:notebook:](https://github.com/fhoeben/hsac-fitnesse-fixtures.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/nl/hsac/hsac-fitnesse-fixtures/hsac-fitnesse-fixtures-4.13.0.buildinfo): [ 3 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/nl/hsac/hsac-fitnesse-fixtures/hsac-fitnesse-fixtures-4.13.0.buildinfo.compare) |
| org.apache.dubbo:dubbo:[2.7.7](https://search.maven.org/artifact/org.apache.dubbo/dubbo/2.7.7/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/dubbo/dubbo-2.7.7.buildspec): [:notebook:](https://github.com/apache/dubbo.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/dubbo/dubbo-metadata-processor-2.7.7.buildinfo): [148 :heavy_check_mark:  3 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/dubbo/dubbo-metadata-processor-2.7.7.buildinfo.compare) |
| org.apache.jena:jena:[3.14.0](https://search.maven.org/artifact/org.apache.jena/jena/3.14.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jena/jena/jena-3.14.0.buildspec): [:notebook:](https://github.com/apache/maven-jena.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jena/jena/jena-osgi-features-3.14.0.buildinfo): [107 :heavy_check_mark:  30 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jena/jena/jena-osgi-features-3.14.0.buildinfo.compare) |
| org.apache.jspwiki:sjpwiki-builder:[2.11.0.M7](https://search.maven.org/artifact/org.apache.jspwiki/sjpwiki-builder/2.11.0.M7/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jspwiki/jspwiki-2.11.0.M7.buildspec): [:notebook:](https://github.com/apache/jspwiki.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jspwiki/jspwiki-it-test-cma-jdbc-2.11.0.M7.buildinfo): [11 :heavy_check_mark:  58 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/jspwiki/jspwiki-it-test-cma-jdbc-2.11.0.M7.buildinfo.compare) |
| org.apache.maven.doxia:doxia:[1.9.1](https://search.maven.org/artifact/org.apache.maven.doxia/doxia/1.9.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia/doxia-1.9.1.buildspec): [:notebook:](https://github.com/apache/maven-doxia.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia/doxia-module-markdown-1.9.1.buildinfo): [38 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia/doxia-module-markdown-1.9.1.buildinfo.compare) |
| org.apache.maven.doxia:doxia-sitetools:[1.9.2](https://search.maven.org/artifact/org.apache.maven.doxia/doxia-sitetools/1.9.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia-sitetools/doxia-sitetools-1.9.2.buildspec): [:notebook:](https://github.com/apache/maven-doxia-sitetools.git) mvn jdk-7 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia-sitetools/doxia-doc-renderer-1.9.2.buildinfo): [12 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/doxia/doxia-sitetools/doxia-doc-renderer-1.9.2.buildinfo.compare) |
| org.apache.maven:maven:[3.6.3](https://search.maven.org/artifact/org.apache.maven/maven/3.6.3/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/maven/maven-3.6.3.buildspec): [:notebook:](https://github.com/apache/maven-maven.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/maven/apache-maven-3.6.3.buildinfo): [2 :heavy_check_mark:  30 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/maven/apache-maven-3.6.3.buildinfo.compare) |
| org.apache.maven.plugins:maven-antrun-plugin:[3.0.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-antrun-plugin/3.0.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-antrun-plugin/maven-antrun-plugin-3.0.0.buildspec): [:notebook:](https://github.com/apache/maven-antrun-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-antrun-plugin/maven-antrun-plugin-3.0.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-antrun-plugin/maven-antrun-plugin-3.0.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-assembly-plugin:[3.3.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-assembly-plugin/3.3.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-assembly-plugin/maven-assembly-plugin-3.3.0.buildspec): [:notebook:](https://github.com/apache/maven-assembly-plugin.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-assembly-plugin/maven-assembly-plugin-3.3.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-assembly-plugin/maven-assembly-plugin-3.3.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-checkstyle-plugin:[3.1.1](https://search.maven.org/artifact/org.apache.maven.plugins/maven-checkstyle-plugin/3.1.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-checkstyle-plugin/maven-checkstyle-plugin-3.1.1.buildspec): [:notebook:](https://github.com/apache/maven-checkstyle-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-checkstyle-plugin/maven-checkstyle-plugin-3.1.1.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-checkstyle-plugin/maven-checkstyle-plugin-3.1.1.buildinfo.compare) |
| org.apache.maven.plugins:maven-dependency-plugin:[3.1.2](https://search.maven.org/artifact/org.apache.maven.plugins/maven-dependency-plugin/3.1.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-dependency-plugin/maven-dependency-plugin-3.1.2.buildspec): [:notebook:](https://github.com/apache/maven-dependency-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-dependency-plugin/maven-dependency-plugin-3.1.2.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-dependency-plugin/maven-dependency-plugin-3.1.2.buildinfo.compare) |
| org.apache.maven.plugins:maven-ejb-plugin:[3.1.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-ejb-plugin/3.1.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-ejb-plugin/maven-ejb-plugin-3.1.0.buildspec): [:notebook:](https://github.com/apache/maven-ejb-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-ejb-plugin/maven-ejb-plugin-3.1.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-ejb-plugin/maven-ejb-plugin-3.1.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-javadoc-plugin:[3.2.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-javadoc-plugin/3.2.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-javadoc-plugin/maven-javadoc-plugin-3.2.0.buildspec): [:notebook:](https://github.com/apache/maven-javadoc-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-javadoc-plugin/maven-javadoc-plugin-3.2.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-javadoc-plugin/maven-javadoc-plugin-3.2.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-project-info-reports-plugin:[3.1.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-project-info-reports-plugin/3.1.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-project-info-reports-plugin/maven-project-info-reports-plugin-3.1.0.buildspec): [:notebook:](https://github.com/apache/maven-project-info-reports-plugin.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-project-info-reports-plugin/maven-project-info-reports-plugin-3.1.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-project-info-reports-plugin/maven-project-info-reports-plugin-3.1.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-shade-plugin:[3.2.2](https://search.maven.org/artifact/org.apache.maven.plugins/maven-shade-plugin/3.2.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.2.buildspec): [:notebook:](https://github.com/apache/maven-shade-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.2.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.2.buildinfo.compare) |
| org.apache.maven.plugins:maven-shade-plugin:[3.2.3](https://search.maven.org/artifact/org.apache.maven.plugins/maven-shade-plugin/3.2.3/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.3.buildspec): [:notebook:](https://github.com/apache/maven-shade-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.3.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.3.buildinfo.compare) |
| org.apache.maven.plugins:maven-shade-plugin:[3.2.4](https://search.maven.org/artifact/org.apache.maven.plugins/maven-shade-plugin/3.2.4/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.4.buildspec): [:notebook:](https://github.com/apache/maven-shade-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.4.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-shade-plugin/maven-shade-plugin-3.2.4.buildinfo.compare) |
| org.apache.maven.plugins:maven-site-plugin:[3.9.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-site-plugin/3.9.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-site-plugin/maven-site-plugin-3.9.0.buildspec): [:notebook:](https://github.com/apache/maven-site-plugin.git) mvn jdk-7 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-site-plugin/maven-site-plugin-3.9.0.buildinfo): [1 :heavy_check_mark:  2 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-site-plugin/maven-site-plugin-3.9.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-source-plugin:[3.2.1](https://search.maven.org/artifact/org.apache.maven.plugins/maven-source-plugin/3.2.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-source-plugin/maven-source-plugin-3.2.1.buildspec): [:notebook:](https://github.com/apache/maven-source-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-source-plugin/maven-source-plugin-3.2.1.buildinfo): [ 3 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-source-plugin/maven-source-plugin-3.2.1.buildinfo.compare) |
| org.apache.maven.plugins:maven-war-plugin:[3.3.0](https://search.maven.org/artifact/org.apache.maven.plugins/maven-war-plugin/3.3.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-war-plugin/maven-war-plugin-3.3.0.buildspec): [:notebook:](https://github.com/apache/maven-war-plugin.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-war-plugin/maven-war-plugin-3.3.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-war-plugin/maven-war-plugin-3.3.0.buildinfo.compare) |
| org.apache.maven.plugins:maven-wrapper-plugin:[3.0.1](https://search.maven.org/artifact/org.apache.maven.plugins/maven-wrapper-plugin/3.0.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-wrapper-plugin/maven-wrapper-plugin-3.0.1.buildspec): [:notebook:](https://github.com/apache/maven-wrapper-plugin.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-wrapper-plugin/maven-wrapper-plugin-3.0.1.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/plugins/maven-wrapper-plugin/maven-wrapper-plugin-3.0.1.buildinfo.compare) |
| org.apache.maven.reporting:maven-reporting-exec:[1.5.1](https://search.maven.org/artifact/org.apache.maven.reporting/maven-reporting-exec/1.5.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/reporting/maven-reporting-exec/maven-reporting-exec-1.5.1.buildspec): [:notebook:](https://github.com/apache/maven-reporting-exec.git) mvn jdk-7 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/reporting/maven-reporting-exec/maven-reporting-exec-1.5.1.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/reporting/maven-reporting-exec/maven-reporting-exec-1.5.1.buildinfo.compare) |
| org.apache.maven.resolver:maven-resolver-ant-tasks:[1.2.1](https://search.maven.org/artifact/org.apache.maven.resolver/maven-resolver-ant-tasks/1.2.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/resolver/maven-resolver-ant-tasks/maven-resolver-ant-tasks-1.2.1.buildspec): [:notebook:](https://github.com/apache/maven-resolver-ant-tasks.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/resolver/maven-resolver-ant-tasks/maven-resolver-ant-tasks-1.2.1.buildinfo): [4 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/resolver/maven-resolver-ant-tasks/maven-resolver-ant-tasks-1.2.1.buildinfo.compare) |
| org.apache.maven.resolver:maven-resolver:[1.4.2](https://search.maven.org/artifact/org.apache.maven.resolver/maven-resolver/1.4.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/resolver/maven-resolver/maven-resolver-1.4.2.buildspec): [:notebook:](https://github.com/apache/maven-resolver.git) mvn jdk-8 win | [12 :heavy_check_mark:  10 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/resolver/maven-resolver/maven-resolver-*-1.4.2.buildinfo.compare) |
| org.apache.maven.shared:maven-verifier:[1.7.1](https://search.maven.org/artifact/org.apache.maven.shared/maven-verifier/1.7.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.1.buildspec): [:notebook:](https://github.com/apache/maven-verifier.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.1.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.1.buildinfo.compare) |
| org.apache.maven.shared:maven-verifier:[1.7.2](https://search.maven.org/artifact/org.apache.maven.shared/maven-verifier/1.7.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.2.buildspec): [:notebook:](https://github.com/apache/maven-verifier.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.2.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/shared/maven-verifier/maven-verifier-1.7.2.buildinfo.compare) |
| org.apache.maven.surefire:surefire:[3.0.0-M5](https://search.maven.org/artifact/org.apache.maven.surefire/surefire/3.0.0-M5/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/surefire/surefire-3.0.0-M5.buildspec): [:notebook:](https://github.com/apache/maven-surefire.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/surefire/surefire-shared-utils-3.0.0-M5.buildinfo): [45 :heavy_check_mark:  5 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/surefire/surefire-shared-utils-3.0.0-M5.buildinfo.compare) |
| org.apache.maven.wagon:wagon:[3.4.0](https://search.maven.org/artifact/org.apache.maven.wagon/wagon/3.4.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-3.4.0.buildspec): [:notebook:](https://github.com/apache/maven-wagon.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-webdav-jackrabbit-3.4.0.buildinfo): [33 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-webdav-jackrabbit-3.4.0.buildinfo.compare) |
| org.apache.maven.wagon:wagon:[3.4.1](https://search.maven.org/artifact/org.apache.maven.wagon/wagon/3.4.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-3.4.1.buildspec): [:notebook:](https://github.com/apache/maven-wagon.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-webdav-jackrabbit-3.4.1.buildinfo): [33 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/maven/wagon/wagon/wagon-webdav-jackrabbit-3.4.1.buildinfo.compare) |
| org.apache.plc4x:plc4x:[0.7.0](https://search.maven.org/artifact/org.apache.plc4x/plc4x/0.7.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/plc4x/plc4x/plc4x-0.7.0.buildspec): [:notebook:](https://github.com/apache/plc4x.git) mvn jdk-11 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/plc4x/plc4x/plc4x-tools-0.7.0.buildinfo): [16 :heavy_check_mark:  51 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/plc4x/plc4x/plc4x-tools-0.7.0.buildinfo.compare) |
| org.apache.royale.compiler:compiler:[0.9.7](https://search.maven.org/artifact/org.apache.royale.compiler/compiler/0.9.7/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/royale/compiler/royale-compiler-0.9.7.buildspec): [:notebook:](https://github.com/apache/royale-compiler.git) mvn jdk-8 win | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/royale/compiler/royale-maven-plugin-0.9.7.buildinfo): [20 :heavy_check_mark:  5 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/royale/compiler/royale-maven-plugin-0.9.7.buildinfo.compare) |
| org.apache.sling:org.apache.sling.commons.johnzon:[1.2.0](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.commons.johnzon/1.2.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.commons.johnzon/org.apache.sling.commons.johnzon-1.2.0.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-commons-johnzon.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.commons.johnzon/org.apache.sling.commons.johnzon-1.2.0.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.commons.johnzon/org.apache.sling.commons.johnzon-1.2.0.buildinfo.compare) |
| org.apache.sling:org.apache.sling.installer.core:[3.11.0](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.installer.core/3.11.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.core/org.apache.sling.installer.core-3.11.0.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-installer-core.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.core/org.apache.sling.installer.core-3.11.0.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.core/org.apache.sling.installer.core-3.11.0.buildinfo.compare) |
| org.apache.sling:org.apache.sling.installer.factory.packages:[1.0.2](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.installer.factory.packages/1.0.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.factory.packages/org.apache.sling.installer.factory.packages-1.0.2.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-installer-factory-packages.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.factory.packages/org.apache.sling.installer.factory.packages-1.0.2.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.factory.packages/org.apache.sling.installer.factory.packages-1.0.2.buildinfo.compare) |
| org.apache.sling:org.apache.sling.installer.provider.file:[1.2.2](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.installer.provider.file/1.2.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.file/org.apache.sling.installer.provider.file-1.2.2.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-installer-provider-file.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.file/org.apache.sling.installer.provider.file-1.2.2.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.file/org.apache.sling.installer.provider.file-1.2.2.buildinfo.compare) |
| org.apache.sling:org.apache.sling.installer.provider.jcr:[3.2.2](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.installer.provider.jcr/3.2.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.jcr/org.apache.sling.installer.provider.jcr-3.2.2.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-installer-provider-jcr.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.jcr/org.apache.sling.installer.provider.jcr-3.2.2.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.installer.provider.jcr/org.apache.sling.installer.provider.jcr-3.2.2.buildinfo.compare) |
| org.apache.sling:org.apache.sling.models.validation-impl:[1.0.0](https://search.maven.org/artifact/org.apache.sling/org.apache.sling.models.validation-impl/1.0.0/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.models.validation-impl/org.apache.sling.models.validation-impl-1.0.0.buildspec): [:notebook:](https://github.com/apache/sling-org-apache-sling-models-validation-impl.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.models.validation-impl/org.apache.sling.models.validation-impl-1.0.0.buildinfo): [3 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/apache/sling/org.apache.sling.models.validation-impl/org.apache.sling.models.validation-impl-1.0.0.buildinfo.compare) |
| org.codehaus.plexus:plexus-archiver:[4.2.2](https://search.maven.org/artifact/org.codehaus.plexus/plexus-archiver/4.2.2/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-archiver/plexus-archiver-4.2.2.buildspec): [:notebook:](https://github.com/codehaus-plexus/plexus-archiver.git) mvn jdk-7 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-archiver/plexus-archiver-4.2.2.buildinfo): [2 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-archiver/plexus-archiver-4.2.2.buildinfo.compare) |
| org.codehaus.plexus:plexus-compiler:[2.8.6](https://search.maven.org/artifact/org.codehaus.plexus/plexus-compiler/2.8.6/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-compiler/plexus-compiler-2.8.6.buildspec): [:notebook:](https://github.com/codehaus-plexus/plexus-compiler.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-compiler/plexus-compiler-j2objc-2.8.6.buildinfo): [21 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-compiler/plexus-compiler-j2objc-2.8.6.buildinfo.compare) |
| org.codehaus.plexus:plexus-languages:[1.0.5](https://search.maven.org/artifact/org.codehaus.plexus/plexus-languages/1.0.5/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-languages/plexus-languages-1.0.5.buildspec): [:notebook:](https://github.com/codehaus-plexus/plexus-languages.git) mvn jdk-9 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-languages/plexus-java-1.0.5.buildinfo): [2 :heavy_check_mark:  1 :warning:](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/codehaus/plexus/plexus-languages/plexus-java-1.0.5.buildinfo.compare) |
| org.tomitribe.transformer:org.eclipse.transformer.parent:[0.1.1](https://search.maven.org/artifact/org.tomitribe.transformer/org.eclipse.transformer.parent/0.1.1/pom) | [buildspec](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/tomitribe/transformer/org.eclipse.transformer.parent-0.1.1.buildspec): [:notebook:](https://github.com/tomitribe/transformer.git) mvn jdk-8 | [buildinfo](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/tomitribe/transformer/org.eclipse.transformer.maven-0.1.1.buildinfo): [4 :heavy_check_mark: ](https://github.com/jvm-repo-rebuild/reproducible-central/tree/master/content/org/tomitribe/transformer/org.eclipse.transformer.maven-0.1.1.buildinfo.compare) |
<!-- END GENERATED CONTENT -->

## Understanding What Is Behind

see [history](HISTORY.md)
