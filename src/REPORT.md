# Basic Kubernetes

The result of the work must be a report with detailed descriptions of the implementation of each of the points with screenshots. The report is prepared as a markdown file in the `src` directory named `REPORT.MD`.

## Part 1. Ready-made manifest

1) Run a Kubernetes environment with 4GB memory

<img src="./images/start4gb.png" width="700"/>

<img src="./images/status.png" width="700"/>

2) Apply the manifest from the `/src/example` directory to the created Kubernetes environment

<img src="./images/applyexample.png" width="700"/>

<img src="./images/showexample.png" width="700"/>

3) Run the standard Kubernetes control panel with the `minikube dashboard`

<img src="./images/dashexample.png" width="700"/>

4) Create tunnels to access the deployed services with the command `minikube services`

All services:

<img src="./images/alltunnels.png" width="700"/>

Only apache:

<img src="./images/serviceapache.png" width="700"/>

5) Check if the deployed application works by opening the application page in the browser (apache service)

<img src="./images/apache.png" width="700"/>

## Part 2. Your own manifest

1) Write your own yml-files of manifests for the application from the first project (`/src/services`) implementing the following:
   - Configuration map with the values of database hosts and services
   - Secrets with the password and login to the database and cross-service authorization keys (they can be found in the `application.properties` files)
   - Pods and services for all application modules: postgres, rabbitmq and 7 application services. Use a single replica for all services.

<img src="./images/manifest.png" width="700"/>

2) Run the application by sequentially applying manifests with the command `kubectl apply -f <manifest>.yaml`.

<img src="./images/apply.png" width="700"/>

3) Check the status of created objects (secrets, configuration map, pods and services) in the cluster using `kubectl get <object_type> <object_name>` and `kubectl describe <object_type> <object_name>`. Add the result to the report.

<img src="./images/get.png" width="700"/>

<img src="./images/dev1.png" width="700"/>
<img src="./images/dev2.png" width="700"/>
<img src="./images/dev3.png" width="700"/>
<img src="./images/dev4.png" width="700"/>
<img src="./images/dev5.png" width="700"/>
<img src="./images/dev6.png" width="700"/>
<img src="./images/dev7.png" width="700"/>
<img src="./images/dev8.png" width="700"/>
<img src="./images/dev9.png" width="700"/>
<img src="./images/dev10.png" width="700"/>
<img src="./images/dev11.png" width="700"/>
<img src="./images/dev12.png" width="700"/>
<img src="./images/dev13.png" width="700"/>
<img src="./images/dev14.png" width="700"/>
<img src="./images/dev15.png" width="700"/>
<img src="./images/dev16.png" width="700"/>
<img src="./images/dev17.png" width="700"/>

4) Check for correct secret values by applying, for example, the command: `kubectl get secret my-secret -o jsonpath='{.data.password}' | base64 --decode` to decode the secret.

<img src="./images/getsecretbase.png" width="700"/>

5) Check the logs of the application running in the cluster with the command `kubectl logs <container_name>`. Add a screenshot to the report.

<img src="./images/logbook.png" width="700"/>
<img src="./images/loggate.png" width="700"/>
<img src="./images/loghot.png" width="700"/>
<img src="./images/logloyal.png" width="700"/>
<img src="./images/logrep.png" width="700"/>
<img src="./images/logpay.png" width="700"/>
<img src="./images/logses.png" width="700"/>

6) Create tunnels to access the gateway service and session service.

<img src="./images/81.png" width="700"/>
<img src="./images/87.png" width="700"/>

7) Run postman functional tests and make sure that the application works.

<img src="./images/test.png" width="700"/>

8) Run the standard Kubernetes control panel with the command `minikube dashboard`. Include the following information in the report as screenshots from the dashboard: the current state of the cluster nodes, a list of running Pods, and other metrics such as CPU and memory utilization, Pod logs, configurations on the Pod and secrets.

<img src="./images/statusui.png" width="700"/>

<img src="./images/pod.png" width="700"/>

<img src="./images/node.png" width="700"/>

<img src="./images/secret.png" width="700"/>

<img src="./images/map.png" width="700"/>

9) Update the application (by adding a new dependency to the pom file), and rebuild the application with the following deployment strategies (measure the application re-deployment time for each case and note the results in the report):
   - recreate

<img src="./images/typerec.png" width="700"/>

<img src="./images/recreate.png" width="700"/>

   - rolling

<img src="./images/typerol.png" width="700"/>

<img src="./images/rolling.png" width="700"/>
