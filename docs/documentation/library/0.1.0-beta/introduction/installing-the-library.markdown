---
title: "Installing the Library"
layout: doc
---

## **Let's use Gradle!**

To install and use the MModding Library within your mod, you will need to add the following to your `gradle/libs.versions.toml` file:

```toml
[versions]
# ...
# under the quilted_fabric_api
mmodding = "VERSION"

[libraries]
# ...
# under the quilted_fabric_api
mmodding = { module = "com.mmodding:mmodding-library", version.ref = "mmodding" }
```

<div class="notification is-success is-dark">Tip: check the release tags on GitHub to see what to replace <code>VERSION</code> with.</div>

Then go to your `build.gradle` file:

```groovy
repositories {
    // ...
    maven { url 'https://jitpack.io' }
    maven { url 'https://maven.terraformersmc.com' }
}

dependencies {
    // ...
    
    // MModding Library
    modImplementation libs.mmodding
}
```

<div class="notification is-warning is-dark">Warning: Do not put this in your buildscript section!</div>
