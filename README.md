Forked by Shopping-Cross, if you have any question please send email to: shopping-cross@despegar.com

1) Add in the package.json the following dependency.

In this example, v2.24.0 is the branch you are going to download. In future versions you may have to change this value to the last branch created.

...
"dependencies": {
  "moment": "despegar/moment#v2.24.0",
}
....

2) Run: 'npm install' in yout project dir

<hr />

A lightweight JavaScript date library for parsing, validating, manipulating, and formatting dates.

**[Documentation](http://momentjs.com/docs/)**

## Port to ECMAScript 6 (version 2.10.0)

Moment 2.10.0 does not bring any new features, but the code is now written in
ECMAScript 6 modules and placed inside `src/`. Previously `moment.js`, `locale/*.js` and
`test/moment/*.js`, `test/locale/*.js` contained the source of the project. Now
the source is in `src/`, temporary build (ECMAScript 5) files are placed under
`build/umd/` (for running tests during development), and the `moment.js` and
`locale/*.js` files are updated only on release.

If you want to use a particular revision of the code, make sure to run
`grunt transpile update-index`, so `moment.js` and `locales/*.js` are synced
with `src/*`. We might place that in a commit hook in the future.

## Upgrading to 2.0.0
There are a number of small backwards incompatible changes with version 2.0.0. [See the full descriptions here](https://gist.github.com/timrwood/e72f2eef320ed9e37c51#backwards-incompatible-changes)
 * Changed language ordinal method to return the number + ordinal instead of just the ordinal.
 * Changed two digit year parsing cutoff to match strptime.
 * Removed `moment#sod` and `moment#eod` in favor of `moment#startOf` and `moment#endOf`.
 * Removed `moment.humanizeDuration()` in favor of `moment.duration().humanize()`.
 * Removed the lang data objects from the top level namespace.
 * Duplicate `Date` passed to `moment()` instead of referencing it.
