this dockerfile is used in order to build a container that runs the quarkus application in jvm mode

before building the container image run:

./gradlew build

then, build the image with:

docker build -f src/main/docker/dockerfile.jvm -t quarkus/gca-argocd-api-jvm .

then run the container using:

docker run -i --rm -p 8080:8080 quarkus/gca-argocd-api-jvm

if you want to include the debug port into your docker image  
you will have to expose the debug port (default 5005 being the default) like this : expose 8080 5005.  
additionally you will have to set -e java_debug=true and -e java_debug_port=*:5005  
when running the container

then run the container using :

docker run -i --rm -p 8080:8080 quarkus/gca-argocd-api-jvm

this image uses the `run-java.sh` script to run the application.  
this script computes the command line to execute your java application, and  
includes memory/gc tuning.  
you can configure the behavior using the following environment properties:

- java_opts: jvm options passed to the `java` command (example: "-verbose:class") - be aware that this will override  
    the default jvm options, use `java_opts_append` to append options
    
- java_opts_append: user specified java options to be appended to generated options  
    in java_opts (example: "-dsome.property=foo")
    
- java_max_mem_ratio: is used when no `-xmx` option is given in java_opts. this is  
    used to calculate a default maximal heap memory based on a container's restriction.  
    if used in a container without any memory constraints for the container then this  
    option has no effect. if there is a memory constraint then `-xmx` is set to a ratio  
    of the container available memory as set here. the default is `50` which means 50%  
    of the available memory is used as an upper boundary. you can skip this mechanism by  
    setting this value to `0` in which case no `-xmx` option is added.
    
- java_initial_mem_ratio: is used when no `-xms` option is given in java_opts. this  
    is used to calculate a default initial heap memory based on the maximum heap memory.  
    if used in a container without any memory constraints for the container then this  
    option has no effect. if there is a memory constraint then `-xms` is set to a ratio  
    of the `-xmx` memory as set here. the default is `25` which means 25% of the `-xmx`  
    is used as the initial heap size. you can skip this mechanism by setting this value  
    to `0` in which case no `-xms` option is added (example: "25")
    
- java_max_initial_mem: is used when no `-xms` option is given in java_opts.  
    this is used to calculate the maximum value of the initial heap memory. if used in  
    a container without any memory constraints for the container then this option has  
    no effect. if there is a memory constraint then `-xms` is limited to the value set  
    here. the default is 4096mb which means the calculated value of `-xms` never will  
    be greater than 4096mb. the value of this variable is expressed in mb (example: "4096")
    
- java_diagnostics: set this to get some diagnostics information to standard output  
    when things are happening. this option, if set to true, will set  
    `-xx:+unlockdiagnosticvmoptions`. disabled by default (example: "true").
    
- java_debug: if set remote debugging will be switched on. disabled by default (example:  
    true").
    
- java_debug_port: port used for remote debugging. defaults to 5005 (example: "8787").
    
- container_core_limit: a calculated core limit as described in  
    [https://www.kernel.org/doc/documentation/scheduler/sched-bwc.txt](https://www.kernel.org/doc/documentation/scheduler/sched-bwc.txt). (example: "2")
    
- container_max_memory: memory limit given to the container (example: "1024").
    
- gc_min_heap_free_ratio: minimum percentage of heap free after gc to avoid expansion.  
    (example: "20")
    
- gc_max_heap_free_ratio: maximum percentage of heap free after gc to avoid shrinking.  
    (example: "40")
    
- gc_time_ratio: specifies the ratio of the time spent outside the garbage collection.  
    (example: "4")
    
- gc_adaptive_size_policy_weight: the weighting given to the current gc time versus  
    previous gc times. (example: "90")
    
- gc_metaspace_size: the initial metaspace size. (example: "20")
    
- gc_max_metaspace_size: the maximum metaspace size. (example: "100")
    
- gc_container_options: specify java gc to use. the value of this variable should  
    contain the necessary jre command-line options to specify the required gc, which  
    will override the default of `-xx:+useparallelgc` (example: -xx:+useg1gc).
    
- https_proxy: the location of the https proxy. (example: "myuser@127.0.0.1:8080")
    
- http_proxy: the location of the http proxy. (example: "myuser@127.0.0.1:8080")
    
- no_proxy: a comma separated list of hosts, ip addresses or domains that can be  
    accessed directly. (example: "foo.example.com,bar.example.com")
    

from registry.access.redhat.com/ubi9/openjdk-21:1.21

env language='en_us:en'

copy --chown=185 build/quarkus-app/lib/ /deployments/lib/  
copy --chown=185 build/quarkus-app/*.jar /deployments/  
copy --chown=185 build/quarkus-app/app/ /deployments/app/  
copy --chown=185 build/quarkus-app/quarkus/ /deployments/quarkus/

expose 8080  
user 185  
env java_opts_append="-dquarkus.http.host=0.0.0.0 -djava.util.logging.manager=org.jboss.logmanager.logmanager"  
env java_app_jar="/deployments/quarkus-run.jar"

entrypoint [ "/opt/jboss/container/java/run/run-java.sh" ]