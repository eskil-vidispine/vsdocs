---
title: "Accessing VidiEditor"
date: 2018-12-29T11:02:05+06:00
icon: "ti-panel"
type : "docs"
---

#### Getting Started with VidiEditor

Users who have been granted access for VidiEditor usage in VidiCore can
login (see [Adding Users for VidiEditor \[INT VE 20.2
OG\]](Adding_Users_for_VidiEditor_VE_20.2_OG_)). Just enter the
customer's individual html address in Google's Chrome browser. Login
with your personal user and password and start your project.

![image](/attachments/1297481781/1297481805.png)

**Please note** that when using the Vidinet version of VidiEditor, and
the VidiEditor address (URL) is not known; it can be easily found in
Vidinet under My Services → VidiEditor:

![image](/attachments/1297481781/1297481802.png)

A walkthrough of VidiEditor being initiated can be seen in following
video for the VidiNet version:

{{< youtube IrZ4srO8JSM >}}

#### Concurrent user limitation

The usage of VidiEditor is limited to a fixed amount of concurrent user
sessions. In case the maximum number of allowed sessions is reached, the
user will be unable to login and gets meaningful error message. The user
will be able to login again after a new session is made free. This can
be achieved when:

- Another user uses the logout functionality of VidiEditor
- Another user is inactive for more then 1 hour
- An admin uses the Vidispine API to clear active user sessions. This
    can lead to the scenario in which users are kicked out of the
    application without warnin (see: [Adding Users for VidiEditor \[INT
    VE 20.2 OG\]](Adding_Users_for_VidiEditor_VE_20.2_OG_)).
