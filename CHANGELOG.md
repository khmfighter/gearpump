gearpump-0.3.5
=====================
Change list
------------------
 - #729 remove argument '-master' in YARN service and documents.
 - #759, fix storm connector bug due to unstable topology sort of DAG
 - #775, fix netty config
 - #778, log improvements
 - #781 when launching lots of tasks, the application failed to transfer message across hosts 
 - #782, a) add wildcard match to return metrics(support glob char … and *), b) add diagnosis message if the clock stop advancing
 - #786, Read user config from classpath, the appmaster/executor wil use the dynamic user config
 - #773: skew chart will show relative skew
 - #790, 1) return detail task data in appmaster REST. 2) bind executor id with executor system id
 - #795 TaskScheduleImpl'bug when executor failed
 - #799 Getting 2.10 cross build working
 - #802 add process id and host name in executor log file
 - #803: (1) websocket is by default not preferred (2) throughput should be added as sum not mean (3) changed input/output message to sink/source processor receive/send throughput
 - #805, metrics rest service should return latest metrics received
 - #684 - setting -Xmx for master and worker when running on Yarn This will prevent JVMs from growing above limits and get killed by Yarn
 - #796: (1) added executor info (2) fixed skew chart issue for the first node
 - #801, add config service for master and worker.
 - #741 add a example transport use case
 - #814, expose TaskActor.minClock through TaskContext
 - #741 refine example
 - #817 split examples jar into multiple jars
 - #824, allow to use default partitioner when defining a DAG
 - #829, add some handly operator like groupByKey, sum, for KV Stream
 - #831: uses pagination control to speedup table rendering
 - #816: use multi-select control to select tasks
 - #840: task charts data were incorrect
 - #844, expose upstream minclock
 - #204, page rank demo code
 - #846, support more anyVals in user config
 - #843, Can't put custom user config in application.conf
 - #849, set default hostname to 127.0.0.1 in UT
 - #851, JVM not exited when there is exception due to akka create non-daemon threads
 - #854， fix storm connector performance
 - #856， Service launch failed
 - #853, fix resource leak(thread not closed, process not killed in UT. Also increase the PermGen size to avoid Permgen OOM.
 - #859, random UT fail due to akka bug, "akka cluster deadlock when initializing"
 - #865, Change the default timeout setting in akka test expectMsg
 - #871, Add explicit error log for kryo serialization exception
 - #877: source node and sink node were not calculated correctly.
 - #874, [TaskActor] task onStart should be called after the network transport layer is ready
 - #879: split metrics into different views and changed tooltip control
 - #881: diverse issues of skew charts and made tooltip nice
 - #876: clock is updated every second-
 - #885: wrong application clock in some case
 - #53, rest interface to submit a dag by JSON representation
 - #887, add a rest to get stalling tasks
 - #801: added download links for configurations-
 - #742 add a rest to get Gearpump version
 - #898, Downgrade akka version from 2.3.9 to 2.3.6
 - #900, Use gearpump.hostname by default=
 - #719 add Kafka Source and HBase Sink for dsl
 - #905: Upgrade sbt-pack from 0.6.8 to 0.6.9
 - #602: dashboard will freeze when server is unreachable
 - #907: calculate application clock update frequence for a 30 second time frame
 - #919: vis.js's version was not updated 

gearpump-0.3.4
====================
Change List:
----------------
 - #768, Serious performance degration of ui server on windows
 - #765, improve the graph type inference so we don't need to set template argument type explicitly

gearpump-0.3.3
====================
Change List:
----------------
 - #716, Refine the user interface. improve the user interface, like Application, Processor
 - #755, fix Build breakage, 
 - #729, remove argument '-master' in command line option, use gear.conf instead.
 - #713, provide an option to read from beginning of a topic 
 - #746, support state clock for task so that we can retrieve the state timestamp
 - #744: fix several metrics issues
 - #638, Use Subscription to link two processor
 - #662, [UI] added processor  details tab
 - #735, [yarn]Launch UI in the same container of Yarn AppMaster container.
 - #732: [UI]add more charts and add more metrics to dag
 - #731 rename TaskDescription to ProcessorDescription
 - #708, fix storm connector config classpath 
 - #722: [UI]use different color and opacity for edges
 - #708, allow user to pass in a customized storm config
 - #709: [UI]npe when streaming dag is not initialized
 - #704, DAG processor name is "undefined" if "description` field of TaskDescription is not defined
 - #706, Remove example jars from gearpump built-in classpath.
 - #701 add a HBase sink
 - #28, add an experiment module to support a very basic flatmap dsl
 - #666, add UI for stock crawler example
 - #691: [UI] fix metrics
 - #680, add a service in appmaster to support query of task actorRef
 - #210, allow easier remote debugging executor process
 - #666, add a stock index crawler example,
 - #658 make config of Gearpump on Yarn configurable
 - #676, add a storm connector to allow user to run arbitrary storm jar
 - #657, remove unnecessary yarn deps
 - #672, extend Task to support unmanaged messages so that every task can serve as full functional service
 - #670, fix yarn application path and log path
 - #665, Add scheduleOnce interface in TaskContext

gearpump-0.3.2
====================
Change List:
 - #654, Use yarn to distribute whole gearpump package instead of jars
 - #631, remove unnecessary storm dependencies
 - #652, log conflict between slf4j and log4j
 - #652, log is muted when running on yarn
 - #650, remove logback classic slf4j binding from classpath
 - #648, yarn unable to start worker
 - #27, Integrate YARN into scheduler
 - #643: metrics tables are now sortable
 - #639, fix parallelism is 0 on GlobalGrouping
 - #636, fix FieldsGroupingPartitioner
 - #629 - query backend for actual websocket address 
 - #634: create websocket can be failed when url is undefined
 - #415, support storm connector
 - #613, Show metrics charts in application's detail page
 - #546 add a rest api to query WebSocket url
 - #624, add description field to TaskDescription
 - #434 add api/v1.0 prefix for all rest services
 - #618 fix no data returned when call Metrics rest
 - #607, bump up kafka version to 0.8.2.1
 - #615, Incorrect Dag edge width
 - #608 increase the maximum frame size of Akka
 - #611: dag looks more elegant
 
gearpump-0.3.1
====================
Change List:
- #591, (1) added metrics to application detail page (2) periodically update page contents without pressing refresh (3) replaced angular-dashboard-framework with bootstrap + angular
- #600, Config API should return all config under section "gearpump"
- #597, by default, app wil run for ever except you kill it explicitly.
- #595, use smaller metrics interval
- #417, update READ.ME and refactor DistributedShell
- #388, catch netty channel close exception and warn
- #589, change applicationData's timestamp to 24-h format
- #417, deploy a service across the cluster
- #568, enable history metrics service
- #584, KafkaOffsetManager should only stores one offset per timestamp 
- #562 fix AppMaster and Executor restart infinitely
- #576, Add processor level for REST returned DAG, so that the UI can render the DAG correctly.
- #568, [REST] add history metrics service in backend 
- #571 AppMaster failed to recover
- #569, dag cannot be rendered
- #566, a) add rest service to shutdown an application b) add a rest service to provide app configuration
- #564, REST should return more data for Application information
- #561, add more task metrics
- #558, [REST]Add missing "name" field for metric Histogram
- #556, Use "Processor" to replace taskGroup in source code
- #555, DAG data returned should contains processor Id
- #544, (1) dashboard will now request appmaster details only once 2) visdag is no longer a widget of adf (3) reduced animation of visdag
- #526, Kafka tests are failing in master branch
- #467, Expose codahale metrics by rest service
- #526, temporary disabled kafka examples to make build pass
- #513, Several remain UI issues in new dashboard, like version tag in dashboard
- #516, Travis failed to deploy the binary to github release

gearpump-0.3.0-rc1
====================
Change List:
---------------
 - #510, add log directory for UI server
 - #485, retain inactive application history in Master
 - #504, 1) AppMaster return more detailed application runtime information. 2) fix a worker bug when returning executors which run on worker. 
 - #422, [UI] show the number of executors (2) changed layout of application page
 - #417, add a experiment module to distribute a zip file to different machines
 - #502, fix KafkaStorage loading data for async kafka consumer
 - #422, [UI] (1) added home directory in UI (2) removed millis from duration 3) updated dag control height
 - #476, fix worker and master log path format in rest service
 - #498, worker rest data is not updated in UI
 - #397, move distributed shell from experiments to examples folder
 - #493 add implicit sender so that the Task can send itself messages[work around]
 - #427, use new kafka producer in kafka 0.8.2
 - #422, added cluster page to show master and worker information
 - #489, make the worker rest information easier to parse
 - #202, Add a default serializer for all kinds of messages
 - #477, REST Workers should return more information
 - #456, uses webjars to serve visjs 3.10.0
 - #483, upgrade visdag to 3.10 because widget does not repaint correctly when a node is moved
 - #473, Use webjars with spray support instead of bower to serve static resources
 - #477, return more data for rest call workers/
 - #474, fix rest service UT test fail.
 - #479, publish test jar as artifacts
 - #419, Reorder the application log by master startup timestamp
 - #456, Use visdag to render the graph DAG
 - #464， Travis bower integration
 - #394, fix kafka producer hang issue
 - #468, For test code, the ClockService will throw excepton when the DAG is not defined
 - #465, fix appname prefix bug
 - #461, AppMasterSpec and WorkServiceSpec UT are failing 
 - #270, Create a force-direct dag 
 - #453, Add rest service to serve master info 
 - #423, refactor task by seperating TaskActor and Task
 - #422, add worker rest api
 - #449: avoid load external resource by removing all CDN external links
 - #397 refactor distributed shell by using new Cluster API
 - #441, ui-portal is failed to build because of spray version conflict
 - #430 use application name as unique identifier for an application
 - #440, moved dashboard code from conf to service/dashboard
 - #402, refactor task manager
 - #280, Add websockets to REST api
 - #269, Define UI Dashboard structure
 - #406, custom executor jvm config in gear.conf is not effective.
 - #394, fix ActorSystemBooter process not shut down after application finishes
 - #412, add version.sbt 
 - #410 Add sbt-eclipse plugin and wiki for how to build gearpump on eclipse
 - #408, handle Ctrl+C(sigint) gracefully.
 - #396, bump up kafka version to 0.8.2.0
 - #398, Expose more metrics info
 - #389, fix kafka fetch thread bug 
 - #386 UT fail due to unclosed sequence file
 - #370, refactor streaming appmaster
 - #358, use uPickle for REST Service
 - #372, fix DAG subgraph build and more Graph UT
 - #377, fix KafkaSource.pull performance due to the List.append is not having good performance
 - #378, construct the serializer explicitly, instead of implicitly via the kryo serializer akka extension
 - #380, set the context class loader as the URL class loader for ActorSystem.


gearpump-0.2.3
====================
Change List:
---------------
 - #333, KafkaUtilSpec causes out of memory on travis
 - #335, #359， Enable auto-deployment to sonatype
 - #299, Some UT may fail randomly, most because of the expectMsg time out
 - #338, fix kafka leader not available exception
 - #349, scoverage dependencies get into snapshot build binaries.
 - #352, add RollingCountSpec
 - #356, User's application.conf can not be loaded due to empty config.
 - #373, add more restrict checks for warning, deprecation and feature

gearpump-0.2.2
====================
Change List:
-----------------
 - #327 fix 0.2.1 build error
 - #308 add another dag example project
 - #330 Allow user to output the metrics to log file besides graphite

gearpump-0.2.1
====================

Change List:
-----------------
 - #244, add more UT, 
 - #250, refactor kafka implementations
 - #301, fix UserConfig ClassNotFoundException
 - #306, ClassNotFound for customized Application type
 - #299 fix SeqFileStreamProcessorSpec
 - #320 fix dead lock in StreamTestUtil.createEchoTaskActor
 - #317, allow user to customize the akka system config for appmaste… 
 - #244, add KafkaUtilSpec and kafka integration test

gearpump-0.2
=========================

Highlights:
-----------------
 - Published a tech paper about the design on https://typesafe.com/blog/gearpump-real-time-streaming-engine-using-akka
 - UT coverage rate to 70%
 - Add support for general replay-able data source to support at least once delivery. 
 - More robust streaming. Be resilient to message loss, message duplication, and zombie processes. 
 - Refactor Kafka data source for at least once delivery.
 - Support general applications besides streaming, add an experimental distrubtedshell application under experiments/.
 - Re-defined the AppMaster, and Task interface, It is much easier to write an application now.
 - Support submitting and distributing large applications jars.
 - Add CI tool, nightly build, code coverage, and defined a formal commit guideline.

Change list:
-------------------
 - #274 AppMaster cannot connect to worker if there are multiple interface on one machine 
 - #272 Too many dead log mesages in the log
 - #266 Kafka grouper conf is incorrect 
 - #259 fix stream replay api and impl
 - #245 jacoco conflict with codecov
 - #244 Add more unit test for better test coverage
 - #242 Add application sumbittor username so that we can seperate the logs for different user
 - #239 REST AppMasterService test failed
 - #237 Add more information in log line
 - #233 Add TIMEOUT for interactive messages between two parties
 - #230 Executor fails to connect with AppMaster when in a multiple NIC environment
 - #229  Add a default cluster config under conf/
 - #226 return error message to user if not enough slots
 - #225 Gearpump logging application logs to different streams(and to persistent storage)
 - #222 TimeStampFilter implementation is wrong
 - #221 AppMastersDataRequest, AppMasterDataRequest and AppMasterDataDetailRequest should return information about failed appmaster attempts
 - #217 Write a small custom AppMaster example, which can run distributed shell.
 - #216 Support large application jars
 - #215 Improve the API and configs so it more easy to write and submit a new application.
 - #213 Add documents about how we do benchmark
 - #212 when network partition happen there maybe zombie tasks still sending messages for a while
 - #208 Support long-running applications
 - #196 When AppMasterStarter fails to load a class, the whole Gearpump cluster crash
 - #191 Add docs for all examples
 - #184 When packing example to a uber jar, should not include core and streaming jars
 - #176  Fix NPE for REST /appmaster/0?detail=true when no appmasters have launched
 - #169 Convert REST CustomSerializers to extend DefaultJsonProtocol
 - #162 version conflicts between dependencies of sub projects  bug
 - #148 Revert code to be Java 6 compatible
 - #145 Add instructions document for Gearpump commit process
 - #138 Update ReadMe.md project description
 - #135 Add travis build|passing status icon to README.md
 - #130 AppMaster, TaskActor class references should not be explicitly referenced in SubmitApplication and TaskDescription  - messages
 - #127 Document how to run coverage reports, fix sigar exception seen during tests.
 - #117 Fix style and code warnings, use slf4j where appropriate  
 - #116 Add unit tests to gearpump-core
 - #115 Setup travis CI and codecov.io for Gearpump
 - #112 Break up examples into separate projects as prerequisite to #100
 - #110 Netty Java code cleanup
 - #108 Spout and Bolt classes should be renamed
 - #106 Add unit tests for REST api  
 - #104 ActorInitializationException while running wordCount in local mode
 - #103 Build error, unable to resolve akka-data-replication
