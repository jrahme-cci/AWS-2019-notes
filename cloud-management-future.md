# The future of cloud management

## Current Complexity

* overshooting budget

* accidentally exposing services

* workloads not optimized


There are a tonne of different service options, hard to manage and make sure you're using the right ones

managing accounts is painful

complexity of teams and their interactions

There tends to be a gap of new services coming out and how well we can apply those services

ml, databases, lambdas, and sooooo much else (ie the hackathon stack used)

omg the cloud native computing foundation K8 view of services and ecosystem components available is bafflingly large 

just look at their security options

* infra

* endpoint

* app 

* managed sec service provider 

* messaging

* web

* etc etc

So focus on who cares about the cloud

but each persona has a different concern about the cloud



things have matured over time in;

* visibility

* optimization

* governance & automation

* business integration

you want standards that can be broadly shared and then automated. The less you care about lower levels the more you can get shit done.

### cost and optimization

The flip side of usage, things cost $$ to run

we need visiblity into workloads (all private, publci and everything in between)

reduce the waste

distrbiute the responsibility of cost between centra It and finance as well as business needs

### Security
in the future we need application aware exposure and risk scoring

realtime event driven asset change controlmonitoring

dsl driven compliace as code language

compliance with security standards (HIPPA)

security operator, and automated remediation with quarantining for digital forensics

### provisiong and orchesttarion

we need to move to incontext views for apps, performance, network, and logs

rich library of serverless actions for cloud extensibility, 

and aggregated cloud dashboards

*so be able to plug into CI/Cd pipeline, and evaluate whats happening there*

### operations and analytics

we need to provide logs and analytic details about our pipeline execution so clients can futher optimize how their pipelines are running

these kind of anayltics could potentitally be used to train a ML model for clients to cost out the actual cost of their pipeline

give automated actions for clients to be able to do things like stop a pipeline if it's going to cause them to run over a cost, 

### service control

self service requests for native cloud service access

out of the box catalog for manage resource pools

additional template and cloud platform support (helm, terraform, etc etc)

### third party services

eco system is so complicated, 

a high level marketplace of SaaS services (like a package manager but for Saas?)

## What can we do about it

### Security

there is already standards in place for things like how we process credit cards

these standards should be a part of an existing catalog so that we can just plug and play those standards, or allow automated validation of conformation to them.

these standards need to be publicly available or we'll always be handing $$$$ over to contractors. 

A good platform will be able to provide the recomendations and best pactices we need

Audit process is harsh for cloud where the environment is ephemeral. You have to keep up with change, and the amount of changes makes it impossible
for it to be human drive.

### Cost

cloud usage isn't the same as it was when we were just buying datacentre hardware

the management system needs a way to annotize burst usage and when it's expected to calm down (new game vs 5 mo old game usage)

feeding costs into accounting software needs tobe a closed loop system like CI/CD

### Governance

single solution for single use cases (deploying, canarying these are particular pain points for us)

## All in All

The cloud is awesome, but hella complicated

More roles in the copmany continue to use the cloud and be interested in it's management

Cloud management needs to lessen the cognitive load of operating it

cloud success requires collaboration between actors coupled with automation
