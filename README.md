# docs-mysql-k8s
================

Documentation for VMware Tanzu™ SQL with MySQL for Kubernetes

## Which branch to use?

**Note**: Provide instructions in your PRs to indicate which branches you want Docs to apply your commits to.

| Branch name | Use for… |
|-------------| -------|
| main      | the development branch for the doc, publishes to https://docs-pcf-staging.cfapps.io/tanzu-mysql-kubernetes/1-n |
| 1.0      | v1.0 GA, publishes to http://docs.pivotal.io/tanzu-mysql-kubernetes/1-0/  This app must be `cf push`-ed manually. No concourse jobs or CI as of 2021.04.15.| 
| 0.2      | v0.2.x beta, publishes to http://docs.pivotal.io/tanzu-mysql-kubernetes/0-2/|
| 0.1      | v0.1.x beta, publishes to http://docs.pivotal.io/tanzu-mysql-kubernetes/0-1/|


## Where is the book repository?

The private book repo associated with this content repo is [**docs-book-mysql-k8s**](https://github.com/pivotal-cf/docs-book-mysql-k8s).



## Style Guide

This is a word list for terminology and word usage specific to the VMware Tanzu SQL with MySQL for VMs docs.

| Word | Explanation |
|------|-------------|
| admin | Use as a person's job description instead of operator. Decided: JD, Kim Bassett, and David Sharp 2020.12.09 and changed to admin because that's our house style. If this specifically refers to the Kubernetes admin, use "Kubernetes admin" in first use on the page. |
| connect | As in "connect an app to a service instance". Do not use "bind" unless you are referring to creating a [ServiceBinding](https://kubernetes.io/docs/concepts/extend-kubernetes/service-catalog/#binding-to-a-managed-service) resource.  |
| high-availability MySQL instance | Rather than "MySQL high-availability instance". Shorten to HA MySQL instance after first used. Also okay to shorten to HA instance if using the term a lot on a page.|
| Kubernetes admin | See "admin" above. |
| MySQL command-line client | [4.5.1 mysql — The MySQL Command-Line Client](https://dev.mysql.com/doc/refman/8.0/en/mysql.html) instead of the assorted "mysql CLI client" vs "mysql client" vs " local mysql client" |
| MySQL instance | Not MySQL cluster. From [A. Garner](https://github.com/pivotal-cf/docs-mysql-k8s/pull/28): "To avoid overloading "cluster" further, we now always reference the deployed MySQL as an "instance" rather than "cluster" within our config samples. Updated docs that reference the Tanzu MySQL configuration to replace "cluster" with "instance". Remaining usage of the word cluster are now reference a "Kubernetes cluster" or the default Kubernetes system domain("svc.cluster.local")." _Also see below._|
| MySQL instance  | Use this phrase consistently. Okay to shorten it to "instance". Not okay to use "Tanzu instance" or "database instance". "MySQL" is a _kind_ in Kubernetes so that is the precise term. Decided: JD, Kim Bassett, and David Sharp 2020.12.09. Changed TanzuMySQL -> MySQL (Shaan 2021.02.24)|
| MySQL Pod | Usually use this instead of just Pod. Decided: 2020.12.10 Judy and Jane |
| Operator | Don't use as a job description for a person. Use as the "MySQL Operator" or "Kubernetes Operator". Decided: 2020.12.10 Judy explained that the ~~Tanzu~~ MySQL Operator is a more precise term than the Kubernetes operator. The ~~Tanzu~~ MySQL Operator is a type of Kubernetes Operator. Use the capital "O" and in the first use on the page, preface with "Kubernetes" or something similar to show that it's a pattern and not a person.   _Note:_ 2021.04.02 After Judy left, we learned we can't write ~~Tanzu MySQL~~ because MySQL doesn't belong to the Tanzu brand.|
| Pod  | From the [word list](https://docs.google.com/spreadsheets/d/1hkadtxR1hY57kK7h5HN4ITHLJleZixCDH_RJPUpNq_A/edit?usp=sharing) See "MySQL Pod" below. |
| persistent volume claim (PVC)  | Spell out on first use on page.|
| single-node MySQL instance | Rather than "MySQL single-node instance". Okay to shorten to single-node instance if using the term a lot on a page.|
| ~~`mysql.yaml`~~ | Maybe: "your copy of the mysql.yaml file"? [JD] We don't want users to edit the `mysql.yaml` file directly. Instead, they use it as a template and create their own copy with a different name. We haven't a good term for that file yet. |
| `.yaml` | Instead of `.yml` |

## Placeholder Table

This is a place to keep track of the placeholder we use.
We want to use placeholders consistently throughout the doc.

| Placeholder | Sample | Explanation | Used in |
|-------------|--------|-------------|---------|
| DEVELOPMENT-NAMESPACE | my-namespace | "is the namespace in which you want to create the instance" or "is the namespace where you created the instance." | create-delete.html |
| REGISTRY-SERVER-URL |https://registry.tanzu.vmware.com/ |  is the TanzuNet registry or the private registry configured for your environment | create-delete.html|
| DOCKER-PASSWORD | sample-password | credentials used to pull images from the registry | create-delete.html |
| DOCKER-USERNAME |sample-username |  credentials used to pull images from the registry | create-delete.html |
| INSTANCE-NAME | mysql-sample and another-sample |   is the value that you configured for metadata.name in the mysql.yaml deployment template | create-delete.html, accessing.html |
| INSTANCE-NAME-N (use instead of POD-NAME)| mysql-sample-0 | "Where: + `INSTANCE-NAME` is the value that you configured for metadata.name in the mysql.yaml deployment template. + `N` is the index of the Pod in the MySQL instance." | create-delete-mysql.html, update-instance.html |
| REGISTRY-SERVER-URL |https://registry.tanzu.vmware.com/ |  is the TanzuNet registry or the private registry configured for your environment | create-delete.html|
| TLS-SECRET-NAME |mysql-tls-secret | the name you choose for the TLS Secret.  | configure-tls.html|
|
