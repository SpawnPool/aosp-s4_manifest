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



More options
--------------
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
<remove-project name="platform/external/jpeg" />
 <remove-project name="platform/bionic" />
 <remove-project name="platform/dalvik" />
 <!-- add linaro git repository as a remote source -->
 <remote name="linaro" fetch="git://android.git.linaro.org/" review="review.android.git.linaro.org" />
 <remote name="linaro-other" fetch="git://git.linaro.org/" />
 <project path="external/jpeg" name="people/tomgall/libjpeg-turbo/libjpeg-turbo" revision="android" remote="linaro-other" />
 <project path="bionic" name="platform/bionic" revision="linaro_android_4.2.1" remote="linaro"/>
 <project path="dalvik" name="platform/dalvik" revision="linaro_android_4.2.1" remote="linaro" />
</manifest>
