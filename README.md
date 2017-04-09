README
------

Gmail Shared Labels is a Google Apps Script that adds the ability to
share labels across fellow google apps-for-your-domain members (or friends).

CODE INSTALLATION
-----------------
To install Shared Labels from code:

 * Navigate to https://script.google.com (or from Google Drive, choose New => More => Google Apps Script)
 * Replace the sample code in the text editor with the contents of "Code.gs"
 * Use the File > Save menu and name the script (e.g. "Gmail Shared Labels")
 * Use the File > New > Html file menu and create a file called "ui"
 * Replace the sample code in the text editor with the contents of "ui.html"
 * Use the Publish > Deploy as Web App menu
 * Click "Save new version" (no need for any text in the box)
 * Change "Execute the app as" to "User accessing the web app"
 * For apps-for-your-domain folks, set 'Access' to "Anyone within (yourdomain.com)"
 * Click Deploy
 * Navigate to the "Current web app URL"
 * Follow the piggyback installation instructions below.


PIGGYBACK INSTALLATION
----------------------
To install from an existing code installation:

 * Navigate to the deployed web app URL from a code installation
 * If prompted to authorize or grant permissions, do so (Security tip: Avoid Google App Scripts that connect to the outside world, or your privacy may be severely violated.)
 * Create a shared folder name
 * Click install


UNINSTALL
---------
You can temporarily uninstall using the Uninstall button at the web app URL.
This will functionally disable Shared Labels but preserve all of your options
for reinstalling later. If you would like to fully uninstall,
there is a link in the automated email you will receive from Apps Script
at installation time. If you did a code installation you can also delete
the project.


USE
---

For each shared label, you create a *name* (to describe to fellow
members what it's for), the *label* that you will share across
members, and an *unlabel* -- a label you will use to trigger removal
of the actual label.

For instance, let's say you have a label named "resolved", and choose
the unlabel of "unresolved" -- when an email thread is mislabeled
"resolved" (i.e. maybe the status changed), then add the label
"unresolved."  That will trigger the next run to remove the label
"resolved" from your fellow members, (including yourself).

Synchronization is NOT immediate -- it will generally occur at
whatever twice the value of UPDATE_MINUTES is set to at the top of
Code.gs.  The repository has it set to 1, so it should take about two
minutes for fellow members to sync.
(Note that Google only allows certain values for UPDATE_MINUTES;
 It can also be 5 or 10, e.g.)

Whenever you want to create a new shared label across people, then go
to the installation screen, add aq label and click Save.  Then tell
others to visit the same URL and add themselves as members (checking
the box, and clicking Save/Install).

AUTHOR
------

* Schuyler Duveen (https://github.com/schuyler1d)
