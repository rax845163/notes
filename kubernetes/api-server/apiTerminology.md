## Kind

The type of an entity. Each object has a field Kind (lowercase kind in JSON, capitalized Kind in Golang), which tells a client such as kubectl that it represents, for example, a pod. There are three categories of kinds:
* Objects represent a persistent entity in the system—for example, Pod or Endpoints. Objects have names, and many of them live in namespaces.

* Lists are collections of one or more kinds of entities. Lists have a limited set of common metadata. Examples include PodLists or NodeLists. When you do a kubectl get pods, that’s exactly what you get.

* Special-purpose kinds are used for specific actions on objects and for nonpersistent entities such as /binding or /scale. For discovery, Kubernetes uses APIGroup and APIResource; for error results, it uses Status.

## Resource
A usually lowercase, plural word (e.g., pods) identifying a set of HTTP endpoints (paths) exposing the CRUD (create, read, update, delete) semantics of a certain object type in the system. Common paths are:

## Tips
Resources and kinds are often mixed up. Note the clear distinction:

* Resources correspond to HTTP paths.
* Kinds are the types of objects returned by and received by these endpoints, as well as persisted into etcd.