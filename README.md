# sideload-releases

Unsigned iOS builds of Atrium, Vantage, OpenWhispr and Locket, published for
SideStore. Add this source once in SideStore (Sources, then +):

```
https://raw.githubusercontent.com/duaragha/sideload-releases/main/sidestore-source.json
```

Every release here comes from a successful Codemagic build of the app's main
branch. Serena's `serena.fleet.reconcile` checks the build's manifest, commit,
and IPA checksum, plus the bundle ID and version inside the IPA, before it
uploads only the IPA. Then it adds the version to `sidestore-source.json`.
Tags are per app (`atrium-v…`, `vantage-v…`, `openwhispr-v…`, `locket-v…`), and
the version string is exactly the IPA's `CFBundleShortVersionString`, which
SideStore checks on install.

Unified ships separately from `duaragha/unified-releases`.
