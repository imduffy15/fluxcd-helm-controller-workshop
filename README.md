# Exploring Helm Controller Failure Scenarios Workshop

This repository serves as a comprehensive workshop to explore failure scenarios associated with Helm Controller in Kubernetes clusters. The primary goal is to simulate various failure conditions, observe how Helm Controller and HelmRelease objects respond, and understand the recovery strategies.

## Self evaluation

After completing the workshop, you should be able to confident answer all of the following questions:

### Understanding Helm Controller and HelmRelease:

- What is Helm Controller, and how does it simplify managing Helm releases in Kubernetes clusters?
- How are HelmRelease objects used to define Helm chart releases in a Kubernetes cluster?
- What role do Helm values files play in configuring HelmRelease objects?

### Exploring Failure Scenarios:

- Can you name at least 10 different failure scenarios that were simulated during the workshop?
- Describe the behavior of the applications when specific failure scenarios occur (e.g., chart not found, image pull failure, resource quota exceeded).
- How does Helm Controller represent the status of HelmRelease objects during different failure states?

### Observing Application Behavior:

- What happens to pods when readiness probes fail? How does it affect the application deployment?
- Describe the behavior of pods when liveness probes fail continuously. What are the implications for application stability?
- How do network policies impact communication between pods? Can you provide an example from the workshop?

### Recovery Strategies and Best Practices:

- What are the common recovery strategies used to resolve HelmRelease failure scenarios?
- Explain the process of rolling back a failed Helm release to a stable state.
- How can misconfigured HelmRelease objects be corrected to ensure successful deployments?

### Reflecting on Best Practices:

- Based on the scenarios explored, what are some best practices for Helm chart development and HelmRelease configuration?
- How can these best practices be applied to real-world Kubernetes deployments to enhance resilience and recovery capabilities?

## Getting Started

Follow these steps to set up the workshop environment and start exploring Helm Controller failure scenarios:

1. **Clone this Repository**:

    ```bash
    git clone <repository-url>
    cd helm-controller-failure-workshop
    ```

2. **Prerequisites**:

    Ensure you have the following tools installed, it is recommended to use [**asdf**](https://asdf-vm.com/) to do this:

	1. [**Kind**](https://kind.sigs.k8s.io/):
	
	   ```bash
	   asdf plugin-add kind https://github.com/virtualstaticvoid/asdf-kind.git
	   asdf install kind
	   ```

	2. [**Helm**](https://helm.sh/docs/intro/install/):
	
	   ```bash
		asdf plugin-add helm https://github.com/Antiarchitect/asdf-helm.git
		asdf install helm
		helm plugin install https://github.com/databus23/helm-diff
	   ```

	3. [**Helmfile**](https://github.com/roboll/helmfile#installation):
	
	   ```bash
	   asdf plugin-add helmfile https://github.com/feniix/asdf-helmfile.git
		asdf install helmfile
	   ```

3. **Setting Up the Workshop**:

    Follow the instructions in the `setup/` directory to create a Kubernetes cluster using `kind`, install Helm Controller, and set up HelmRelease objects for various failure scenarios.

4. **Exploring Failure Scenarios**:

    Explore the HelmRelease definitions in the `scenarios/` directory to simulate different failure conditions. Use `kubectl` commands to apply these HelmRelease objects and observe the behavior of the deployed applications.

5. **Recovery Strategies**:

    Experiment with recovery strategies such as rolling back releases, updating misconfigured HelmRelease objects, and resolving dependencies to understand how Helm Controller can be recovered from failure states.

## Contributing

Contributions to enhance the workshop content, add new failure scenarios, or improve recovery methods are highly encouraged. Please submit issues and pull requests to collaborate and improve the learning experience for everyone.
