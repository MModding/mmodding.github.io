---
title: "Create the Main Class"
layout: doc
---

Create a new class in your mod package that implements `MModdingModInitializer`:

`MyMModdingMod.java`
```java
public class MyMModdingMod implements MModdingModInitializer {
    
    @Override
    public Config getConfig() {
        // We will keep this value as null for the moment
        return null;
    }
    
    @Override
    public List<ElementsInitializer> getElementsInitializers() {
        List<ElementsInitializer> elementsInitializers = new ArrayList<>();
        // Check the "Use ElementsInitializer" page
        return elementsInitializers;
    }
    
    @Override
    public void onInitialize(AdvancedModContainer mod) {
        mod.getLogger().log("Hello MModding World!");
    }

    public static String id() {
        return "yourmodid";
    }

    public static Identifier createId(String path) {
        return new Identifier(MyMModdingMod.id(), path);
    }
}
```

<div class="notification is-warning is-dark">Warning: You must replace <code>MyMModdingMod</code> by your mod name in CamelCase (following Java Naming Conventions) and <code>yourmodid</code> by your mod identifier.</div>
