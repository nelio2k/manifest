# What is here?

These are manifests describing the source code which goes into building
many Couchbase products. They are intended to be read using the
[https://gerrit.googlesource.com/git-repo/+/refs/heads/master/README.md](repo tool).

Each product (or family of products) has a top-level directory, containing
manifests and subdirectories based on the various releases of those products.

When we make a release, we take the manifest emitted from the builder
and store it in the released/ directory.  This manifest only has exact
commit SHAs, so that it explicitly describes which revision was used,
in both Couchbase and external repositories.

# Which Manifest Do I Use?

## Couchbase Server

If you want to build the most recent development branch you should use
"branch-master.xml" from the top-level directory (located there primarily
for historical reasons).

Each Server release is given a code name (eg. mad-hatter, spock, etc).
During development prior to a release, the manifest to use will be
couchbase-server/RELEASE.xml, eg. couchbase-server/mad-hatter.xml.

After GA of a given release, the "main" manifest will become the manifest
for the next point release of that release. Eg. once Mad-Hatter is GA
(as 6.5.0), couchbase-server/mad-hatter.xml will start being the manifest
for the upcoming 6.5.1 point release.

Also at GA, a new manifest couchbase-server/RELEASE/VERSION.xml will be
made based on the GA version number (couchbase-server/mad-hatter/6.5.0.xml
in the example above). This will be used for maintenance packs, urgent
releases, etc, but generally will have very few changes.

## Other products

Other products have similar life-cycles to the above, although many
products do not adopt the "code name" methodology and instead simply use
the version number for the release name. Some products use slight
variations on the above.

## Couchbase Experimental Builds

The toy/ directory is used by Couchbase developers for experimental builds,
and so are probably not of interest to anyone not familiar with the context
of the experiment.
