# How to create new interior
To create new floor select some folder in the **Project** window -> Right Mouse Click -> Create -> Domik -> Interior

**Furniture** - here you can define a set of furniture or some other placeable objects which can be in rooms with this interior.

**Skins** - a set of skins for rooms with this interior. These skins have higher priority than House Generator skins, so you can use them for define more specific cases like **room walls, floors, furniture look**, etc.

## Placing Rules
 this panel defines special rules for interior placing.

**Prefer Room** - which size of room better for this interior?
- Small - prefer small rooms
- Middle - prefer regular rooms
- Big - prefer big rooms
- Random - you don't care

### Parts Limit
Here you defines necessary and forbidden parts of the house.

lets add something:

mode: 
- Fixed - only this number of part is acceptable
- Range - only this range of part's count is acceptable
- At least one - there should be at least one instance of this part
- Unacceptable - rooms with this part will be ignored