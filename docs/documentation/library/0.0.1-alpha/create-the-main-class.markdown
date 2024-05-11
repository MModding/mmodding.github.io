---
title: "Create the Main Class"
layout: doc
---

Create a new class in your mod package that implements `MModdingModInitializer`:

`MModdingExampleMod.java`
```java
public class MModdingExampleMod implements MModdingModInitializer {

    public static MModdingModContainer mod;
    
    @Override
    public List<ElementsInitializer> getElementsInitializers() {
        List<ElementsInitializer> elementsInitializers = new ArrayList<>();
        // Check the "Use ElementsInitializer" page
        return elementsInitializers;
    }
    
    @Override
    public void onInitialize(ModContainer mod) {
        MModdingModInitializer.super.onInitialize();
        MModdingExampleMod.mod = MModdingModContainer.from(mod);
        
        // Your amazing code here
    }
}
```

<div class="notification is-warning is-dark">Warning: You must replace <code>MModdingExampleMod</code> by your mod's name!</div>
