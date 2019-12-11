# Deep dive into 100G networking & elastic Fabric Adpater on Amazon EC2

## Agneda

* Networking overview

* 100g use cases

* nitro architecture

* elastic fabric adapter on ec2

* HPC use cases

## Networking Overview

nitro gives 20x increase in pps peroformance

reduces instance to instance latencies

enables 100gbps of bandwidth performance


### instances w/ 100g networking

* C5n instances
* m5n
* r5n
* P2dn -- ml optimized 
* G4dn -- most powerful accelerated compute
* i3en - io intensive instance
* INF1  ml inference uses tensor core GPUs
* C5AN (they forgot to mention this one in the slides) (D and N variants) - AMD based (hawt)

if the instance has a n it has this networking capability

## Use cases

Data dog uses for i3n for a lot of their worloads

100 gbps is only withing the VPC or peered vpc

S3 is only 100gbps in the same region

placement group - 10 gbps flow limit. Aggregate across whole group you can do 100g

everything else 5gbps

## Nitro Overview 

zoom zoom, hardware fast, zoom zoom (I have other notes look at those)

in short, off loaded the hypervisor onto a PCI card and off the mobo saving resources for the virtualized stuff

## Fabric

EFA allowed for single route virtualization, so a virtaul peice of hardare is visibile at the PCI level (libfabric)

lib fabric allows to bypass the CPU and Kernel for network ops to make things super zippy

just pushes packets directly onto the wire, no drivers, no kernels, just pure unadulterated speed


### SRD (Scalable reliable datagram)

inspired by infiniband

equal-cost multi-path routing is a routing strategy where next hop packet forwarding to a single destination can occur over multiple "best paths. This can substantitally increase bandwidth by load balancing traffic over multiple paths

see pic for tcp vs inifiniband vs SRD

packets get lost, and that's okay - cosmic rays sometimes snipe a packet (friggen Galacticus)

link failure is considered to be the same thing as a packet drop

But with infiniband you eat a microsecond instead of milliseconds with TCP


