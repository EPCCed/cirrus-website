---
title: Cirrus EX4000 service start - charging enabled and updated login address
date: 2025-12-08T10:00:00
---
Dear Cirrus EX4000 Users,

We are pleased to announce that the new Cirrus EX4000 service has now started. Jobs finishing after 0800 GMT today (Mon 8 Dec 2025) will be charged against budgets.

You should now use "login.cirrus.ac.uk" to access the system rather than "preview.cirrus.ac.uk". The preview address will be removed at some time in the future. If you previously had a entry in your "known_hosts" file for the old Cirrus login nodes, you may need to manualy remove this before you can login. An example of the error and how you can fix it are included at the bottom of this message.

If you have any questions or run into issues with the new Cirrus EX4000 system, please contact the service desk: support@cirrus.ac.uk.

Regards

Andy Turner

Cirrus Service Desk


---

If you have an entry in your known hosts file for old Cirrus login nodes you may see an error similar to:

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@ WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED! @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ED25519 key sent by the remote host is
SHA256:WX5NbmOOYZdcm0HN3KgSkkI67+cSudpll0E1R6n9nto.
Please contact your system administrator.
Add correct host key in /Users/auser/.ssh/known_hosts to get rid of this message.
Offending ECDSA key in /Users/auser/.ssh/known_hosts:2
Host key for login.cirrus.ac.uk has changed and you have requested strict checking.
Host key verification failed.
```

When you try to login to the new service using "login.cirrus.ac.uk".

To fix this, you should delete the offending line from the file. The error indicates the line to delete (in the example above, it is line number 2 in the file).

---

This message was sent to the
Cirrus [Major Announcements] list.

Instructions on how to manage your mailing list subscriptions are at: https://epcced.github.io/safe-docs/safe-for-users/#user-mailing-options