# Prometheus Lab 2 #

## Presented by: ##
***Mustafa Ahmed***
#### 8 August 2023 #### 
***
### 1- How do I trigger a Prometheus alert?

####  1-  Set up Prometheus.
####  2-  Define alerting rules using PromQL.
####  3- Configure alert managers.
####  4- Test and validate alerting rules.
####  5- Simulate or generate conditions that match the alerting rules to trigger an alert.
***
### 2- What is the difference between a node exporter and a MySQL exporter? 


 ####   1- Node Exporter: 
 ##### The Node Exporter is a Prometheus exporter specifically designed to collect system-level metrics from the host machine. It provides details about CPU usage, memory usage, disk usage, network statistics, and other basic system information.

 ####  2- MySQL Exporter:
 ##### The MySQL Exporter is a Prometheus exporter specifically designed to collect metrics from MySQL databases. It provides detailed metrics about the MySQL server, such as query execution time, slow queries, connection statistics, cache utilization, and other database-specific metrics.
***
#### 3- what is the maximum retention period to save data in Prometheus and how to increase it?
##### The maximum retention period to save data in Prometheus is determined by the configured retention time in the Prometheus storage configuration. By default, Prometheus retains data for 15 days.

##### To increase the retention period in Prometheus, you need to modify the storage.tsdb.retention.time parameter in the Prometheus configuration file. Set it to the desired duration, specifying the time in a suitable format (e.g., 30d for 30 days or 6w for 6 weeks).

##### After updating the configuration, restart the Prometheus server for the changes to take effect. This will extend the retention period, allowing Prometheus to store data for a longer duration. Keep in mind that increasing the retention period will also increase the storage requirements for Prometheus.
***
#### 4- What are the different PromQL data types available in the Prometheus Expression language?


##### Scalars: Scalars represent single numeric values and are used for metrics like CPU usage, memory usage, or any other numerical measurements. Scalars can be integers or floating-point numbers.

#####  Vectors: Vectors represent a set of time-series data, where each time-series has a label set. They are used to query and manipulate multi-dimensional data. Vectors can have zero or more data points, making them suitable for operations like filtering, aggregating, and performing calculations on specific groups of time-series.

##### Strings: Strings represent text or string values. They are useful for working with metric labels, annotations, or any other string-based data in Prometheus
***
#### 5- How To calculate the average request duration over the last 5 minutes from a histogram?

#####   Calculate the quantile value for the histogram using the histogram_quantile function.
###### histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))
 #####   Calculate the average over the range vector.
 ###### avg_over_time(histogram_quantile(0.95, sum(rate(http_request_duration_seconds_bucket[5m])) by (le))) .

***

#### 6- What is Thanos Prometheus?
##### Thanos Prometheus is an open-source project that extends Prometheus by providing long-term storage, horizontal scalability, and global query capabilities. It enables storing and querying Prometheus data across multiple clusters, improving fault tolerance and enabling efficient long-term data retention.
***
    
  #### 7- What is Promtool and how i can use it?
  ##### To use Promtool:

  ###### Install Prometheus: First, you need to install Prometheus on your system. Promtool is bundled with Prometheus, so you will have access to it once Prometheus is installed.

##### Access the command line: Open your terminal or command prompt and navigate to the directory where Prometheus is installed.

##### Run Promtool commands: Promtool provides various subcommands to validate different aspects of Prometheus configurations. Here are some commonly used commands:

##### check-config: This command checks the correctness of the Prometheus configuration file (prometheus.yml) and reports any errors or warnings.
##### check-rules: This command validates the alerting and recording rules defined in a rules file and ensures their correctness.

##### lint: This command performs a general linting of the Prometheus configuration and rule files, highlighting any potential issues or inconsistencies.
#####  test: This command allows you to test a rule expression against a given range of time to validate its behavior.
***
#### 8- What types of Monitoring can be done via Grafana?
###### Infrastructure monitoring: Grafana can be used to monitor the performance and availability of infrastructure components such as servers, networks, and storage devices.
###### Application monitoring: Grafana can be used to monitor the performance and availability of applications. This includes monitoring metrics such as CPU usage, memory usage, and database queries.
###### Log monitoring: Grafana can be used to monitor logs from applications and infrastructure components.
###### Alerting: Grafana can be used to create alerts that notify you when certain metrics or events occur.
###### Dashboards: Grafana can be used to create dashboards that display your metrics and logs in a visually appealing way.
##### Security monitoring: Grafana can be used to monitor security metrics such as login attempts, failed logins, and unauthorized access.
***

#### 9- Can we see different Servers' CPU comparisons in Grafana?
###### Yes, you can see different servers' CPU comparisons in Grafana.



