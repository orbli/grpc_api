# api

The grpc definitions that are used across the projects

### golang

Put the following into `glide.yaml`

```
- package: github.com/orbli/grpc_api
  version: 0.2.3
  repo: https://github.com/orbli/grpc_api.git
```

Change the version yourself. Then it will be downloaded into `/vendor`. An example code usage is

```
import "github.com/orbli/golang/authentik/authority/v1"
```

### python

Put the following into vagga when building container:

```
containers:
  python:
    setup:
      - !Py3Install
        - git+https://github.com/orbli/grpc_api.git@v0.2.3#egg=api&subdirectory=python
```

Change the version and other respective configurations yourself. Then it will be downloaded to some system managed library in that container. An example code usage is

```
from authentik.authority.v1 import identification_registry_pb2 as rpc_message
```

### dart

Put the following into `pubspec.yaml`:

```
dependencies:
  grpc_api:
    git:
      url: https://github.com/orbli/grpc_api.git
      ref: v0.2.3
      path: dart/
```

Change the ref to any version tag or branch yourself. Then it will be downloaded according to your flutter configuration (probably something like `.pub-cache`). Example usage:

```
import 'package:grpc_api/test/helloworld_service.pb.dart';
```

### typescript

Put the following into `package.json`:

```
"dependencies": {
  "grpc_api": "git+https://github.com/orbli/grpc_api.git#semver:v0.3.0"
}
```

You can also use command `npm install <URI above>`

Change the version to any version tag or branch yourself. Then it will be downloaded to `node_modules`. Example usage:

```
import { TestServiceClient } from 'grpc_api/js/test/helloworld_pb_service'
import * as irs from 'grpc_api/js/test/helloworld_pb'
```

