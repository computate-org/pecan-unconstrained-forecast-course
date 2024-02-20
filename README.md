

# PEcAn Unconstrained Ecological Forecast Course

## Written by [Christopher Tate](https://www.computate.org/)

- Red Hat Principal Software Engineer in Red Hat Research 

- Creator of the Smart Village Operator and Smart Village Platform 

- Architect of the Red Hat Social Innovation Program 

- Founder of the Smarta Byar Smart Village Community FIWARE Innovation Hub 

- Principal Software Engineer for the New England Research Cloud

## OpenShift cluster prerequisites

### Clone the pecan-unconstrained-forecast-course

Create a source directory for the pecan-unconstrained-forecast-course 
and clone the pecan-unconstrained-forecast-course with git. 

```bash
mkdir -p ~/.local/src/pecan-unconstrained-forecast-course
git clone https://github.com/computate-org/pecan-unconstrained-forecast-course.git ~/.local/src/pecan-unconstrained-forecast-course
```

### Deploy the OpenShift AI Operator

As a cluster admin, deploy the OpenShift AI Operator 
and Wait for the OpenShift AI Operator to be installed. 

```bash
oc apply -k ~/.local/src/pecan-unconstrained-forecast-course/kustomize/bundles/openshift-ai/base/

oc -n redhat-ods-operator wait csv -l operators.coreos.com/rhods-operator.redhat-ods-operator="" --for=jsonpath={.status.phase}='Succeeded'
```


```bash
```

### Deploy a Data Science Cluster

Deploy a Data Science Cluster and wait for it to be ready. 

```bash
oc apply -k ~/.local/src/pecan-unconstrained-forecast-course/kustomize/bundles/openshift-ai/app/datascienceclusters/

oc -n redhat-ods-operator wait datasciencecluster/default-dsc --for=jsonpath='{.status.phase}'='Ready'
```

### Deploy R Studio and PEcAn Unconstrained Forecast Image Streams

Deploy the R Studio and PEcAn Unconstrained Forecast Image Streams to OpenShift AI. 

```bash
oc apply -k ~/.local/src/pecan-unconstrained-forecast-course/kustomize/bundles/openshift-ai/app/imagestreams/
```

### Create a PEcAn Data Science Project in OpenShift AI

In the OpenShift Console, open the OpenShift AI app. 

![Open the OpenShift AI app](pictures/openshift-apps-openshift-ai.png "Open the OpenShift AI app") 

Click on ![Data Science Projects](pictures/button-data-science-projects.png "Data Science Projects")

Click on ![Create Data Science Project](pictures/button-create-data-science-project.png "Create Data Science Project")

Create a Data Science Project named: `pecan`

![Create Data Science Project](pictures/form-create-data-science-project.png "Create Data Science Project")

Click on ![Create](pictures/button-create.png "Create")

Click on ![Create Workbench](pictures/button-create-workbench.png "Create Workbench")

Create a workbench named: `pecan-unconstrained-forecast`

With image selection: `PEcAn Unconstrained Forecast`

Click on ![Create Workbench](pictures/button-create-workbench.png "Create Workbench")


