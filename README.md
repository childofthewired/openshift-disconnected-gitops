# openshift-disconnected-gitops

## aka: Project Genesis

Documenting the process of automating disconnected (airgapped) installations of Red Hat OpenShift using GitOps

### why operate OpenShift in an air gapped network?

It comes down to security and control. Data must be physically transferred into an air gapped environment. This means that exfiltration of data generated in the environment typylcally requires physical access to the systems in the air gapped environment.

This is typically used in Law Enforcement, the Military, Banking, Scientific Computing, and in industrial control networks.

### What tools do we have to work with?

OpenShift is part of a large ecosystem of tools that have been able to operate in disconnected networks. A lot of work was done by the Red Hat Government Team, and without them, the current tools wouldn't exist:


[oc-mirror - A tool for mirroring images, Operators and Helm charts stored in OCI registries](https://docs.openshift.com/container-platform/latest/installing/disconnected_install/installing-mirroring-disconnected.html)

[Mirror Registry for Red Hat OpenShift - A self contained Quay Registry built for disconnected environments](https://docs.openshift.com/container-platform/latest/installing/disconnected_install/installing-mirroring-creating-registry.html)


As an added difficulty, we will automate much of the Day2 operations of the cluster configuration using OpenShift GitOps.

The advantage of this, is that architects, developers, engineers and administrators looking to deploy a system like this can practice the deployment on a connected system and develop a working configuration. The tested and working configurations of OpenShift and the applications to be deployed may be configured as Applications in OpenShift GitOps and synced via git.

![This is a diagram of the disconnected Openshift environment](https://github.com/childofthewired/openshift-disconnected-gitops/blob/67edca520f4ddd3985c8ec57f8f3f121cd015c02/DisconnectedOpenShiftwithGitOpsDiagram.svg)