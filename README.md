# ActiveRecordLite
ActiveRecordLite is an object-relational mapping system inspired by
ActiveRecord. Uses Ruby's metaprogramming capabilities to implement its
core functionality.

## Current Features
- `SQLObject::find(id)` returns a SQLObject with attributes matching the database row having the corresponding id
- `SQLObject#insert` creates new row in the database with the SQLObject's attributes and assigns an id
- `SQLObject#update` maps current attribute values over previous column values in the database on the row with the corresponding id
- `SQLObject#save` inserts or updates SQLObject based on `id.nil?`
- `SQLObject#where(params)` forms and executes SQL query based on params; returns an array of SQLObjects
- `SQLObject#belongs_to(name, options)` defines a method, `name`, that returns a SQLObject whose `#model_name` and `:primary_key` value correspond to the `:class_name` option and `:foreign_key` value of the association
- `SQLObject#has_many(name, options)` is the inverse of `#belongs_to`; defines a method, `name` that returns an array of SQLObjects with appropriate `#model_name`s and `:primary_key` values
- `SQLObject#has_one_through(name, through_name, source_name)` defines a relationship between two SQLObjects through two `#belongs_to` relationships. Defines a method, `name`, that returns a SQLObject whose `#model_name` corresponds to the `source_name`

## Using ActiveRecordLite
- Add this repo to your project
- Require `'active_record_lite'`
