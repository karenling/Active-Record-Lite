# w3d5 Active Record Lite

Implements basic Rails Active Record functionality. Active Record provides an interface to interact with data in relational databases.

**Phase 0: `my_attr_accessor`**

Uses metaprogramming to implement `attr_accessor` macro.

**Phase I: `SQLObject`**

Creates a `SQLObject` class to interact with the database.
Generates methods found in the real `ActiveRecord::Base`:
* `::all` returns an array of all records in the DB
* `::find` looks up a single record by primary key/id
* `#insert` inserts a new row into the table to represent the `SQLObject`
* `#update` updates the row with the `id` of the given `SQLObject`
* `#save` convenience method that calls either `insert` or `update` depending on whether or not the `SQLObject` already exists in the table (based on presence of `id`)

**PhaseII: `Searchable`**

Implements the ability to search using `::where`. Uses `extend` to allow us to mix in `Searchable` to our `SQLObject` class, adding all the module methods as class methods

**Phase III: `Associatable`**

Here we defined `belongs_to` and `has_many`. This uses an `Associatable` module that we mixin to `SQLObject`

**Phase IV: `has_one_through`**

Implements `has_one_through`, which combines two `belongs_to` associations.
