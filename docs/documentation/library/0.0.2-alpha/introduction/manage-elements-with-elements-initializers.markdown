---
title: "Manage Elements with Elements Initializers"
layout: doc
---

The MModding Library provide the `ElementsInitializer` interface. This interface is used to initialize mod elements, and register them.

# **Create an Element Initializer**

`MyMModdingModBlocks.java`
```java
public class MyMModdingModBlocks implements ElementsInitializer {
    
    // Creation of a Simple Block
    public static final CustomBlock MMODDING_BLOCK = new CustomBlock(
        QuiltBlockSettings.of(Material.METAL)
    );

    @Override
    public void register() {
        // And we register it
        MMODDING_BLOCK.register(MyMModdingMod.createId("mmodding_block"));
    }
}
```

<div class="notification is-success is-dark">Tip: For more information about the <code>CustomBlock</code>, go to the Custom Elements Page</div>

# **Put an Elements Initializer in the Main Class**

`MyMModdingMod.java`
```java
public class MyMModdingMod implements MModdingModInitializer {

    // ...

    @Override
    public List<ElementsInitializer> getElementsInitializers() {
        List<ElementsInitializer> elementsInitializers = new ArrayList<>();
        // Add the Element Initializer in the List
        elementsInitializers.add(new MyMModdingModBlocks());
        return elementsInitializers;
    }

    // ...
}
```

By doing this, the `MModdingModInitializer` interface will directly run your `ElementsInitializer` objects before the execution of the `MModdingModInitializer#onInitialize` method.
