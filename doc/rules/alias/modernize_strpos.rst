=========================
Rule ``modernize_strpos``
=========================

Replace ``strpos()`` calls with ``str_starts_with()`` or ``str_contains()`` if
possible.

Warning
-------

Using this rule is risky
~~~~~~~~~~~~~~~~~~~~~~~~

Risky if ``strpos``, ``str_starts_with`` or ``str_contains`` functions are
overridden.

Examples
--------

Example #1
~~~~~~~~~~

.. code-block:: diff

   --- Original
   +++ New
    <?php
   -if (strpos($haystack, $needle) === 0) {}
   -if (strpos($haystack, $needle) !== 0) {}
   -if (strpos($haystack, $needle) !== false) {}
   -if (strpos($haystack, $needle) === false) {}
   +if (str_starts_with($haystack, $needle)  ) {}
   +if (!str_starts_with($haystack, $needle)  ) {}
   +if (str_contains($haystack, $needle)  ) {}
   +if (!str_contains($haystack, $needle)  ) {}

Rule sets
---------

The rule is part of the following rule sets:

- `@PHP80Migration:risky <./../../ruleSets/PHP80MigrationRisky.rst>`_
- `@PHP82Migration:risky <./../../ruleSets/PHP82MigrationRisky.rst>`_
- `@Symfony:risky <./../../ruleSets/SymfonyRisky.rst>`_

References
----------

- Fixer class: `PhpCsFixer\\Fixer\\Alias\\ModernizeStrposFixer <./../../../src/Fixer/Alias/ModernizeStrposFixer.php>`_
- Test class: `PhpCsFixer\\Tests\\Fixer\\Alias\\ModernizeStrposFixerTest <./../../../tests/Fixer/Alias/ModernizeStrposFixerTest.php>`_

The test class defines officially supported behaviour. Each test case is a part of our backward compatibility promise.
