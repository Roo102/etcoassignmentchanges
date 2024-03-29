Etco changes to the Assignment Plugin
-

In order to make the marking workflow work in the way we wanted it to, and limit the permissions of some roles, changes have been made to this core assign code.

* Bullet point items were added in the most recent updates 15/02/2023.

access.php
-
Added two new capabilities mod/assign:completemarking and mod/assign:assessor to allow restriction of the workflow options and which users appear in the list of available markers (see lines 152 - 168)

assign.php
-
Named new capabilities (see lines 53 & 54)
Named new setting (see lines 43 & 133)

* Add notification text for marker allocated notification (see lines 231 - 240)

gradingoptionsform.php
-
Added check for new assign/allowquickgrading setting (see line 77)

gradingtable.php
-
Populate $markers variable with users who have the mod/assign:assessor capability instead of the mod/assign:grade capability (see line 686)

locallib.php
-
Populate $markers variable with users who have the mod/assign:assessor capability instead of the mod/assign:grade capability (see lines 4501, 5138, 7210, 7875, 8351, 9434).

Added requirement for user to have mod/assign:completemarking capability to see marking allocated to them, this also allows users without this capability but with the mod/assign:grade capability to see users in their group without the need to have them assigned (see line 2177).

Restrict users without the mod/assign:completemarking capability to only access the first two steps of the marking workflow. This prevents users with this capability but without the mod/assign:grade capability from selecting the Marking complete workflow step.

Added check for new assign/allowquickgrading setting (see lines 4485 - 4489)

* Only Assessors should be able to change the grade value (see line 7649)

* Allow Assessor to be assigned at the same time as workflow moved to 'Assessor assigned' (see line 7874)

* Create notification for markers to let them know they have been allocated to mark an assignment (see lines 6572 - 6603)

* Update Submission timemodified and send notification to allocated marker (see lines 8382 - 8391 & 8500 - 8507)

settings.php
-
Added setting to enable / disable quick grading (assign/allowquickgrading see lines 42 - 47)

These changes were made by Andrew Chandler (andrewc@etco.co.nz) on the 19th October 2022 and are not intended to be used outside of The Electrical Training Company Ltd.
-
