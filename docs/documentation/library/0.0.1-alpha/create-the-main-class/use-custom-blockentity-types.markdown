---
title: "Use Custom BlockEntity Types"
layout: doc
---

With the `CustomBlockEntityType` class provided by the MModding Library, registering a new BlockEntityType is more simple.

## **Create your BlockEntity class**

`MModdingBlockEntity.java`
```java
public class MModdingBlockEntity extends BlockEntity {
    
    public MModdingBlockEntity(BlockPos pos, BlockState state) {
        super(NOTHING, pos, state);
    }
}
```

<div class="notification is-warning is-dark">Warning: "NOTHING" is not permanent, we will replace it later.</div>

## **Create and register your BlockEntityType**

In your BlockEntityTypes class:

`BlockEntityTypes.class`
```java
public class BlockEntityTypes {
    public static final CustomBlockEntityType<TestBlockEntity> TEST = new CustomBlockEntityType<>(MModdingBlockEntity::new, BLOCK)
	.createAndRegister(new Identifier("mmodding_exemple_mod", "testBlockEntityType"));
}
```

<div class="notification is-success is-dark">Tip: Replace "BLOCK" by the instance of the block that uses the BlockEntity.</div>

**Update your BlockEntity class**

Replace "NOTHING" by your BlockEntityType:

`MModdingBlockEntity.java`
```java
public class MModdingBlockEntity extends BlockEntity {
    
    public MModdingBlockEntity(BlockPos pos, BlockState state) {
        super(BlockEntityTypes.TEST.getBlockEntityTypeIfCreated(), pos, state);
    }
}
```
