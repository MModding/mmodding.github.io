---
title: "Client-Side and Server-Side Classes with their Own Management"
layout: doc
---

# **Client-Side**

To create a Client Side Main Class with the MModding Library Base Content, you must create a class that implements `MModdingClientModInitializer`:

`MyMModdingClientMod.java`
```java
public class MyMModdingClientMod implements MModdingClientModInitializer {
    
    @Override
    public Config getConfig() {
        // We will keep this value as null for the moment
        return null;
    }
    
    @Override
    public List<ClientElementsInitializer> getClientElementsInitializers() {
        List<ClientElementsInitializer> clientElementsInitializers = new ArrayList<>();
        // ...
        return clientElementsIntializers;
    }
    
    @Override
    public void onInitializeClient(AdvancedModContainer mod) {
        mod.getLogger().log("Hello MModding Client World!");
    }
}
```

The `ClientElementsInitializer` creation is very likely the same as `ElementsInitializer`'s one, and it's up to you to use them to manage your Client Elements!

# **Server-Side**

To create a Server Side Main Class with the MModding Library Base Content, you must create a class that implements `MModdingServerModInitializer`:

```java
public class MyMModdingServerMod implements MModdingServerModInitializer {
    
    @Override
    public Config getConfig() {
        // We will keep this value as null for the moment
        return null;
    }
    
    @Override
    public List<ServerElementsInitializer> getServerElementsInitializers() {
        List<ServerElementsInitializer> serverElementsInitializers = new ArrayList<>();
        // ...
        return serverElementsInitializers;
    }
    
    @Override
    public void onInitializeClient(AdvancedModContainer mod) {
        mod.getLogger().log("Hello MModding Server World!");
    }
}
```

The `ServerElementsInitializer` creation is very likely the same as `ElementsInitializer`'s one, and it's up to you to use them to manage your Server Elements!
