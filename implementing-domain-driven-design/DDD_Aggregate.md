# Aggregate and Aggregate Root
>A DDD aggregate is a cluster of domain objects that can be treated as a single unit

An aggregate will have one of its component objects be the aggregate root.

### Example: an order and its items
An example may be an order and its line-items; even though these will be separate objects, it's useful to treat the order (together with its line items) as a single aggregate.
