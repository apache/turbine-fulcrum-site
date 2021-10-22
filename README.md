
# The Fulcrum Website Instructions
--------------------------------

The Fulcrum web site is based on .xml files which are transformed
into .html files using Maven.

<http://maven.apache.org/>

## Description

The Fulcrum site builds the *wrapper site* for the Fulcrum components listed in site.xml. 

It is a Website repository, which is used to provides a mechanism (Management Tool) to *publish Turbine Fulcrum Components*, see [Apache Project site](https://infra.apache.org/project-site).

Build Tool is the Maven site building mechanism, though this includes a version it does not contain released sources to be published and versioning of this component is just for convenience (or unavoidable in pom.xml). Nevertheless Apache Site management rules apply.

### Publishing

This is described in section *Git Checkout source. Generate and Publish Site* here:

    https://github.com/apache/turbine-fulcrum-build#git-checkout--source-generate-and-publish-site
    
The basic mechanism is explained [here](https://infra.apache.org/version-control.html#git).    
    

### Deprecated SCM-Publish Maven Mechanism

*Important*: Using [scm-publish Plugin](https://commons.apache.org/site-publish.html) for publishing is not yet tested for current [Apache GIT](https://infra.apache.org/version-control.html).

Check first, that turbine.site.path matches the target pubScmUrl (e.g. by investigating the result of mvn help:effective-pom)

Once you have the site checked out locally, cd into your fulcrum-site directory and execute:


    mvn site


This will build the documentation into the target/site/ directory. The output will show you which files got re-generated.

If you would like to make modifications to the web site documents, you simply need to edit the files in the xdocs/ directory.

Once you have built your documentation and confirmed that your changes are ok, you can check your .xml files back into Subversion.

To test what files would be deleted or updated run:


    mvn site:stage scm-publish:publish-scm -Dscmpublish.dryRun=true


To deploy the site execute:

    mvn site:stage scm-publish:publish-scm


To do this you need an account on the people.apache.org machine!!



