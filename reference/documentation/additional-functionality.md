# Additional functionality

The library comes with a few useful helper classes and interfaces you can use to further reduce boilerplate code.&#x20;

#### Trackable

When inheriting from trackable your class is automatically extended by tracking "Created" and "Updated" and is automatically tracking last change date, this gets extended with LastUpdatedBy soon.&#x20;

#### SoftDeletable

Items are not deleted but just marked with "IsDeleted" in the database and are no longer returned via GET calls





