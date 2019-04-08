# Domain Events
>Something happened that domain experts care about. 

A domain event is a full-fledged part of the domain model, 
a representation of something that happened in the domain.

### Individuating events:
Consider a few key phrases to listen for when domain experts talk:
* "When..."
* "If that happens..."
* "Inform me if..." and "Notify me if..."
* "An occurrence of..."

**Use domain events to explicitly implement side effects of changes within your domain,
namely across multiple aggregates**.
