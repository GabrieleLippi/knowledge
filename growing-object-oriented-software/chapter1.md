# What is the point of test-driven development?

Almost all software projects are attempting something that nobody has done
before (or at least that nobody in the organization has done before).

Developers often don’t completely understand the technologies they’re using.
They have to learn how the components work whilst completing the project.

Everyone involved in a software project has to learn as it progresses.

**For the
project to succeed, the people involved have to work together just to understand
what they’re supposed to achieve, and to identify and resolve misunderstandings
along the way. They all know there will be changes, they just don’t know what
changes. They need a process that will help them cope with uncertainty as their
experience grows—to anticipate unanticipated changes.**

## feedback is the fundamental tool

We think that the best approach a team can take is to use empirical feedback to
learn about the system and its use, and then apply that learning back to the system.

we apply feedback cycles at every level of development, organizing
projects as a system of nested loops ranging from seconds to months, such as:
pair programming, unit tests, acceptance tests, daily meetings, iterations, releases,
and so on.

In a project organized as a set of nested feedback loops, development is
incremental and iterative.

**Incremental development builds a system feature by feature, instead of building
all the layers and components and integrating them at the end. Each feature is
implemented as an end-to-end “slice” through all the relevant parts of the system.
The system is always integrated and ready for deployment.**

**Iterative development progressively refines the implementation of features in
response to feedback until they are good enough.**

## practices that support change

iif we want to grow a system
reliably and to cope with the unanticipated changes that always happen, we need constant testing to catch regression errors, so we can add new features
without breaking existing ones
For systems of any interesting size, frequent
manual testing is just impractical, so we must automate testing as much as we
can to reduce the costs of building, deploying, and modifying versions of the
system

Second, we need to keep the code as simple as possible, so it’s easier to under-
stand and modify. Developers spend far more time reading code than writing it,
so that’s what we should optimize for. 1 Simplicity takes effort, so we constantly
refactor [Fowler99] our code as we work with it—to improve and simplify its
design, to remove duplication, and to ensure that it clearly expresses what it does.


## test-driven development in a nutshell

The cycle at the heart of TDD is: write a test; write some code to get it working;
refactor the code to be as simple an implementation of the tested features as
possible. Repeat.

As we develop the system, we use TDD to give us feedback on the quality of
both its implementation (“Does it work?”) and design (“Is it well structured?”).

Refactoring means changing the internal structure of an existing body of code
without changing its behavior. The point is to improve the code so that it’s a better
representation of the features it implements, making it more maintainable.

When we’re implementing a feature, we start by writing an acceptance test,
which exercises the functionality we want to build.

## testing end-to-end

For us, “end-to-end” means more than just interacting with the system from
the outside—that might be better called “edge-to-edge” testing. We prefer to
have the end-to-end tests exercise both the system and the process by which it’s
built and deployed.

## levels of testing

**Acceptance**: Does the whole system work?
**Integration**: Does our code work against code we can't change?
**Unit**: Do our objects do the right thing, are they convenient to work with?
