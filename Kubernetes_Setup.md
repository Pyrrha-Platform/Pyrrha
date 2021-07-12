# Deployment to Kubernetes

You can run the OpenEEW detection engine as a standalone Docker container on your laptop, a Raspberry Pi device, or another computer. But you can also deploy it to a Kubernetes cluster such as the [IBM Container Service](https://www.ibm.com/cloud/container-service/) or [Red Hat OpenShift](https://www.ibm.com/cloud/openshift).

## Set up a Kubernetes cluster on the IBM Cloud

Register for an [IBM Cloud account](https://developer.ibm.com/dwwi/jsp/register.jsp?eventid=cfc-2020-projects), then set up a [free single worker node Kubernetes cluster](https://cloud.ibm.com/docs/containers?topic=containers-getting-started#clusters_gs).

Note: You can also choose a more scalable Kubernetes or OpenShift cluster, but those are not free.

- In the [IBM Cloud Catalog](https://cloud.ibm.com/catalog?category=containers), select **Kubernetes Service**. A cluster configuration page opens.
- From the plan dropdown, select the **Free** cluster option.
- Give your cluster a unique name, such as `openeew-free`.
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

You can now deploy the `openeew/postgres` and `openeew/mqtt` apps to your cluster.

- Select your cluster from the [cluster list](https://cloud.ibm.com/kubernetes/clusters) to open the details for your cluster.
- Click **Kubernetes dashboard**.
- From the menu bar, click the **Create new resource** icon (+).
  - Update the **container image** in [openeew YAML](openeew.yaml)
  - If using a private image registry, update the **imagePullSecrets**
  - Copy the [openeew YAML](openeew.yaml)
  - In the **Create from input** box, paste the `openeew.yml` that you copied in the previous step.
  - Click **Upload**. The node port service and deployment is created.
- From the menu, click **Service > Services**. If using the defaults in the sample, the MQTT service will be named **openeew-mqtt-lb** and the Postgres service will be named **openeew-psql-lb**. Under the **External Endpoints** column, take note of the IP and and Port values in the form IP:Port. For example, `169.xx.xx.xxx:yy ` indicates your IP is `169.xx.xx.xxx` and your port is `yy`.
