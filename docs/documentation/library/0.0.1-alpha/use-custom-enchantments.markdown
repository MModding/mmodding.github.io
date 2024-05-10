---
title: "Use Custom Enchantments"
layout: doc
---

Use `CustomEnchantment` allow you to set a EnchantmentType for your Enchantment. You can also easly register your Enchantment with `CustomEnchantment#register`.

`Enchantments.java`
```java
public class Enchantments implements ElementsInitializer {
    
    public static CustomEnchantment enchantment = new CustomEnchantment(
        EnchantmentType.DEFAULT, // The Enchantment Type
        Enchantment.Rarity.COMMON, // The Enchantment Rarity
        EnchantmentTarget.BREAKABLE, // The Enchantment Target
        EquipmentSlot.MAINHAND // The Equipment Slot
    );
    
    public void register() {
        enchantment.register(new Identifier("mmodding_exemple_mod", "mmodding_enchantment"));
    }
}
```

<div class="notification is-success is-dark">Tip: <code>EnchantmentType.DEFAULT</code> represents a normal enchantment.</div>
<div class="notification is-success is-dark">Tip: Enchantment Rarity can be: <code>COMMON</code> <code>UNCOMMON</code> <code>RARE</code> <code>VERY_RARE</code>.</div>
<div class="notification is-success is-dark">Tip: Enchantment Target can be: <code>ARMOR</code> <code>ARMOR_FEET</code> <code>ARMOR_LEGS</code> <code>ARMOR_CHEST</code> <code>ARMOR_HEAD</code> <code>WEAPON</code> <code>DIGGER</code> <code>FISHING_ROD</code> <code>TRIDENT</code> <code>BREAKABLE</code> <code>BOW</code> <code>WEARABLE</code> <code>CROSSBOW</code> <code>VANISHABLE</code>.</div>
<div class="notification is-success is-dark">Tip: Equipment Slot can be: <code>MAINHAND</code> <code>OFFHAND</code> <code>FEET</code> <code>LEGS</code> <code>CHEST</code> <code>HEAD</code>.</div>
