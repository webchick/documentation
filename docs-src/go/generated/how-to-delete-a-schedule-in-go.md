---
id: how-to-delete-a-schedule-in-go
title: How to delete a Schedule in Go
sidebar_label: Delete Schedule
description: To delete a Schedule, use `Delete()` on the `ScheduleHandle`.
tags:
- go sdk
- code sample
- schedule
- delete
---

<!-- DO NOT EDIT THIS FILE DIRECTLY.
THIS FILE IS GENERATED from https://github.com/temporalio/documentation-samples-go/blob/main/schedule/delete/main_dacx.go. -->

Deleting a Schedule erases a Schedule.
Deletion does not affect any Workflows started by the Schedule.

To delete a Schedule, use `Delete()` on the `ScheduleHandle`.

<div class="copycode-notice-container"><div class="copycode-notice"><img data-style="copycode-icon" src="/icons/copycode.png" alt="Copy code icon" /> Sample application code information <img id="i-260a74c5-5137-4ce2-9a18-59eeed31f475" data-event="clickable-copycode-info" data-style="chevron-icon" src="/icons/chevron.png" alt="Chevron icon" /></div><div id="copycode-info-260a74c5-5137-4ce2-9a18-59eeed31f475" class="copycode-info">The following code sample comes from a working and tested sample application. The code sample might be abridged within the guide to highlight key aspects. Visit the source repository to <a href="https://github.com/temporalio/documentation-samples-go/blob/main/schedule/delete/main_dacx.go">view the source code</a> in the context of the rest of the application code.</div></div>

```go
func main() {
// ...
	defer func() {
		log.Println("Deleting schedule", "ScheduleID", scheduleHandle.GetID())
		err = scheduleHandle.Delete(ctx)
		if err != nil {
			log.Fatalln("Unable to delete schedule", err)
		}
	}()
// ...
```