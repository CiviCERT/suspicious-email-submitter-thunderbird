# suspicious-email-submitter-thunderbird

A Thunderbird add-on to facilitate forwarding malicious emails to analysts via the Suspicious Email Submission process.

## What does it do?

### Globally

In the global menubar there will be an entry, “SES”, with two child items: “Load config file” which will load a new config file into SES, and “About SES”, which will take you to SES’s home on the web.

### Toolbars

Both the 3-pane view toolbar and the single-message-view toolbar have a button added labeled “Report to SES”.  Once SES is configured, this button will send the email off to whatever MISP upstream has been set up.

### Context menu

In the mail context menu there’s a “Report to SES” entry.

## How can I test it out?

You will need [Python 3.5 or later](https://www.python.org/downloads/) to build from source.

 * Download the latest [source](https://github.com/rjhansen/suspicious-email-submitter-tb/archive/master.zip) and uncompress it to a directory of your choice
 * Open a terminal window and change to that directory
 * Run `python3 ./make-xpi.py`, which will place `SES-tb.xpi` in your home directory
 * Start Thunderbird
 * Install the `.xpi` file found in your home directory
 * Restart Thunderbird
 * You’ll get a file picker prompt.  Choose your SES configuration file.
 * In `Preferences->Toolbar Layout` (`View->Toolbars->Customize` on macOS), click and drag the “Report to SES” button where you like in your Thunderbird toolbar

## Is it only email?

Both `mailto:` and `https://` handlers exist, but only `mailto:` has had significant testing. `https://` is a work in progress.
