# An Application Container Specification for Services

An Application Container Specification for requested and provisioned services.

* Version: 0.1
* Feedback: 
  * GitHub Issue,
  * GitHub Pull request, or 
  * Contact <andreas.solberg@uninett.no> or <gurvinder.singh@uninett.no>.



## General model

Each available service specifies:

* Service Identifier
* Depenedencies to other services
* A request specfication
* A provisioned service specfication

## Services

* [Host](services/host.md)
* [Certificates](services/cert.md)
* [L7 Loadbalancer](services/httpLB.md)
* [Dataporten](services/dataporten.md)
* [Dataporten API Gatekeeper](services/dataportenAPI.md)
* [Dataporten Authorization](services/dataportenAuthz.md)
* [SQL Storage](services/sql.md)


## Examples

* [Example applications](examples.md)
* [Example of using the app engine provisioning API](examples-api.md)
