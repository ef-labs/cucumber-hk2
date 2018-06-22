# cucumber-hk2

The HK2 module follows the patterns used by the [Cucumber Guice](https://github.com/cucumber/cucumber-jvm/tree/master/guice) 
dependency module. 
 

An annotation binding scope named `@ScenarioScoped` has been added, which when set as the binding scope for a class, 
will limit the object's lifespan to the lifespan of a Cucumber scenario. (i.e. a new instance of this object will be 
created for each Cucumber scenario)
 

The `ServiceLocator` used by the module is provided by the user's implementation of `ServiceLocatorSource`. Expose
your implementation to the Cucumber runtime by setting the environment key `hk2.locator-source` to the fully qualified 
name of the implementing class.
 

The easiest way to do this is by creating a cucumber.properties file with the configuration values, and placing
this file at the root of your classpath.


If you do not provide your own custom ServiceLocatorSource, a default ServiceLocatorSource will be created by 
the module. This default ServiceLocator will be populated by services found in the `META-INF/hk2-locator/default` file.


Please refer to the [HK2 project page](https://hk2-project.github.io/) for further information on HK2.
