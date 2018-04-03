Changelog
*********

1.3.3 (unreleased)
==================

- Small documentation improvements

- Now ``test_XXX.json`` files are automatically collected and executed

- You can run a test scenario using the pytest CLI ``pytest test_YYY.json``

- Introduced json test scenario ini file with markers definition. For a given
  ``test_YYY.json`` scenario you can add a ``test_YYY.ini`` ini file::

    [pytest]
    markers =
        marker1
        marker2

  and filter scenarios using marker expressions ``pytest -m marker1``

- Enabled parametrization of arguments for a plain json scenario in scenario ini file::

    [pytest]
    test_data =
       {"username": "foo"}
       {"username": "bar"}

  and your json scenario will be executed twice


1.3.2 (2018-02-05)
==================

- Add ``sorted`` in python expressions


1.3.1 (2018-01-31)
==================

- Add more tests

- Documentation update

- play_json fixture no more assumes that you
  have some pytest-variables settings.
  No more mandatory

- fix include scenario bug that occurs only
  on Windows (slash vs backslash and
  JSON decoding issues)


1.3.0 (2018-01-22)
==================

- documentation improvements

- supports teardown callbacks


1.2.0 (2018-01-22)
==================

- implement python based commands in ``pytest-play`` and
  deprecates ``play_python``.
  So this feature is a drop-in replacement for the
  ``play-python`` plugin.

  You should no more install ``play_python`` since now.

- update documentation

- deprecate selenium commands (they will be implemented
  on a separate plugin and dropped in
  ``pytest-play`` >= 2.0.0). All your previous scripts
  will work fine, this warning is just for people
  directly importing the provider for some reason.

- implement skip conditions. You can omit the execution of
  any command evaluating a Python based skip condition


1.1.0 (2018-01-16)
==================

- Documentation updated (add new pytest play plugins)

- Support default payloads for command providers. Useful
  for HTTP authentication headers, common database settings


1.0.0 (2018-01-10)
==================

- execute command accepts kwargs now

- execute command returns the command value now

- complete refactor of ``include`` provider (no
  backwards compatibility)

- add ``play_json.get_file_contents`` and removed
  ``data_getter`` fixture (no backwards compatibility)


0.3.1 (2018-01-04)
==================

- play engine now logs commands to be executed and errors


0.3.0 (2018-01-04)
==================

- you are able to update variables when executing commands

- you can extend ``pytest-play`` with new pluggable commands coming
  from third party packages thanks to setuptools entrypoints


0.2.0 (2018-01-02)
==================

- no more open browser by default
  pytest-play is a generic test engine and it could be used for non UI tests too.

  So there is no need to open the browser for non UI tests (eg: API tests)


0.1.0 (2017-12-22)
==================

- implement reusable steps (include scenario)

- minor documentation changes

0.0.1 (2017-12-20)
==================

- First release
