---
layout: docs
title: Invariants
---

# Invariants

This page lists invariants that can be maintained with Rich-CRDTs.

## Non nullity

An attribute of an entity cannot have a null value.

### Unique identifier

An identifier refers to a single element in a collection.

Uniqueness constraints can be maintained by ensuring disjoin identifier spaces between identifier generators and pseudo-random unique identifier generator.

## Unique sequence

An identifier refers to a single element in a collection and new identifiers are created following a sequence.

Provide a total order between elements that respects the generation order. Identifier generation requires coordination to ensure no gaps in the sequence.

## Prefixed unique sequence

An identifier refers to a single element in a collection and new identifiers are created following a prefixed sequence.

Provides a total order of elements generated from a single source without coordination. Relative ordering of identifiers generated in different sources is determined by the prefix.

## Monotonicity

A function is entirely increasing, or entirely non-decreasing.

In practice, this can be used to ensure that once a value of some variable is set it can’t go back to “smaller” value. For instance, once a flag is set true, no other operation might set it false, or vice versa.

## Numerical bounds

Numerical bounds express an inequality against a constant or another variable.

Each side of the inequality can be a single number, or an arithmetic expression. Numerical bounds are typically expressed through CHECK constraints.

## Referential Integrity

In a relationship where two entities are linked by a uni/bi-directional relation, the entity on the referenced side of the relation must exist.

Relational databases use relations: “belongs to”, “has one/many” and “ManyToMany” to associate entities in a schema.

## Phantom reads

Wikipedia defines Phantom reads as follows: "A _phantom read_ occurs when, in the course of a transaction, new rows are added or removed by another transaction to the records being read."

## Tree invariant (TODO)

...
