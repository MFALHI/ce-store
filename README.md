# ITA Controlled English (CE)

The CE Store contains everything you need to get started with the ITA Controlled English environment.

We are an IBM initiated open source organisation focused on providing an experimental research environment for the ITA Controlled English language.

## Quick Guide

* [Tutorials (See wiki)](https://github.com/ce-store/ce-store/wiki)
* [Installation and Setup](https://github.com/ce-store/ce-store#installation-and-setup)
* [Usage](https://github.com/ce-store/ce-store#usage)
* [Contributing](https://github.com/ce-store/ce-store#contributing)
* [License](https://github.com/ce-store/ce-store#license)

## Installation and Setup

Clone the code

```
git clone https://github.com/ce-store/ce-store
```

### Eclipse

Install Eclipse

  1. Download and install [Eclipse IDE for Java EE Developers](http://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/mars1).
  2. Open Eclipse and set up your workspace.

Set the Eclipse Text encoding
  1. In Eclipse open `Window`, `Preferences`, `General`, `Workspace`
  2. Set the Text file encoding to UTF-8, Click on `OK`

Set new Eclipse file associations
  1. In Eclipse open `Window`, `Preferences`, `General`, `Content Types`
  2. Click on the `Text` entry in the top `Content types` pane
  3. In the lower `File associations` pane, use the `Add` button to add file associations for `*.ce` and `*.cecmd`, then click on `Ok`.

Import the project into Eclipse

  1. In Eclipse select `File` then `Import`
  2. Under the `Import` window select `Git` then `Projects from Git`
  3. Select `Existing local repository`
  4. Select the git repository that contains the ce-store code and click `Next`. If this repository is not listed click `Add...` and locate the folder
  5. Select `Import existing Eclipse projects` and click `Next`
  6. Select the `ce-store` project on the Import Projects pane and click `Next` 
  7. Click `Finish`

The project should now appear in your Package Explorer. 

You may find that you get a number of servlet-based compilation errors due to the runtime setup. These will be resolved by configuring a web server in the following section.

### Web Server
Add the project to your favourite server and run. Tomcat and Liberty examples are described below.

**Tomcat**

Install Tomcat

  1. Go to the [Tomcat website](http://tomcat.apache.org/) and download Tomcat 7 (minimum required version).

Add Tomcat to Eclipse

  1. In Eclipse open `Window`, `Preferences`, `Server`, `Runtime Environments`
  2. Click `Add...`
  3. Under the New Server Runtime dialog select your runtime under Apache (minimum Tomcat 7)
  4. Click `Next`
  5. Fill in the Tomcat installation directory
  6. In `Window`, `Preferences`, `Java`, `Installed JREs`, ensure the selected JRE is a full JDK and is a version that will satisfy Apache Tomcat. If necessary, you can add a compatible JDK to Eclipse
  7. Click `Finish`

Set up Tomcat server

  1. Set up a new server by clicking `File`, `New`, `Other...`, `Server`, `Server`
  2. Click `Next`
  3. Under `Apache` select `Tomcat`
  4. Name your server and click `Next`
  5. Add `ce-store` to configure on the server
  6. Click `Finish`

Run the server

  1. In the Server view right click the Tomcat server and click `Start`
  2. Access the CE Store at [http://localhost:8080/ce-store](http://localhost:8080/ce-store)

**Liberty**

Install Liberty

  1. Go to the [Liberty Get Started page](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/) and follow instructions to install

Set up Liberty server

  1. Set up a new server by clicking `File`, `New`, `Other...`, `Server`, `Server`
  2. Click `Next`
  3. Under `IBM` select `WebSphere Application Server Liberty`
  4. Click `Next`
  5. Select `Install from an archive or a repository` (If you already have the Liberty Runtime installed select the runtime and skip to step 12)
  6. Click `Next`
  7. Select `Download and install a new runtime environment from ibm.com`
  8. Select `WAS Liberty V8.5.* Runtime`
  9. Enter a destination path for the installation (.\Servers\Liberty under the workspace is a good location) 
  10. Click `Next`, then `Next` again
  11. Accept the T&Cs
  12. Name your server and click `Next`
  13. Add `ce-store` to configure on the server (right click on the Liberty server in the Servers view, select `Add and Remove` and add the ce-store)
  14. Click `Finish`

Change the project build path
  1. In the Project Explorer view, right click on the ce-store project, select `Build Path`, `Configure Build Path...`
  2. In the Libraries tab, click on `Add Library`
  3. Select `Server Runtime` and click `Next`
  4. Select the WebSphere Application Server Liberty Profile, click `Finish`
  5. Click `Ok`. 
  The ce-store should now build with no compilation errors, using the Liberty profile.


Run the server

  1. In the Server view right click the Liberty server and click `Start`
  2. Access the CE Store at [http://localhost:9080/ce-store](http://localhost:9080/ce-store)

## Usage

### Engineering Panel

The Engineering Panel provides a simple web interface to the CE Store, enabling the user view the contents of the CE Store, to load new CE sentences, run queries agains the store, and more.

To open the Engineering Panel go to `<SERVER>/ce-store/ui`. It should look like this:

![Engineering Panel](http://ce-store.github.io/i/ui.png)

The engineering panel has four main areas:

  * [Left] Model operations: CE models can be loaded and modified.
  * [Right] Object pane: Contents of a CE store can be viewed.
  * [Bottom] Messages: Errors will be reported here
  * [Centre] Working area: Interactions with the model.

The CE Store comes with a sample set of CE sentences to build a model about medical data. The wiki includes a tutorial for using the [Medicine model](https://github.com/ce-store/ce-store/wiki/Introducing-the-Medicine-Model).

## Contributing

Read about contributing [here](https://github.com/ce-store/ce-store/blob/master/CONTRIBUTE.md).

## License

Licensed under the [Apache License, Version 2.0](https://github.com/ce-store/ce-store/blob/master/LICENSE.md)
