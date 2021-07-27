# Deployment to Kubernetes

You can run Pyrrha as a standalone Docker container on your laptop, a Raspberry Pi device, or another computer. But you can also deploy it to a Kubernetes cluster such as the [IBM Container Service](https://www.ibm.com/cloud/container-service/) or [Red Hat OpenShift](https://www.ibm.com/cloud/openshift).

## Set up a Kubernetes cluster on the IBM Cloud

Register for an [IBM Cloud account](https://developer.ibm.com/dwwi/jsp/register.jsp?eventid=cfc-2020-projects), then set up a [free single worker node Kubernetes cluster](https://cloud.ibm.com/docs/containers?topic=containers-getting-started#clusters_gs).

Note: You can also choose a more scalable Kubernetes or OpenShift cluster, but those are not free.

- In the [IBM Cloud Catalog](https://cloud.ibm.com/catalog?category=containers), select **Kubernetes Service**. A cluster configuration page opens.
- From the plan dropdown, select the **Free** cluster option.
- Give your cluster a unique name, such as `Pyrrha-free`.
- Select a resource group to create the cluster in, such as `default`.
- In the **Summary** pane, review the order summary and then click **Create**. A worker pool is created that contains one worker node in the default resource group.

While your cluster is provisioning, set up your local workstation with the client tools.

- Download and install a few CLI tools and the Kubernetes Service plug-in.

  ```shell-script
  curl -sL https://ibm.biz/idt-installer | bash
  ```

- Log in to your IBM Cloud account. Include the --sso option if you have a federated ID.

  ```shell-script
  ibmcloud login -a cloud.ibm.com -r us-south -g default
  ```

- Set the Kubernetes context to your cluster for this terminal session. This command will fail if the cluster isn't yet ready.

  ```shell-script
  ibmcloud ks cluster config --cluster <your cluster id>
  ```

- Verify that you can connect to your cluster.

  ```shell-script
  kubectl config current-context
  ```

- Now, you can run `kubectl` commands to manage your cluster on the IBM Cloud. For a full list of commands, see the [Kubernetes docs](https://kubectl.docs.kubernetes.io/).

## Run a deployment containing the Docker container

- TBD upon completion of deployment configurations 
