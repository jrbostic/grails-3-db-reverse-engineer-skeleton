# Grails DB Reverse Engineer Skeleton

The purpose of this project is to provide a working application that can be quickly cloned and modified to generate grails domains from existing databases.  

Due to some incompatibilities with the current highest version of the grails reverse engineer plugin and Hibernate 5, it is potentially a time-saving endeavor to use this approach (which utilizes Hibernate 4), then copying your domains into the higher version application.  Whatever differences exist between the two versions of Hibernate... if the number of tables is great enough, it will be worth the tweaking that may need to be done to get everything working.  Unless you really like hand-coding properties, mappings, and constraints.  :D

Reasons you might use this:

1. You are adding domains to an existing application that is having trouble adding the reverse engineering plugin as a dependency.
2. You are working with a Grails application >3.0.x which is using the incompatible Hibernate 5
3. Because it's simpler/easier than trying to hook up the deps and configuration to your actual application

[Reverse Engineer Plugin Code](https://github.com/grails-plugins/grails-db-reverse-engineer)

[Reverse Engineer Plugin Docs](https://grails-plugins.github.io/grails-db-reverse-engineer/grails3v4/index.html)

### Connecting to Database:

1. Add appropriate driver dependency to match target DB in `build.gradle`
2. Set up your `application.yml` datasource by updating:
    * driver class 
    * connection string
    * [dialect](https://docs.jboss.org/hibernate/orm/3.5/api/org/hibernate/dialect/package-summary.html) 
    * username
    * password

### Setting Up Options:

Update desired options. Using the [plugin docs](https://grails-plugins.github.io/grails-db-reverse-engineer/grails3v4/index.html#core-properties) for reference would be best here, but I do provide the list of config settings in `application.groovy` (where the configurations will be set).

### Generate Domains: 

    ./gradlew dbReverseEngineer
