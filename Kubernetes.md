# Kubernetes

## Deployment vs StatefulSet

**Deployments** are used for *stateless* Applications like REST APIs or Microservices.

**StatefulSets** are useful for *stateful* installations like Databases, Elasticsearch, Redis, ...

Key Differences:

1. **Pods** deployed by deployments are identical and interchangeable, created
   in random order with random hashes in their names.  Pods deployed by
   StatefulSets are not identical, keen their identity between restarts and can
   be addressed individually.  So they cannot be created or deleted at the same
   time.
2. StatefulSets don't create **ReplicaSets** but rather create the Pods
   themselves with unique naming convention. They manage the deployment and
   scaling of Pods and guarantee ordering and uniqueness of these Pods.
3. Every Replica of a StatefulSet will create their own PVC (Persistent Volume
   Claim)
