---
title: "Enchantment Type"
layout: doc
---

## Several features may not work properly.

You can create your own EnchantmentType by this way:

`EnchantmentTypes.java`
```java
public class Enchantments implements ElementsInitializer {
    
    public static EnchantmentType type = EnchantmentType.createWithCustomBook(
        // The Name of the EntityType
        "mmodding_enchantment_type",
        // The Prefix Before the Book Item Name for All The Enchanted Books with this EnchantmentType
        Text.of("§4 MModding Enchantment Type"),
        // Can the Enchantments with this EnchantmentType be in the Enchanting Table
        false,
        // The Identifier for the CustomBookItem
        new Identifier("mmodding_exemple_mod", "mmodding_enchantment_book"),
        // Item Settings for the CustomBookItem
        new CustomItemSettings.glint()
    );
    
    public void register() {}
}
```
