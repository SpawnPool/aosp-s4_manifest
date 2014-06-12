aosp-s4_manifest
================

Instructions
-------------------
Go to the root of the build directory then:
git clone https://github.com/SpawnPool/aosp-s4_manifest ./repo/local_manifests


Explanation
-------------------
This allows you to sync with multiple manifests by placing the manifests in a ".repo/local_manifests" directory.



Local Manifests
===============
Additional remotes and projects may be added through local manifest files stored in `$TOP_DIR/.repo/local_manifests/*.xml`.
 
For example:
$ ls .repo/local_manifests
  local_manifest.xml
  another_local_manifest.xml
$ cat .repo/local_manifests/local_manifest.xml 
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
   <project path="manifest" name="tools/manifest" />
   <project path="platform-manifest" name="platform/manifest" />
</manifest>
 
Users may add projects to the local manifest(s) prior to a `repo sync`invocation, instructing repo to automatically download and manage these extra projects.
Manifest files stored in `$TOP_DIR/.repo/local_manifests/*.xml` will be loaded in alphabetical order. Additional remotes and projects may also be added through a local
manifest, stored in `$TOP_DIR/.repo/local_manifest.xml`. This method is deprecated in favor of using multiple manifest files as mentioned above.
If `$TOP_DIR/.repo/local_manifest.xml` exists, it will be loaded before any manifest files stored in `$TOP_DIR/.repo/local_manifests/*.xml`.
