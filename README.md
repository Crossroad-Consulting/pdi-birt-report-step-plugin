# General
A Pentaho Data Integration plugin for generating Birt reports within transformations

# Version information
The current version of the plugin was tested using the Birt Runtime 4.5.0, Pentaho DI CE 6.1.0.1-196 and Java 1.8. Other versions were not tested.

# Build & Deploy
## Dependant libraries
Obviously, the plugin depends on Birt Runtime libraries. These are not included in this repository, but can be easily obtained from http://download.eclipse.org/birt/downloads/.

## Gradle setup
A Gradle script (https://gradle.org/) is used for managing project dependencies, building the code an deploying the plugin. This script can be found in the root of the project: build.gradle. We have used Gradle version 2.14.1, although other Gradle versions should work as well.
At the top of the file, you need to fill two variables with correct values to be able to build and deploy the plugin:
* pdi_folder: This is the root folder were Pentaho DI is installed (usually called data-integration)
* birt_lib: This is the lib folder that contains the Birt Runtime library files

## Gradle tasks
The Gradle tasks that can be executed are:
* recompileBirtJar: This task will recompile the main Birt runtime library, excluding some classes which proved to be incompatible within the Pentaho DI environment. The new jar filed is suffixed with \_updated and placed in the distributions folder of the Gradle build folder.
* cleanDeploy: This task will delete the Birt Report Step Plugin from the Pentaho DI plugin folder.
* deploy: This task will deploy the plugin to the Pentaho DI environment. It will copy the compile Birt Report Step Plugin jar, the Birt Runtime library files (excluding the main Birt Runtime library) and the updated Birt Runtime library file to the Pentaho DI plugin folder (under 'birt-report-step-plugin').

# Issues
This is still a project 'in progress'. The code is not completely clean and still has a lot of possible improvements. Feel free to add issues!
