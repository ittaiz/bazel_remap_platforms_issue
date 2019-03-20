# bazel_remap_platforms_issue
Reproduction repository for issue of remap_main_repo flag with execution platforms 

Error:  
```
➜  bazel_remap_platforms_issue git:(master) bazel build //...                 
INFO: Invocation ID: b8f78378-5b97-42bc-a982-ae9aa9c23824
ERROR: While resolving toolchains for target //code:foo: Unable to find an execution platform for target platform @bazel_tools//platforms:target_platform from available execution platforms []
ERROR: Analysis of target '//code:foo' failed; build aborted: Unable to find an execution platform for target platform @bazel_tools//platforms:target_platform from available execution platforms []
INFO: Elapsed time: 0.188s
INFO: 0 processes.
FAILED: Build did NOT complete successfully (1 packages loaded, 3 targets configured)
``` 

You can also check the `remap_off_passes` and `no_qualify_in_ws_passes` branches which show the build passes when remap is off or when you don't qualify the execution platform in the WORKSPACE.