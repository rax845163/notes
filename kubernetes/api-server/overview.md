# API Groups

At top level, distinguish between the core group (everything below /api/v1 not under /apis/core/v1) the named group (at path /apis/$NAME/$VERSION) and the system-wide entities (/metric).

Kind is the type of an entity. Each object has a field Kind which tells a client—such as kubectl or oc—that it represents.
Resource is the representation of a system entity sent or retrieved as JSON via HTTP; can be exposed as an individual resource (such as .../namespaces/default) or collections of resources (like .../jobs).