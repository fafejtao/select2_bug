# Select2 differences

Project demonstrates behavior differences between select2 version 3.5.3 and version 4.0.x.

- test_353.html using version 3.5.3
- test.html using version 4.0.12

Version 3.5.3 works correctly.

### Bugs in select2 version 4.0.x
Bugs occur only in case select is multiple and using option groups (optgroup)

1. selected options are still visible in autocomplete
    - Steps to reproduce:
    1. type Alaska
    2. press enter to select Alaska
    3. type Alaska again - expected: option is not visible, actual: option is still visible
2. removing selected option opens autocomplete
    - Steps to reproduce:
    1. type Alaska
    2. press enter to select Alaska
    3. click to 'x' to remove Alaska - expected: option is removed, actual: option is removed and autocomplete is shown
3. mouse click and keyboard enter behave differently
    - Steps to reproduce:
    1. type Alaska
    2. press enter to select Alaska
    3. type Alaska again (due to bug#1 this option is still available)
    4. press enter (nothing happens)
    5. type Alaska again (due to bug#1 this option is still available)
    6. click mouse to select Alaska - expected: should't be available, actual: removes option from selected options