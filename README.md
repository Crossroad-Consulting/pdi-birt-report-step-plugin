# General
A Pentaho Data Integration plugin for generating Birt reports within transformations

# Version information
The current version of the plugin was tested using the Birt Runtime 4.5.0 and Pentaho DI CE 6.1.0.1-196. Other versions were not tested.

# Build & Deploy
A Gradle script (https://gradle.org/) is used for managing project dependencies, building the code an deploying the plugin. This script can be found in the root of the project: build.gradle. At the top of the file, you need to fill two variables with correct values to be able to build and deploy the plugin:
* pdi_folder: This is the root folder were Pentaho DI is installed (usually called data-integration)
* birt_lib: This is the lib folder that contains the Birt Runtime library files
