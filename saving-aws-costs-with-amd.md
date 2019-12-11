# Reducing cost w/ AMD instances

CMP3030 - m deep drive into nitro (see if seats available)

## dudes intro

Nitro system is what they use to power their EC2 provisioning

Nitro card- NVMe storage, propietary card, netowrking monitoring and security (unique to AWS built on box)

Nitro security chip - integrated on board, protects hardware resources (no hyper visor) 

Nitro Hypervisor: lightway hypervisor for memory and cpu allocation

Nitro components used for all archtiectures

AMD EPYC processors
Genearl purpose instances (m)
burstable instances (t)
memory optimized instances (r)

## Instance AMD vs Intel comparisons

m 
2.5 ghz cpu (intel is 3.1
2 - 96 cipus
storage is --
0.086/hr vs 0.096 /hr for intel, even switching free credit plans to use this would save decent $$$ (MMR)

t (burstable)
0.0047/hr vs 0.0052/hr
2.5 ghz vs 3.1
cpus and storage the same

r
0.126/hr vs 0.113 / hr
this slide was fucked 

C5 next gen epyc cpu (rome)
better compute performance
8 vcpu (c5a/c5ad) and 192vcpus with metal  100G netowrking and EFA(c5an.metal)


if we can manage lower cpu shares (1000 / vcpu???) than AMD is the way to go, like above this would be decent for free tier 

## Expedias Appearance

They have a specialty tool for optimization (cost and sizing)

*CostWatch* is the name of their tool

I don't think this particular tool will help much with our costs, but the amd instances are interseting.

rightsizing recomendation: also not applicable, we're letting customers choose that and the customer is paying for their size already, so meh

though it will automatically generate recommendations for the rest of our stuff which is certainly neat

it looks like it analyzes usage and then picks possible instances that would be a closer fit

### instance comparison

compare the current instance you're using with newer instances and get a cost difference

they made workloads more memory intensive instead of CPU so they could jump down to amd instances and not take a performance hit

going from r4.xl -> r5a xl saved ~75ka month

when all instances were on amd instances, they were wondering about cost saving of engineers vs savings of instances

## Cost watch demo

cost watch monitors all ec2 deployments and their resource usage, and offers smart decisions on where instances can be downgraded

they're gonna opensource costwatch

now this could actually be useful if we adapt it to see how much our clients are actually using on the various tiers

not open sourced yet

no date for it, but it's in the backlog to get it open sourced

it also considers IO savings whcih is nifty

it'll also say switch to a different instance type, and size if that will meet requirements and savings

I guess the magic sauce is the monitoring of current deploys

does usage estimation

the engine will never recommends over 70% cpu or 80% memory usages

just swithcing to a larger AMD instance of the same class can give 10%+ savings

I take back the earlier notes, this tool is actually pretty nifty, we coulda really used this at Cenx

The scanner they use to automate this is not going to be open sourced, which is a shame - that'd be super useful

Capacity limits from AWs may be an issue for the provisioning (but aren't they always)

!!there is a new api for instance availablity by zone!! that could be benificial for our circuit breaking

## Note

There were slide pics to go with this, but they disspeared when my phone gave up on life later this day
