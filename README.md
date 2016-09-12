# Palladio Headless Bridge

This project is used by the [Palladio Headless](https://github.com/SQuAT-Team/palladio-headless) project. The purpose of this project is to download relevant source files from the [Palladio](http://www.palladio-simulator.com/) update sites and repackages them as maven repository. The resulting maven repository is hosted in the `mvn-repo` branch of this git repository and is ready to be declared as dependency in mavenized projects.

### Setup

To get the build working on your machine, you'll need to authorize the GitHub maven plugin to access your account. See the [GitHub site maven plugin](https://github.com/github/maven-plugins#readme) for more information on how to authorize. Typically, your `~/.m2/settings.xml` needs to contain something along the lines of:

```mvn
<settings>
  <servers>
    <server>
      <id>github</id>
      <password>OAUTH_TOKEN</password>
    </server>
  </servers>
</settings>
```

Make sure to grant the oauth token access to the `public_repo` and the `user:email` privilege (see [github/maven-plugins#63](https://github.com/github/maven-plugins/issues/63#issuecomment-102610887)). 

*Note:* The id of the server has to be `github`, as this is referenced from within the `pom.xml`.


### Deployment

To build and deploy the repackaged version of Palladio execute the following command on your CLI:

```sh
mvn clean deploy
```

If you intend to release a new version, make sure to keep the version number in `META-INF/MANIFEST.MF` and `pom.xml` consistent.


## FAQ:

- What is Palladio? Go to http://www.palladio-simulator.com/ to find out.
- How does this work? Read http://stackoverflow.com/a/14013645/1262901 to find out.
- This does not work on my machine. Then [file an issue](https://github.com/FaKeller/palladio-headless-bridge-mvn/issues/new).


## [License](LICENSE)

This project is licensed under the terms of the [Eclipse Public License (EPL), Version 1.0](LICENSE).


---

Project created and maintained by [Fabian Keller](http://www.fabian-keller.de) in the scope of his master's thesis.