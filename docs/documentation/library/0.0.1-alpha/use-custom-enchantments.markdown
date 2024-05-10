---
layout: doc
title: "Use Custom Enchantments"
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

<div class="notification is-success">Tip: `EnchantmentType.DEFAULT` represents a normal enchantment.</div>
<div class="notification is-success">Tip: Enchantment Rarity can be: `COMMON` `UNCOMMON` `RARE` `VERY_RARE`.</div>
<div class="notification is-success">Tip: Enchantment Target can be: `ARMOR` `ARMOR_FEET` `ARMOR_LEGS` `ARMOR_CHEST` `ARMOR_HEAD` `WEAPON` `DIGGER` `FISHING_ROD` `TRIDENT` `BREAKABLE` `BOW` `WEARABLE` `CROSSBOW` `VANISHABLE`.</div>
<div class="notification is-success">Tip: Equipment Slot can be: `MAINHAND` `OFFHAND` `FEET` `LEGS` `CHEST` `HEAD`.</div>
