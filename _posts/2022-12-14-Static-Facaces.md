---
layout: post
title:  "Static Facades"
category: pattern
tags: ["Pattern", "Facade", "Static", "Ada", "`package`", "`renames`"]
version: 0.0.1-wip
---

This is supposed to be a blog about how to make a static facade to a
package called *Bike_Repair_Shop*.

```Ada
package Bike_Repair_Shop
is
   function Is_Open return Boolean;
   procedure Pay_Bill;

   function Is_Coffemaker_On return Boolean;
   procedure Some_Internal_Procedure;

end Bike_Repair_Shop;
```

This is intended use:

```Ada
-- Context
with Bike_Repair_Shop;
...
-- Declaration
package Shop
  renams Bike_Repair_Shop;
-- Abstract away that we are delaing with a bike repair shop.
...
-- Body
if Shop.Is_Open then
   Shop.Pay_Bill;
end if;
```

Now we want to create a facade to the shop;

The transparent facade
----

```Ada
with Bike_Repair_Shop_Facade;
...
package Bike_Repair_Shop
  renames Bike_Repair_Shop_Facade;
--  Transparent facade

package Shop
  renames Bike_Repair_Shop;
-- Abstract Shop
```

Hiding the roughness
----
We replace the renaming;
```Ada

package Bike_Repair_Shop_Facade
is
   function Is_Open return Boolean
      renames Bike_Repair_Shop.Is_Open;
   procedure Pay_Bill
      renames Bike_Repair_Shop.Pay_Bill;
end Bike_Repair_Shop_Facade;
```


