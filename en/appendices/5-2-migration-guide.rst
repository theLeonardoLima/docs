5.2 Migration Guide
###################

The 5.2.0 release is a backwards compatible with 5.0. It adds new functionality
and introduces new deprecations. Any functionality deprecated in 5.x will be
removed in 6.0.0.

Behavior Changes
================

- ``ValidationSet::add()`` will now raise errors when a rule is added with
  a name that is already defined. This change aims to prevent rules from being
  overwritten by accident.
- ``Http\Session`` will now raise an exception when an invalid session preset is
  used.
- ``FormProtectionComponent`` now raises ``Cake\Controller\Exception\FormProtectionException``. This
  class is a subclass of ``BadRequestException``, and offers the benefit of
  being filterable from logging.

New Features
============

Console
-------

- The ``cake counter_cache`` command was added. This command can be used to
  regenerate counters for models that use ``CounterCacheBehavior``.
- ``ConsoleIntegrationTestTrait::debugOutput()`` makes it easier to debug
  integration tests for console commands.

ORM
---

- ``CounterCacheBehavior::updateCounterCache()`` has been addded. This method
  allows you to update the counter cache values for all records of the configured
  associations.

Error
-----

- Custom exceptions can have specific error handling logic defined in
  ``ErrorController``.
