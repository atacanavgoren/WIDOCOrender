origin -> https://github.com/dgarijo/Widoco

# WIzard for DOCumenting Ontologies (WIDOCO)
[![DOI](https://zenodo.org/badge/11427075.svg)](https://zenodo.org/badge/latestdoi/11427075) [![](https://jitpack.io/v/dgarijo/Widoco.svg)](https://jitpack.io/#dgarijo/Widoco) [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)

![Logo](src/main/resources/logo/logo2.png)

WIDOCO helps you to publish and create an enriched and customized documentation of your ontology automatically, by following a series of steps in a GUI.

**Author**: Daniel Garijo Verdejo (@dgarijo)

**Contributors**: María Poveda, Idafen Santana, Almudena Ruiz, Miguel Angel García, Oscar Corcho, Daniel Vila, Sergio Barrio, Martin Scharm, Maxime Lefrancois, Alfredo Serafini, @kartgk, Pat Mc Bennett, Christophe Camel, Jacobus Geluk, Martin Scharm, @rpietzsch, Jonathan Leitschuh, Jodi Schneider, Giacomo Lanza, Alejandra Gonzalez-Beltran, Mario Scrocca, Miguel Angel García, Flores Bakker, @JohnnyMoonlight,  René Fritze, @telecsur, Jan Vlug, Han Kruiger, Johannes Theissen-Lipp and Roberto Polli.

**Citing WIDOCO**: If you used WIDOCO in your work, please cite the ISWC 2017 paper: https://iswc2017.semanticweb.org/paper-138

```bib
@inproceedings{garijo2017widoco,
  title={WIDOCO: a wizard for documenting ontologies},
  author={Garijo, Daniel},
  booktitle={International Semantic Web Conference},
  pages={94--102},
  year={2017},
  organization={Springer, Cham},
  doi = {10.1007/978-3-319-68204-4_9},
  funding = {USNSF ICER-1541029, NIH 1R01GM117097-01},
  url={http://dgarijo.com/papers/widoco-iswc2017.pdf}
}
```
If you want to cite the latest version of the software, you can do so by using: https://zenodo.org/badge/latestdoi/11427075.

## Downloading the executable

To download WIDOCO, you need to download a JAR executable file. Check the latest release for more details: (https://github.com/dgarijo/WIDOCO/releases/latest).

## Importing WIDOCO as a dependency
Just add the dependency and repository to your `pom.xml` file as follows. See the [WIDOCO JitPack](https://jitpack.io/#dgarijo/Widoco) page to find alternative means to incorporate WIDOCO to your project.

```xml
<dependencies>
  <dependency>
      <groupId>com.github.dgarijo</groupId>
      <artifactId>Widoco</artifactId>
      <version>v1.4.16</version>
  </dependency>
</dependencies>

[ ... ]

<repositories>
	<repository>
	    <id>jitpack.io</id>
	    <url>https://jitpack.io</url>
	</repository>
</repositories>
```

## Description
WIDOCO helps you to publish and create an enriched and customized documentation of your ontology, by following a series of steps in a wizard. We extend the LODE framework by Silvio Peroni to describe the classes, properties and data properties of the ontology, the OOPS! webservice by María Poveda to print an evaluation and the Licensius service by Victor Rodriguez Doncel to determine the license URI and title being used. In addition, we use WebVowl to visualize the ontology and have extended Bubastis to show a complete changelog between different versions of your ontology.

Features of WIDOCO:
* Automatic documentation of the terms in your ontology (based on [LODE](http://www.essepuntato.it/lode/)). Now **you can use Markdown on your class descriptions** (see [example](doc/gallery/index.html))
* Massive metadata extraction and support: WIDOCO will enhance your ontology documentation  based on your ontology annotations. Now you can add custom logos and images, edit the content of your sections, etc. by just editing metadata. See our [supported metadata](https://github.com/dgarijo/Widoco/blob/master/doc/metadataGuide/guide.md) and [recommendations](https://dgarijo.github.io/Widoco/doc/bestPractices/index-en.html) for more information.
* Automatic annotation in JSON-LD snippets of the html produced.
* Association of a provenance page which includes the history of your vocabulary (W3C PROV-O compliant).
* Guidelines on the main sections that your document should have and how to complete them.
* Integration with diagram creators ([WebVOWL](http://vowl.visualdataweb.org/webvowl/)).
* Automatic changelog of differences between the actual and the previous version of the ontology (based on [Bubastis](http://www.ebi.ac.uk/efo/bubastis/)).
* Separation of the sections of your html page so you can write them independently and replace only those needed.
* Content negotiation and serialization of your ontology according to [W3C best practices](https://www.w3.org/TR/swbp-vocab-pub/)
* Evaluation reports of your ontology (using the [OOPS! web service](https://oops.linkeddata.es/))
* Integration with license metadata services ([Licensius](http://licensius.com/)) to automatically describe the license used in your ontology.

## Examples
Examples of the features of WIDOCO can be seen on [the gallery](https://dgarijo.github.io/Widoco/doc/gallery/)

## GUI Tutorial
A tutorial explaining the main features of the GUI can be found [here](https://dgarijo.github.io/Widoco/doc/tutorial/)  

## Metadata usage
To see how WIDOCO recognizes metadata annotations in your ontology to create the documentation files, see [the WIDOCO metadata documentation](doc/metadataGuide/guide.md). To learn which metadata properties we recommend adding to your ontology for producing a nice-looking documentation, have a look at our [best practices guide](doc/bestPractices/index-en.html).

For example, in order to show your logo in your documentation you just need to use `foaf:logo` as an annotation, as follows:
```
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
<https://w3id.org/roar> a owl:Ontology ;
    foaf:logo <https://www.leonvanwissen.nl/vocab/roar/docs/resources/roar-logo.png#> .
```

and it will show right next to the title. The [WIDOCO metadata documentation](doc/metadataGuide/guide.md) shows all supported metadata fields.

## How to use WIDOCO

### Building the JAR executable
We provide JAR files for each release (see the [releases](https://github.com/dgarijo/Widoco/releases) page). However, if you want to build WIDOCO from scratch, just cd into the project folder and run:

```bash
mvn install
```
The JAR will be generated in a "JAR" folder. The name will follow the pattern: `widoco-{VERSION_ID}-jar-with-dependencies.jar`, where {VERSION_ID} is the version number of the tool.

### JAR execution

Download the latest `.jar` [WIDOCO available release](https://github.com/dgarijo/WIDOCO/releases/latest) (it will be something like `widoco-VERSION-jar-with-dependencies.jar`). Then just double click the `.jar` file.

You may also execute WIDOCO through the command line. Usage:
```bash
java -jar widoco-VERSION-jar-with-dependencies.jar [OPTIONS]
```

### Docker execution

First build the image using the `Dockerfile` in project folder:

```bash
docker build -t dgarijo/widoco .
```

You can now execute WIDOCO through the command line. Usage:

```bash
docker run -ti --rm dgarijo/widoco [OPTIONS]
```

If you want to share data between the Docker Container and your Host, for instance to load a local ontology file (from PATH), you will need to mount the container
with host directories. For instance:

```bash
docker run -ti --rm \
  -v `pwd`/test:/usr/local/widoco/in \
  -v `pwd`/target/generated-doc:/usr/local/widoco/out \
  dgarijo/widoco -ontFile in/bne.ttl -outFolder out -rewriteAll
```

### Options

`-ontFile PATH`  [required (unless -ontURI is used)]: Load a local ontology file (from PATH) to document. This option is incompatible with -ontURI

`-ontURI  URI`   [required (unless -ontFile is used)]: Load an ontology to document from its URI. This option is incompatible with -ontFile

`-outFolder folderName`: Specifies the name of the folder where to save the documentation. By default is 'myDocumentation'

`-confFile PATH`: Load your own configuration file for the ontology metadata. Incompatible with -getOntologyMetadata. See [the configuration documentation](doc/configuration/configuration_doc.md) for more information about the accepted fields.

`-getOntologyMetadata`: Extract ontology metadata from the given ontology

`-oops`: Create an html page with the evaluation from the OOPS service (http://oops.linkeddata.es/)

`-rewriteAll`: Replace any existing files when documenting an ontology (e.g., from a previous execution)

`-crossRef`: ONLY generate the overview and cross reference sections. The index document will NOT be generated. The htaccess, provenance page, etc., will not be generated unless requested by other flags. This flag is intended to be used only after a first version of the documentation exists.

`-saveConfig PATH`: Save a configuration file on PATH with the properties of a given ontology

`-useCustomStyle`: Export the documentation using alternate css files (by Daniel Vila).

`-lang LANG1-LANG2`: Generate documentation in multiple languages (separated by "-"). Note that if the language is not supported, the system will load the labels in english. For example: en-pt-es

`-includeImportedOntologies`: Indicates whether the terms of the imported ontologies of the current ontology should be documented as well or not.

`-htaccess`: Create a bundle for publication ready to be deployed on your Apache server.

`-webVowl`: Create a visualization based on WebVowl (http://vowl.visualdataweb.org/webvowl/index.html#) in the documentation.

`-licensius`: Use the Licensius web services (http://licensius.com/apidoc/index.html) to retrieve license metadata. Only works if the -getOntologyMetadata  flag is enabled.

`-ignoreIndividuals`: Individuals will not be included in the documentation.

`-includeAnnotationProperties`: Include annotation properties defined in your ontology in the documentation (by default they are not included)

`-analytics CODE`: Add a code snippet for Google analytics to track your HTML documentation. You need to add your CODE next to the flag. For example: UA-1234

`-doNotDisplaySerializations`: The serializations of the ontology will not be displayed.

`-displayDirectImportsOnly`: Only those imported ontologies that are directly imported in the ontology being documented.

`-rewriteBase PATH`: Change the default rewrite base path. The default value is "/". This flag can only be used with the htaccess option.

`-excludeIntroduction`: Skip the introduction section in the documentation.

`-uniteSections`: Write all HTML sections into a single HTML document.

`-noPlaceHolderText`: Do not add any placeholder text (this will remove intro, abstract (if empty) and description sections).

`--help`: Shows a help message and exits.

`--version`: Shows the version of WIDOCO.


## How can I make WIDOCO automatically recognize my vocabulary annotations?
There are two alternative ways for making WIDOCO get your vocabulary metadata annotations and use them automatically to document the ontology.

* The recommended way: add them in your OWL file. For guidelines on which ones to include, follow our [best practices document](https://w3id.org/widoco/bestPractices), which indicates which ones we recommend.
* Alternatively, edit the project properties of /config/config.properties. This is a key-value pair file with metadata properties. Some people consider it easier than adding the property annotations to the OWL file, although I recommend doing the former option. Note that the character ";" is used for lists (for instance first author; second author; third author).

For more information, see the [Widoco metadata guide](doc/metadataGuide/guide.md)

## Browser issues (Why can't I see the generated documentation / visualization?)
WIDOCO separates the contents of different sections in HTML files, which are then loaded in the `index.html` file. WIDOCO was designed this way because it's easier to edit your introduction or description sections independently without being all aggregated together in a huge HTML document.  **When all the contents generated by WIDOCO are stored in a server, you will be able to see the documentation of your ontology using any browser**. However, if you open the `index.html` file **on your local browser**, you may see a document missing most of the sections in your documentation. This happens because browsers don't allow loading separate content when opening a file locally for security reasons. If you want to explore how your ontology would look locally, you have two options:

* a) Execute WIDOCO with the `-uniteSections` flag; or select the option `add al sections in a single document` in the "load sections" step in the WIDOCO GUI. This will make all the sections of WIDOCO to be in the `index.html`; and you will be able to see it in your browser. Note that the **LODE visualization will not be available** when exploring your ontology locally.
* b) Create a local server: Set up a local server (e.g., using XAMPP or Tomcat) and serve the files WIDOCO generates (in the `htdocs` folder for Apache servers).

If you place the files generated by WIDOCO in a server and access them via its URL (for example, a Github page), you should be able to see your documentation appropriately.

## Current improvements
For a complete list of the current improvements and next features, check the [project open issues](https://github.com/dgarijo/Widoco/issues) and [milestones](https://github.com/dgarijo/Widoco/milestones) in the repository.

## Requirements
You will need Java 1.8 or higher (SDK 1.8 or JRE 8) for WIDOCO to work
Otherwise, you will probably experience an "Unsupported major.minor version 52.0" exception when executing the JAR file.

## Contribution guidelines
Contributions to address any of the current issues are welcome. In order to push your contribution, just **push your pull request to the develop branch**. The master branch has only the code associated to the latest release.
=======
# WIDOCOrender



## Getting started

To make it easy for you to get started with GitLab, here's a list of recommended next steps.

Already a pro? Just edit this README.md and make it your own. Want to make it easy? [Use the template at the bottom](#editing-this-readme)!

## Add your files

- [ ] [Create](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#create-a-file) or [upload](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#upload-a-file) files
- [ ] [Add files using the command line](https://docs.gitlab.com/ee/gitlab-basics/add-file.html#add-a-file-using-the-command-line) or push an existing Git repository with the following command:

```
cd existing_repo
git remote add origin https://gitlab.com/iec_tf31/widocorender.git
git branch -M main
git push -uf origin main
```

## Integrate with your tools

- [ ] [Set up project integrations](https://gitlab.com/iec_tf31/widocorender/-/settings/integrations)

## Collaborate with your team

- [ ] [Invite team members and collaborators](https://docs.gitlab.com/ee/user/project/members/)
- [ ] [Create a new merge request](https://docs.gitlab.com/ee/user/project/merge_requests/creating_merge_requests.html)
- [ ] [Automatically close issues from merge requests](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#closing-issues-automatically)
- [ ] [Enable merge request approvals](https://docs.gitlab.com/ee/user/project/merge_requests/approvals/)
- [ ] [Set auto-merge](https://docs.gitlab.com/ee/user/project/merge_requests/merge_when_pipeline_succeeds.html)

## Test and Deploy

Use the built-in continuous integration in GitLab.

- [ ] [Get started with GitLab CI/CD](https://docs.gitlab.com/ee/ci/quick_start/index.html)
- [ ] [Analyze your code for known vulnerabilities with Static Application Security Testing (SAST)](https://docs.gitlab.com/ee/user/application_security/sast/)
- [ ] [Deploy to Kubernetes, Amazon EC2, or Amazon ECS using Auto Deploy](https://docs.gitlab.com/ee/topics/autodevops/requirements.html)
- [ ] [Use pull-based deployments for improved Kubernetes management](https://docs.gitlab.com/ee/user/clusters/agent/)
- [ ] [Set up protected environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html)

***

# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Choose a self-explaining name for your project.

## Description
Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser.

## Authors and acknowledgment
Show your appreciation to those who have contributed to the project.

## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers.
>>>>>>> a9526b4e13cba371b270b564bbbd50e616699ec7
