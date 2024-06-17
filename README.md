* Run `pants export-codegen src/protos:`
* This should produce the following error:
  ```
    ProcessExecutionFailure: Process 'Generating Go sources from src/protos/test.proto@parametrize=py310.' failed with exit code 1.
    stdout:

    stderr:
    protos/testtwo.proto: File not found.
    protos/test.proto:6:1: Import "protos/testtwo.proto" was not found or had errors.
    protos/test.proto:9:5: "MyType" is not defined.
  ```
* If update the build file and remove the parametrize so it looks like this:
  ```
    protobuf_sources()
  ```
  It builds successfully