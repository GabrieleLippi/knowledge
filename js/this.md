To understand this binding, we have to understand call-site; the only thing that matters for the value the this binding will have, is the actual call-site.
We can use 4 rules:
  * Default Binding => global object, except if we are in "strict mode"
  * Implicit Binding => check if the call-site have a context object
  * Implictly Lost => fallback to the default binding against our expectation
  * Explicit Binding => call, apply and bind land!
