# Turn.io Platform Coding Challenge

Welcome to our platform coding challenge!

## What you will build

Turn is built in Elixir and is hosted on Kubernetes clusters.

For this challenge you will provision a managed autoscaling Kubernetes cluster running a minimal Phoenlix LiveView based Web Application.

## High level app functionality

We'd like to see a minimal Phoenlix LiveView application that is hosted on a Kubernetes cluster.

The application should be publicly accessible via a loadbalancer routing traffic to one or multiple Kubernetes Pods running the Phoenlix LiveView application.

The app should be able to induce sustained CPU load on a Kubernetes node a specific Pod is being hosted on.

Additional Kubernetes Nodes and Pods should be automatically created when sustained CPU load is observed (horizontal pod autoscaling). The app should also be able to halt previously induced sustained CPU load, at which time additionally automatically created Kubernetes Nodes and Pods should be removed (horizontal pod autoscaling).

The loadbalancer should not route traffic to Pods being created as part of autoscaling events until they are ready to process requests. Running requests should be allowed to complete prior to Pods being removed as part of autoscaling events.

## Technical requirements

1. Terraform manifests should be created provisioning a managed Google Kubernetes Engine (GKE) Kubernetes cluster on Google Cloud Platform.
2. The Phoenix LiveView application should be packaged as a container image that can be deployed into this Kubernetes cluster.
3. Kubernetes manifests should be created allowing for deploying the above described Phoenlix LiveView application into the GKE Kubernetes cluster.
4. Kubernetes manifests should be created exposing the deployed Phoenlix LiveView application on the public internet.

## Important: keep it minimal!

Please remember to keep it minimal and not spend too much time on the challenge.

The Phoenix Live View application does not need to be pretty. It should really just render a 'increase load' and 'decrease load' button that will induce Kubernetes autoscaling events.

General security concerns like HTTPS and authentication is not important for this challenge.

Automating everything end-to-end via CI/CD build pipelines is not required.

Detailed tests are not required.

## Submission

Create a private Git repository on the platform of your choice and add shaun@turn.io as a member. Once you are happy with your submission notify shaun@turn.io for review.

Your submission should include brief documentation detailing:
- How to execute the Terraform (e.g. set GCP credentials in `<insert file name here>` and run `terraform plan` ...)
- How to roll out the the Kubernetes manifests (e.g. `kubectl apply ...`)

## Need help?

Please contact us by email at shaun@turn.io in case of questions.
