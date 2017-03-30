# Needed by Arcola

* automatically run "update" action on startup (as well as
  periodically?)  (incl. configuration option)

* rename "Push" button to "Save to server", and "Update" to "Refresh"
  or so? (incl. configuration option?)

    * what about trying to save to server automatically (and then just
      rename the "Save to server" button to "retry saving to server")?
      Otherwise the only sense it would make is if there's also an
      action to revert changes.

* changed configuration defaults:

    * password length for generated passwords: 14 characters instead of 8
    * no uppercase characters in generated passwords
    * hide password by default

* buttons for "copy login", and "launch URL" (and interpret URLs
  without protocol designator as https), and have "launch URL"
  automatically also copy the login.

* move the "Users" button to after "Delete" or remove completely, and
  add "Users" to the context menu shown on items (right-click)

* needed?: implement additional functionality for per-item users,
  using the meta data storage possibilities that the newest version of
  `pass` offers.

* store all user's public keys as meta data (that the newest version
  of `pass` offers), automatically add them to GnuPG on update, use as
  the users list instead of the keys in the GnuPG
  keyring. (Configuration option?)

    * how to make this secure against an attacker adding fake employee
      keys?  Use network of trust (how to represent in UI)?  Or sign
      the whole key collection with reputable key (but then which keys
      are reputable)?

* Add the "ultimate" (own) public key to the users meta data in the
  repository, either automatically or by confirming a dialog.

* when starting for the first time and GnuPG does not have a private
  key, automatically (or after asking?, since it's a long process)
  create a key pair. (Use somewhat future-proof settings!)

* on X-Windows: probably have copy actions also copy to the X
  selection, not only the clipboard.

* fix the issue that when terminating QtPass by ctl-c, the next time
  it is started it exits right away and then only the second time it
  comes up it starts.

* have a fix for the bug handling the list of GPG keys without private
  keys (the_JinX (on #ijhack on FreeNode) is looking into this)

* have an installation process (on Windows, OS X) that works easily
  (including GnuPG and Git)

* test under Valgrind and ASAN, and review code for pointer usage,
  and/or verify what the Coverity scan covers.

## Nice to have

* verify that the GnuPG public keys used for encryption are
  sufficiently secure.

* to make passwords "unphishable" (aside the offering of the URL
  button that opens the browser on the predefined (and presumably
  correct), unphishable URL): have functionality that offers to (and
  perhaps requires to) copy-paste the current URL in the browser into
  qtpass and only then get the password copied (or if it fails, shows
  error popup). Probably requires an additional "allowed-urls:" field
  or so with a list of secondary (base) URLs (/domains) that are
  allowed to see the password.

