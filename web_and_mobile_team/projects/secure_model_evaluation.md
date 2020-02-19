## Introduction

_Last modified: February 19th, 2020_

Secure model evaluation is one of the primary use-cases of the OpenMined ecosystem. By allowing developers to query a remote dataset, they can evaluate the effectiveness of their models on data they literally "cannot see".

In this concept, a data supplier may allow a data scientist (internal to their organization, or external) to submit their model for private validation, all while tracking and permissioning their usage at a granular level. Doing such validation does not permit the data scientist to steal private, and often sensitive, information of the data owner. It is noteworthy that in this setting, we assume that the data owner is a trusted organization and that future extensions of this project will enable the use of encrypted computation for joint protection of the model and dataset during evaluation.

For this process to work correctly, the data owner will place their private data inside of a PyGrid "node", which is accessible via the PyGrid "gateway" that acts as a secure load balancer. Each node has dedicated compute resources with which to validate models on behalf of the data scientist. The data owner can create users with a variety of preset and custom roles, as well as designate each user's "epsilon budget" which is used to track how many `get()` requests that particular user has made. This ensures that no one user has complete access to the private dataset of the PyGrid node, nor can they make unlimited model validation requests.

Of course, it would be difficult to manage an entire network of user permissions, roles, and model validation requests through a command line or Python notebook. This creates the need for a small user interface to be developed to aide in the management of a private PyGrid network. We call this user interface the "PyGrid Admin" and it will serve as the secondary component of this project's roadmap. An administrator will be able to manage their entire network through this white-labeled user interface, which will be hosted as a standalone single-page application separate from the PyGrid API itself. Developing the PyGrid Admin as a standalone front-end application allows for the PyGrid network infrastructure to be scaled separate from the needs of running a user interface. Thus, the PyGrid Admin may be hosted on a variety of cloud-based file server platforms like AWS's S3, GCP's Cloud Storage, Microsoft's Azure Blob Storage, Netlify, or other such static asset hosting solutions.

One important administrative role of the PyGrid Admin is approving and denying data requests - we call this role the "data compliance officer". This individual is responsible for ensuring that the results of a model evaluation, which will be sent back to the data scientist, do not contain private information. The application will be responsible for empowering the data compliance officer with all of the information they need to make this decision, including: advanced analytics, differential privacy budgeting (tracked via an epsilon value), user request history, model and plan inspection, data request inspection, and other sources of information. Enforcement of these decisions will be performed by this individual within the PyGrid Admin, ensuring total control over their private data.

**Patrick Cason<br />**
_Web and Mobile Team Lead_

## Terminology

Let’s start off by defining a few terms that will be regularly used throughout this document:

- **Model** - a standard machine learning model
- **Plan** - a serialized list of operations that can be executed by a PyGrid Node
- **Model evaluation/validation** - the ability to supply test data (in this case, from a private dataset) to a pre-trained model for the purposes of testing and evaluating that model's prediction accuracy
- **Gateway** - a load balancer that serves as the primary public endpoint for a PyGrid network
- **Node** - a single server running within a PyGrid network, accessible via the PyGrid Gateway
- **Privacy budget** - the amount of validation requests a user can make on a given dataset
- **Epsilon value** - the name of the value for measuring a user's privacy budget

We will also use this section for defining each of the components of the OpenMined secure model evaluation system:

- **PyGrid** - a library consisting of multiple services that allows for "nodes" to be deployed and managed through a single "gateway". This is the main project where validation requests will be sent to and private data will be hosted.
- **PySyft** - a framework for privacy-preserving machine learning that is the primary library called internally by PyGrid
- **PyGrid Admin** - a user interface (UI) for managing a PyGrid network, allowing an administrator to manage user roles and permissions and model validation requests by those users

## Overview

XXX

## Projects

XXX
