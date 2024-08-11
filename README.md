ifdef::env-github[]
:artifactId: kitchensink
endif::[]

//***********************************************************************************
// Enable the following flag to build README.html files for JBoss EAP product builds.
// Comment it out for WildFly builds.
//***********************************************************************************
:ProductRelease:

//***********************************************************************************
// Enable the following flag to build README.html files for EAP XP product builds.
// Comment it out for WildFly or JBoss EAP product builds.
//***********************************************************************************
//:EAPXPRelease:

// This is a universal name for all releases
:ProductShortName: JBoss EAP
// Product names and links are dependent on whether it is a product release (CD or JBoss)
// or the WildFly project.
// The "DocInfo*" attributes are used to build the book links to the product documentation

ifdef::ProductRelease[]
// JBoss EAP release
:productName: JBoss EAP
:productNameFull: Red Hat JBoss Enterprise Application Platform
:productVersion: 8.0
:DocInfoProductNumber: {productVersion}
:WildFlyQuickStartRepoTag: 8.0.x
:productImageVersion: 8.0.0
:helmChartName: jboss-eap/eap8
endif::[]

ifdef::EAPXPRelease[]
// JBoss EAP XP release
:productName: JBoss EAP XP
:productNameFull: Red Hat JBoss Enterprise Application Platform expansion pack
:productVersion: 3.0
:DocInfoProductNumber: 7.4
:WildFlyQuickStartRepoTag: XP_3.0.0.GA
:productImageVersion: 3.0
:helmChartName: jboss-eap/eap-xp3
endif::[]

ifdef::ProductRelease,EAPXPRelease[]
:githubRepoUrl: https://github.com/jboss-developer/jboss-eap-quickstarts/
:githubRepoCodeUrl: https://github.com/jboss-developer/jboss-eap-quickstarts.git
:jbossHomeName: EAP_HOME
:DocInfoProductName: Red Hat JBoss Enterprise Application Platform
:DocInfoProductNameURL: red_hat_jboss_enterprise_application_platform
:DocInfoPreviousProductName: jboss-enterprise-application-platform
:quickstartDownloadName: {productNameFull} {productVersion} Quickstarts
:quickstartDownloadUrl: https://access.redhat.com/jbossnetwork/restricted/listSoftware.html?product=appplatform&downloadType=distributions
:helmRepoName: jboss-eap
:helmRepoUrl: https://jbossas.github.io/eap-charts/
// END ifdef::ProductRelease,EAPXPRelease[]
endif::[]

ifndef::ProductRelease,EAPXPRelease[]
// WildFly project
:productName: WildFly
:productNameFull: WildFly Application Server
:ProductShortName: {productName}
:jbossHomeName: WILDFLY_HOME
:productVersion: 28
:productImageVersion: 28.0
:githubRepoUrl: https://github.com/wildfly/quickstart/
:githubRepoCodeUrl: https://github.com/wildfly/quickstart.git
:WildFlyQuickStartRepoTag: 28.0.1.Final
:DocInfoProductName: Red Hat JBoss Enterprise Application Platform
:DocInfoProductNameURL: red_hat_jboss_enterprise_application_platform
// Do not update the following until after the 7.4 docs are published!
:DocInfoProductNumber: 7.4
:DocInfoPreviousProductName: jboss-enterprise-application-platform
:helmRepoName: wildfly
:helmRepoUrl: http://docs.wildfly.org/wildfly-charts/
:helmChartName: wildfly/wildfly
// END ifndef::ProductRelease,EAPCDRelease,EAPXPRelease[]
endif::[]

:source: {githubRepoUrl}

// Values for Openshift S2i sections attributes
:CDProductName:  {productNameFull} for OpenShift
:CDProductShortName: {ProductShortName} for OpenShift
:CDProductTitle: {CDProductName}
:CDProductNameSentence: Openshift release for {ProductShortName}
:CDProductAcronym: {CDProductShortName}
:CDProductVersion: {productVersion}
:EapForOpenshiftBookName: {productNameFull} for OpenShift
:EapForOpenshiftOnlineBookName: {EapForOpenshiftBookName} Online
:xpaasproduct: {productNameFull} for OpenShift
:xpaasproductOpenShiftOnline: {xpaasproduct} Online
:xpaasproduct-shortname: {CDProductShortName}
:xpaasproductOpenShiftOnline-shortname: {xpaasproduct-shortname} Online
:ContainerRegistryName: Red Hat Container Registry
:EapForOpenshiftBookName: Getting Started with {ProductShortName} for OpenShift Container Platform
:EapForOpenshiftOnlineBookName: Getting Started with {ProductShortName} for OpenShift Online
:OpenShiftOnlinePlatformName: Red Hat OpenShift Container Platform
:OpenShiftOnlineName: Red Hat OpenShift Online
:ImagePrefixVersion: eap80
:ImageandTemplateImportBaseURL: https://raw.githubusercontent.com/jboss-container-images/jboss-eap-openshift-templates
:ImageandTemplateImportURL: {ImageandTemplateImportBaseURL}/{ImagePrefixVersion}/
:BuildImageStream: jboss-{ImagePrefixVersion}-openjdk11-openshift
:RuntimeImageStream: jboss-{ImagePrefixVersion}-openjdk11-runtime-openshift

// OpenShift repository and reference for quickstarts
:EAPQuickStartRepo: https://github.com/jboss-developer/jboss-eap-quickstarts
:EAPQuickStartRepoRef: 8.0.x
:EAPQuickStartRepoTag: EAP_8.0.0.GA
// Links to the OpenShift documentation
:LinkOpenShiftGuide: https://access.redhat.com/documentation/en-us/{DocInfoProductNameURL}/{DocInfoProductNumber}/html-single/getting_started_with_jboss_eap_for_openshift_container_platform/
:LinkOpenShiftOnlineGuide: https://access.redhat.com/documentation/en-us/{DocInfoProductNameURL}/{DocInfoProductNumber}/html-single/getting_started_with_jboss_eap_for_openshift_online/

ifdef::EAPXPRelease[]
// Attributes for XP releases
:EapForOpenshiftBookName: {productNameFull} for OpenShift
:EapForOpenshiftOnlineBookName: {productNameFull} for OpenShift Online
:xpaasproduct: {productNameFull} for OpenShift
:xpaasproductOpenShiftOnline: {productNameFull} for OpenShift Online
:xpaasproduct-shortname: {ProductShortName} for OpenShift
:xpaasproductOpenShiftOnline-shortname: {ProductShortName} for OpenShift Online
:ContainerRegistryName: Red Hat Container Registry
:EapForOpenshiftBookName: {productNameFull} for OpenShift
:EapForOpenshiftOnlineBookName: {productNameFull} for OpenShift Online
:ImagePrefixVersion: eap-xp3
:ImageandTemplateImportURL: {ImageandTemplateImportBaseURL}/{ImagePrefixVersion}/
:BuildImageStream: jboss-{ImagePrefixVersion}-openjdk11-openshift
:RuntimeImageStream: jboss-{ImagePrefixVersion}-openjdk11-runtime-openshift
// OpenShift repository and reference for quickstarts
:EAPQuickStartRepoRef: xp-3.0.x
// Links to the OpenShift documentation
:LinkOpenShiftGuide: https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/{DocInfoProductNumber}/html/using_eclipse_microprofile_in_jboss_eap/using-the-openshift-image-for-jboss-eap-xp_default
:LinkOpenShiftOnlineGuide: https://access.redhat.com/documentation/en-us/red_hat_jboss_enterprise_application_platform/{DocInfoProductNumber}/html/using_eclipse_microprofile_in_jboss_eap/using-the-openshift-image-for-jboss-eap-xp_default
endif::[]

ifndef::ProductRelease,EAPCDRelease,EAPXPRelease[]
:ImageandTemplateImportURL: https://raw.githubusercontent.com/wildfly/wildfly-s2i/v{productVersion}.0/
endif::[]

//*************************
// Other values
//*************************
:buildRequirements: Java 11.0 (Java SDK 11) or later and Maven 3.6.0 or later
:jbdsEapServerName: Red Hat JBoss Enterprise Application Platform 7.3
:javaVersion: Jakarta EE 10
ifdef::EAPXPRelease[]
:javaVersion: Eclipse MicroProfile
endif::[]
:githubRepoBranch: master
:guidesBaseUrl: https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/
:useEclipseUrl: {guidesBaseUrl}USE_JBDS.adoc#use_red_hat_jboss_developer_studio_or_eclipse_to_run_the_quickstarts
:useEclipseDeployJavaClientDocUrl: {guidesBaseUrl}USE_JBDS.adoc#deploy_and_undeploy_a_quickstart_containing_server_and_java_client_projects
:useEclipseDeployEARDocUrl: {guidesBaseUrl}USE_JBDS.adoc#deploy_and_undeploy_a_quickstart_ear_project
:useProductHomeDocUrl: {guidesBaseUrl}USE_OF_{jbossHomeName}.adoc#use_of_product_home_and_jboss_home_variables
:configureMavenDocUrl: {guidesBaseUrl}CONFIGURE_MAVEN_JBOSS_EAP.adoc#configure_maven_to_build_and_deploy_the_quickstarts
:arquillianTestsDocUrl: {guidesBaseUrl}RUN_ARQUILLIAN_TESTS.adoc#run_the_arquillian_tests
:addUserDocUrl: {guidesBaseUrl}CREATE_USERS.adoc#create_users_required_by_the_quickstarts
:addApplicationUserDocUrl: {guidesBaseUrl}CREATE_USERS.adoc#add_an_application_user
:addManagementUserDocUrl: {guidesBaseUrl}CREATE_USERS.adoc#add_an_management_user
:startServerDocUrl: {guidesBaseUrl}START_JBOSS_EAP.adoc#start_the_jboss_eap_server
:configurePostgresDocUrl: {guidesBaseUrl}CONFIGURE_POSTGRESQL_JBOSS_EAP.adoc#configure_the_postgresql_database_for_use_with_the_quickstarts
:configurePostgresDownloadDocUrl: {guidesBaseUrl}CONFIGURE_POSTGRESQL_JBOSS_EAP.adoc#download_and_install_postgresql
:configurePostgresCreateUserDocUrl: {guidesBaseUrl}CONFIGURE_POSTGRESQL_JBOSS_EAP.adoc#create_a_database_user
:configurePostgresAddModuleDocUrl: {guidesBaseUrl}CONFIGURE_POSTGRESQL_JBOSS_EAP.adoc#add_the_postgres_module_to_the_jboss_eap_server
:configurePostgresDriverDocUrl: {guidesBaseUrl}CONFIGURE_POSTGRESQL_JBOSS_EAP.adoc#configure_the_postgresql_driver_in_the_jboss_eap_server
:configureBytemanDownloadDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#download_and_configure_byteman
:configureBytemanDisableDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#disable_the_byteman_script
:configureBytemanClearDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#clear_the_transaction_object_store
:configureBytemanQuickstartDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#configure_byteman_for_use_with_the_quickstarts
:configureBytemanHaltDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#use_byteman_to_halt_the_application[
:configureBytemanQuickstartsDocUrl: {guidesBaseUrl}CONFIGURE_BYTEMAN.adoc#configure_byteman_for_use_with_the_quickstarts

:EESubsystemNamespace: urn:jboss:domain:ee:4.0
:IiopOpenJdkSubsystemNamespace: urn:jboss:domain:iiop-openjdk:2.0
:MailSubsystemNamespace: urn:jboss:domain:mail:3.0
:SingletonSubsystemNamespace: urn:jboss:domain:singleton:1.0
:TransactionsSubsystemNamespace: urn:jboss:domain:transactions:4.0

// LinkProductDocHome: https://access.redhat.com/documentation/en/red-hat-jboss-enterprise-application-platform/
:LinkProductDocHome: https://access.redhat.com/documentation/en/jboss-enterprise-application-platform-continuous-delivery
:LinkConfigGuide: https://access.redhat.com/documentation/en-us/{DocInfoProductNameURL}/{DocInfoProductNumber}/html-single/configuration_guide/
:LinkDevelopmentGuide: https://access.redhat.com/documentation/en-us/{DocInfoProductNameURL}/{DocInfoProductNumber}/html-single/development_guide/
:LinkGettingStartedGuide: https://access.redhat.com/documentation/en-us/{DocInfoProductNameURL}/{DocInfoProductNumber}/html-single/getting_started_guide/
:LinkOpenShiftWelcome: https://docs.openshift.com/online/welcome/index.html
:LinkOpenShiftSignup: https://docs.openshift.com/online/getting_started/choose_a_plan.html
:OpenShiftTemplateName: JBoss EAP CD (no https)

:ConfigBookName: Configuration Guide
:DevelopmentBookName: Development Guide
:GettingStartedBookName: Getting Started Guide

:JBDSProductName: Red Hat CodeReady Studio
:JBDSVersion: 12.15
:LinkJBDSInstall:  https://access.redhat.com/documentation/en-us/red_hat_codeready_studio/{JBDSVersion}/html-single/installation_guide/
:JBDSInstallBookName: Installation Guide
:LinkJBDSGettingStarted: https://access.redhat.com/documentation/en-us/red_hat_codeready_studio/{JBDSVersion}/html-single/getting_started_with_codeready_studio_tools/
:JBDSGettingStartedBookName: Getting Started with CodeReady Studio Tools

= kitchensink: Assortment of technologies including Arquillian
:author: Pete Muir
:level: Intermediate
:technologies: CDI, JSF, JPA, EJB, JAX-RS, BV
:openshift: true

[abstract]
The `kitchensink` quickstart demonstrates a {javaVersion} web-enabled database application using JSF, CDI, EJB, JPA, and Bean Validation.

:standalone-server-type: default
:archiveType: war
:uses-h2:
:uses-ds-xml:

== What is it?

The `kitchensink` quickstart is a deployable Maven 3 project designed to help you get your foot in the door developing with {javaVersion} on {productNameFull}.

It demonstrates how to create a compliant {javaVersion} application using JSF, CDI, JAX-RS, EJB, JPA, and Bean Validation. It also includes a persistence unit and some sample persistence and transaction code to introduce you to database access in enterprise Java.

// Considerations for Use in a Production Environment
:leveloffset: +1

[[considerations_for_use_in_a_production_environment]]
= Considerations for Use in a Production Environment
//******************************************************************************
// Include this template if your quickstart:
// * Uses the h2 database: Be sure to define the `uses-h2` attribute.
// * Uses an `*-ds.xml file`: Be sure to define the `uses-ds-xml` attribute.
// * Has performance or scalability concerns: Be sure to define the `uses-ds-xml` attribute.
//******************************************************************************

ifdef::uses-h2[]

H2 Database:: This quickstart uses the H2 database included with {productNameFull} {productVersion}. It is a lightweight, relational example datasource that is used for examples only. It is not robust or scalable, is not supported, and should NOT be used in a production environment.

endif::uses-h2[]

ifdef::uses-ds-xml[]

Datasource Configuration File:: This quickstart uses a `*-ds.xml` datasource configuration file for convenience and ease of database configuration. These files are deprecated in {productName} and should not be used in a production environment. Instead, you should configure the datasource using the Management CLI or Management Console. Datasource configuration is documented in the {LinkConfigGuide}[__{ConfigBookName}__].

endif::uses-ds-xml[]

ifdef::performance-scalability[]

Performance and Scalability:: A Jakarta EE container is designed with robustness in mind, so you should carefully analyze the scalabiltiy, concurrency, and performance needs of your application before taking advantage of these techniques in your own applications.

endif::performance-scalability[]

:leveloffset!:
// System Requirements
:leveloffset: +1

[[system_requirements]]
= System Requirements
//******************************************************************************
// Include this template to describe the standard system requirements for
// running the quickstarts.
//
// The Forge quickstarts define a `forge-from-scratch` attribute because they
// run entirely in CodeReady Studio and have different requirements .
//******************************************************************************

The application this project produces is designed to be run on {productNameFull} {productVersion} or later.

All you need to build this project is {buildRequirements}. See link:{configureMavenDocUrl}[Configure Maven to Build and Deploy the Quickstarts] to make sure you are configured correctly for testing the quickstarts.

:leveloffset!:
//  Use of {jbossHomeName}
:leveloffset: +1

ifdef::requires-multiple-servers[]
[[use_of_jboss_home_name]]
= Use of the {jbossHomeName}_1, {jbossHomeName}_2, and QUICKSTART_HOME Variables

This quickstart requires that you clone your `__{jbossHomeName}__` installation directory and run two servers. The installation path is described in detail here: link:{useProductHomeDocUrl}[Use of __{jbossHomeName}__ and __JBOSS_HOME__ Variables].

In the following instructions, replace `__{jbossHomeName}_1__` with the path to your first {productName} server and replace `__{jbossHomeName}_2__` with the path to your second cloned {productName} server.

When you see the replaceable variable __QUICKSTART_HOME__, replace it with the path to the root directory of all of the quickstarts.
endif::[]

ifdef::optional-domain-or-multiple-servers[]
[[use_of_jboss_home_name]]
= Use of the {jbossHomeName}_1, {jbossHomeName}_2, and QUICKSTART_HOME Variables

When deploying this quickstart to a managed domain, replace `__{jbossHomeName}__` with the actual path to your {productName} installation. The installation path is described in detail here: link:{useProductHomeDocUrl}[Use of __{jbossHomeName}__ and __JBOSS_HOME__ Variables].

When deploying this quickstart to multiple standalone servers, this quickstart requires that you clone your `__{jbossHomeName}__` installation directory and run two servers. In the following instructions, replace `__{jbossHomeName}_1__` with the path to your first {productName} server and replace `__{jbossHomeName}_2__` with the path to your second cloned {productName} server.

When you see the replaceable variable __QUICKSTART_HOME__, replace it with the path to the root directory of all of the quickstarts.
endif::[]

ifndef::requires-multiple-servers,optional-domain-or-multiple-servers[]
[[use_of_jboss_home_name]]
= Use of the {jbossHomeName} and QUICKSTART_HOME Variables

In the following instructions, replace `__{jbossHomeName}__` with the actual path to your {productName} installation. The installation path is described in detail here: link:{useProductHomeDocUrl}[Use of __{jbossHomeName}__ and __JBOSS_HOME__ Variables].

When you see the replaceable variable __QUICKSTART_HOME__, replace it with the path to the root directory of all of the quickstarts.
endif::[]

:leveloffset!:

// build and run with standard server distribution
[[build_and_run_the_quickstart_with_server_dist]]
== Building and running the quickstart application with a {productName} server distribution
// Start the {productName} Standalone Server
:leveloffset: +2

[[start_the_eap_standalone_server]]
= Start the {productName} Standalone Server
//******************************************************************************
// Include this template if your quickstart requires a normal start of a single
// standalone server.
//
// You must define the `standalone-server-type`. Supported values are:
//    default
//    full
//    full-ha
//    ha
//    custom
//
// * For mobile applications, you can define the `mobileApp` variable in the
//   `README.adoc` file to add `-b 0.0.0.0` to the command line. This allows
//    external clients, such as phones, tablets, and desktops, to connect
//    to the application through through your local network
//    ::mobileApp: {artifactId}-service
//
//******************************************************************************

//******************************************************************************
// This template sets attributes for the different standalone server profiles.
//
// You must define the `standalone-server-type`. Supported values are:
//    default
//    full
//    full-ha
//    ha
//    microprofile
//    custom
//******************************************************************************

// Standalone server with the default profile.
ifeval::["{standalone-server-type}"=="default"]
:serverProfile: default profile
:configFileName: standalone/configuration/standalone.xml
:serverArguments:
endif::[]

// Standalone server with the full profile.
ifeval::["{standalone-server-type}"=="full"]
:serverProfile: full profile
:configFileName: standalone/configuration/standalone-full.xml
:serverArguments:  -c standalone-full.xml
endif::[]

// Standalone server with the full HA profile.
ifeval::["{standalone-server-type}"=="full-ha"]
:serverProfile: full HA profile
:configFileName: standalone/configuration/standalone-full-ha.xml
:serverArguments:  -c standalone-full-ha.xml
endif::[]

// Start the standalone server with the HA profile.
ifeval::["{standalone-server-type}"=="ha"]
:serverProfile: HA profile
:configFileName: standalone/configuration/standalone-ha.xml
:serverArguments:  -c standalone-ha.xml
endif::[]

// Start the standalone server with the Eclipse MicroProfile profile.
ifeval::["{standalone-server-type}"=="microprofile"]
:serverProfile: MicroProfile profile
:configFileName: standalone/configuration/standalone-microprofile.xml
:serverArguments:  -c standalone-microprofile.xml
endif::[]

// Standalone server with the custom profile.
// NOTE: This profile requires that you define the `serverArguments` variable
// within the quickstart README.adoc file. For example:
//  :serverArguments: --server-config=../../docs/examples/configs/standalone-xts.xml
ifeval::["{standalone-server-type}"=="custom"]
:serverProfile: custom profile
endif::[]

// If there is no match, use the default profile.
ifndef::serverProfile[]
:standalone-server-type:  default
:serverProfile: default profile
:configFileName: standalone/configuration/standalone.xml
:serverArguments:
endif::serverProfile[]

. Open a terminal and navigate to the root of the {productName} directory.
. Start the {productName} server with the {serverProfile} by typing the following command.
+
ifdef::uses-jaeger[]
[source,subs="+quotes,attributes+",options="nowrap"]
----
$ __JAEGER_REPORTER_LOG_SPANS=true JAEGER_SAMPLER_TYPE=const JAEGER_SAMPLER_PARAM=1__ __{jbossHomeName}__/bin/standalone.sh {serverArguments}
----
endif::[]
ifndef::uses-jaeger[]
[source,subs="+quotes,attributes+",options="nowrap"]
----
$ __{jbossHomeName}__/bin/standalone.sh {serverArguments}
----
endif::[]
+
NOTE: For Windows, use the `__{jbossHomeName}__\bin\standalone.bat` script.

ifdef::mobileApp[]
+
Adding `-b 0.0.0.0` to the above command allows external clients, such as phones, tablets, and desktops, to connect through your local network. For example:
+
[source,subs="+quotes,attributes+",options="nowrap"]
----
$ __{jbossHomeName}__/bin/standalone.sh {serverArguments} -b 0.0.0.0
----
endif::[]

:leveloffset!:
// Build and Deploy the Quickstart
:leveloffset: +2

[[build_and_deploy_the_quickstart]]
= Build and Deploy the Quickstart
//******************************************************************************
// Include this template if your quickstart does a normal deployment of a archive.
//
// * Define the `archiveType` variable in the quickstart README file.
//   Supported values:
//    :archiveType: ear
//    :archiveType: war
//    :archiveType: jar
//
// * To override the archive name, which defaults to the {artifactId),
//   define the `archiveName` variable, for example:
//    :archiveName: {artifactId}-service
//
// * To override the archive output directory,
//   define the `archiveDir` variable, for example:
//    :archiveDir: ear/target
//
// * To override the Maven command, define the `mavenCommand` variable,
//   for example:
//    :mavenCommand: clean install wildfly:deploy
//******************************************************************************

// The archive name defaults to the artifactId if not overridden
ifndef::archiveName[]
:archiveName: {artifactId}
endif::archiveName[]

// The archive type defaults to war if not overridden
ifndef::archiveType[]
:archiveType: war
endif::archiveType[]

// Define the archive file name as the concatenation of "archiveName" + "." + "archiveType+
:archiveFileName: {archiveName}.{archiveType}

// If they have not defined the target archive directory, make it the default for the archive type.
ifndef::archiveDir[]

ifeval::["{archiveType}"=="ear"]
:archiveDir: {artifactId}/ear/target
endif::[]

ifeval::["{archiveType}"=="war"]
:archiveDir: {artifactId}/target
endif::[]

ifeval::["{archiveType}"=="jar"]
:archiveDir: {artifactId}/target
endif::[]

endif::archiveDir[]

ifndef::mavenCommand[]
ifeval::["{archiveType}"=="ear"]
:mavenCommand: clean install
endif::[]

ifeval::["{archiveType}"=="war"]
:mavenCommand: clean package
endif::[]

ifeval::["{archiveType}"=="jar"]
:mavenCommand: clean install
endif::[]

endif::mavenCommand[]

. Make sure you xref:start_the_eap_standalone_server[start the {productName} server] as described above.
. Open a terminal and navigate to the root directory of this quickstart.
ifdef::reactive-messaging[]
. Run this command to enable the MicroProfile Reactive Messaging functionality on the server
+
[source,subs="attributes+",options="nowrap"]
----
$ __{jbossHomeName}__/bin/jboss-cli.sh --connect --file=enable-reactive-messaging.cli
----
endif::reactive-messaging[]
. Type the following command to build the quickstart.
+
[source,subs="attributes+",options="nowrap"]
----
$ mvn {mavenCommand}
----

. Type the following command to deploy the quickstart.
+
[source,subs="attributes+",options="nowrap"]
----
$ mvn wildfly:deploy
----

ifdef::rest-client-qs[]
This builds and deploys the `country-server` and `country-client` to the running instance of the server.

You should see a message in the server log indicating that the archives deployed successfully.
endif::[]
ifndef::rest-client-qs[]
This deploys the `{archiveDir}/{archiveFileName}` to the running instance of the server.

You should see a message in the server log indicating that the archive deployed successfully.
endif::[]


:leveloffset!:

=== Access the Application

The application will be running at the following URL: http://localhost:8080/{artifactId}/.

=== Server Log: Expected Warnings and Errors

You will see the following warnings in the server log. You can ignore these warnings.

[source,options="nowrap"]
----
WFLYJCA0091: -ds.xml file deployments are deprecated. Support may be removed in a future version.
----

// Testing with Arquillian
:leveloffset: +2

[[run_the_arquillian_integration_tests_with_server_distribution]]
= Run the Arquillian Integration Tests
//******************************************************************************
// Include this template if your quickstart provides standard Arquillian
// integration tests.
//******************************************************************************

This quickstart includes Arquillian integration tests. They are located under the  `src/test/` directory. The integration tests verify that the quickstart runs correctly when deployed on the server.

Follow these steps to run the integration tests.

. Make sure you start the {productName} server, as previously described.

. Make sure you build and deploy the quickstart, as previously described.

. Type the following command to run the `verify` goal with the `arq-remote` profile activated.
+
[source,options="nowrap"]
----
$ mvn verify -Parq-remote
----

[NOTE]
====
You may also use the environment variable `SERVER_HOST` or the system property `server.host` to define the target host of the tests.
====

:leveloffset!:
// Undeploy the Quickstart
:leveloffset: +2

[[undeploy_the_quickstart]]
= Undeploy the Quickstart

//*******************************************************************************
// Include this template if your quickstart does a normal undeployment of an archive.
//*******************************************************************************
When you are finished testing the quickstart, follow these steps to undeploy the archive.

. Make sure you xref:start_the_eap_standalone_server[start the {productName} server] as described above.
. Open a terminal and navigate to the root directory of this quickstart.
. Type this command to undeploy the archive:
+
[source,options="nowrap"]
----
$ mvn wildfly:undeploy
