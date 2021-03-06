# Mozmill Automation
With the mozmill-automation scripts the [automation development team][team]
at [Mozilla][mozilla] runs UI and integration tests for Firefox.

For more information see our [project page][project] for automation
related topics.

[team]: https://wiki.mozilla.org/QA/Automation
[mozilla]: http://www.mozilla.org/
[project]: https://wiki.mozilla.org/Auto-tools/Automation_Development/Projects/Mozmill_Automation

## Installation
The scripts can be installed by running the following command:

    python setup.py develop

This will also install mercurial, mozinstall and mozmill if required.

## How to run entry point scripts?
The path to the Firefox binary to be tested should be supplied as an argument
to the entry point script. For example, to run the `testrun_functional` script:

    testrun_functional "C:\Program Files (x86)\Firefox Developer Edition\firefox.exe"

There is a `--help` option available for further information of any of the testrun scripts:

    testrun_functional --help

## Addons
The `testrun_addons` script executes available Mozmill tests for add-ons,
which should usually be hosted at http://addons.mozilla.org. For add-ons not
hosted on AMO, you also need to pass in `--with-untrusted` as an argument.

The `testrun_compat_addons` script is a special testrun to execute add-on
compatibility tests for Firefox, which ensures that major add-ons are still
working as expected for a new major release of Firefox.

## Endurance
The `testrun_endurance` script executes the endurance tests for Firefox,
which are long running tests to measure the memory usage and performance of
Firefox.

## Functional
The `testrun_functional` script executes functional tests for Firefox, which
are UI and integration tests, and are necessary for Mozilla QA for signing
off from testing a new Firefox release.

## Localization
The `testrun_l10n` script executes localization tests for Firefox, which are
used to check that localized builds of Firefox are working as expected in
terms of accessibility and graphical output.

## Remote
The `testrun_remote` script executes remote tests for Firefox, which are
similar to the functional tests but make use of remote test cases to prove
the functionality against real web sites.

## Update
The `testrun_update` script executes update tests for Firefox, which ensures
that an update is always correctly performed for Firefox.

When running update tests, you have the option of providing an update
channel. The valid update channels are:

* nightly
* nightlytest
* aurora
* auroratest
* beta
* betatest
* release
* releasetest
* esr
* esrtest
* esr[VERSION]-nightly (for example esr24-nightly)
