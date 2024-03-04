# Archetype java11-junit5

## Description and Goals

The archetype is used as a basis for creating Java applications that target Java 11 and jUnit 5.  
Contains a pre-configured template for creating a README.md file.


## How to use

To generate a project, you first need to install the archetype in the local repository.
To do this, clone the repository and execute in its root directory:

```
mvn clean install archetype:update-local-catalog
```

Once the archetype is installed in your local Maven repository, you will be able to generate projects:

```
mvn archetype:generate \
  -DarchetypeGroupId=io.github.xelanimed \
  -DarchetypeArtifactId=java11-junit5 \
  -DarchetypeVersion=0.0.2 \
  -DgroupId=<your.group.id> \
  -DartifactId=<your-artifact-id> \
  -DinteractiveMode=false
```

By default, the package name is created from the specified `groupId` and `artifactId`.
If there are hyphens in the artifact name, they will be replaced with underscores.
You can also force the value of the package used:

```
mvn archetype:generate \
  -DarchetypeGroupId=io.github.xelanimed \
  -DarchetypeArtifactId=java11-junit5 \
  -DarchetypeVersion=0.0.2 \
  -DgroupId=<your.group.id> \
  -DartifactId=<your-artifact-id> \
  -Dpackage=<your.group.id.artifact_id> \
  -DinteractiveMode=false
```

When starting project generation interactively, values that have default values can be omitted:

```
mvn archetype:generate \
  -DarchetypeGroupId=io.github.xelanimed \
  -DarchetypeArtifactId=java11-junit5 \
  -DarchetypeVersion=0.0.2 \
  -DgroupId=my.group.id \
  -DartifactId=my-project
```

Output:

```
[INFO] Scanning for projects...
...
[INFO] Generating project in Interactive mode
[INFO] Archetype repository not defined. Using the one from [io.github.xelanimed:java11-junit5:0.0.2] found in catalog local
[INFO] Using property: groupId = my.group.id
[INFO] Parameter: artifactId, Value: my-project
[INFO] Parameter: version, Value: 0.0.1-SNAPSHOT
...
```

Default values:
- `version` - `0.0.1.-SNAPSHOT`
- `package` - `${groupId}.${artifactId}`
