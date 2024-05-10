---
title: "Use Element Initializers"
layout: doc
---

## **Create an Element Initializer**

`MModdingModBlocks.java`
```java
public class MModdingModBlocks implements ElementsInitializer {
    
    // Init a block
    public static final CustomBlock MMODDING_BLOCK = new CustomBlock(
        QuiltBlockSettings.of(Material.METAL)
    )
    
    @Override
    public void register() {
        // And register it
        MMODDING_BLOCK.register(
            new Identifier("mmodding_exemple_mod", "mmodding_block")
        );
    }
}
```

<div class="notification is-success is-dark">Tip: For more information about the <code>CustomBlock</code>, go to the <code>CustomBlock</code> Page</div>

# **Register an Elements Initializer**

`MModdingExampleMod.java`
```java
public class MModdingExempleMod implements MModdingModInitializer {

    // ...

    @Override
    public List<ElementsInitializer> getElementsInitializers() {
        List<ElementsInitializer> elementsInitializers = new ArrayList<>();
        // Add the Element Initializer in the List
        elementsInitializers.add(new MModdingModBlocks());
        return elementsInitializers;
    }
    
    // ...
}
```

By doing this, you won't need to call `MModdingExempleMod#register`.
