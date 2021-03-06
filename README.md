# blobstore-cli

blobstore-cli provides command-line access to the blobstore abstraction in
[Apache jclouds](https://jclouds.apache.org/), the multi-cloud toolkit.
blobstore-cli reimplements parts of
[jclouds-cli](https://github.com/apache/karaf-jclouds-cli)
using a lighter-weight framework, reducing both binary size and startup time.

## Usage

Users can [download releases](https://github.com/gaul/blobstore-cli/releases)
from GitHub.  Developers can build the project by running `mvn package` which
produces a binary at `target/blobstore`.  blobstore-cli requires Java 7 to
run.

blobstore-cli packages as an executable jar.  Users must provide a properties
files which includes the credentials and endpoint:

```
jclouds.provider=aws-s3
jclouds.identity=xxxxxxxxxxxxxxxxxxxx
jclouds.credential=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

Next run `blobstore`.  Linux and Mac OS X users can run the executable jar:

```
chmod +x blobstore
blobstore
```

Windows users must explicitly invoke java:

```
java -jar blobstore
```

Then invoke via:

```
blobstore --properties properties.conf container create MYCONTAINER
```

## Supported providers

* atmos
* aws-s3 (Amazon-only)
* azureblob
* b2
* google-cloud-storage
* openstack-swift
* rackspace-cloudfiles-uk and rackspace-cloudfiles-us
* s3 (all implementations)

To access private cloud s3 and swift, provide `jclouds.endpoint` in the
properties.

## References

* [jclouds-cli](https://github.com/apache/karaf-jclouds-cli)
* [libcloud-cli](https://github.com/coyo8/libcloud-cli)
* [pkgcloud-cli](https://github.com/pkgcloud/pkgcloud-cli)

## License

Copyright (C) 2017 Andrew Gaul

Licensed under the Apache License, Version 2.0
