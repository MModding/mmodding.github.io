---
title: "Create the Main Class"
layout: doc
---

Create a new class in your mod package that implements `MModdingModInitializer`:

`MModdingExempleMod.java`
```java
public class MModdingExempleMod implements MModdingModInitializer {

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
        MModdingExempleMod.mod = MModdingModContainer.from(mod);
        
        // Your amazing code here
    }
}
```

<div class="notification is-warning is-dark">Warning: You must replace <code>MModdingExempleMod</code> by your mod's name!</div>
