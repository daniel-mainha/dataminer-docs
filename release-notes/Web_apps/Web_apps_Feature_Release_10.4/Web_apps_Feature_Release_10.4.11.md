---
uid: Web_apps_Feature_Release_10.4.11
---

# DataMiner web apps Feature Release 10.4.11 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For release notes for this release that are not related to the web applications, see [General Feature Release 10.4.11](xref:General_Feature_Release_10.4.11).

## Highlights

*No highlights have been selected yet.*

## New features

#### Low-Code Apps - Time range component: New 'Set value' action [ID 40569]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

It is now possible to configure a *Set value* action for a *Time range* component.

This action will allow users to set the current value of the component in question to either a preset range (today, yesterday, next year, ...) or a custom range (which can be either a static value or a feed).

## Changes

### Enhancements

#### Web API - DataMiner Object Models: Client applications will now be notified when a DOM instance no longer matches the subscription filter [ID 40621]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

From now on, when a DOM instance no longer matches the subscription filter, the client application will be notified.

#### Dashboards/Low-Code Apps - Time range component: Apply and Cancel buttons [ID 40622]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

Up to now, when you set a custom time range in the *Time range* component, the feed of the component would immediately be updated. From now on, the feed will only be updated when you click the *Apply* button.

Clicking the *Cancel* button will close the time range picker without updating the feed.

#### Dashboards/Low-Code Apps - Query filter component: Dates used in filters will now be in UTC format [ID 40653]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When, in a *Query filter* component, you filtered by date, up to now, the date used in the filter would be in local format.

From now on, the displayed date will still be in local format, but the date that will actually be used in the filter will be in UTC format.

#### Dashboards/Low-Code Apps - Security: Enhanced loading of user access data [ID 40671]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

A number of enhancements have been made with regard to the loading of user access data when configuring user access restrictions for dashboards or low-code apps.

#### Dashboards app: Enhanced 'Location' box in 'Create dashboard' and 'Dashboard settings' windows [ID 40692]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

In the *Create dashboard* and *Dashboard settings* windows, the *Location* box has been reworked. It will now take up less screen real estate.

#### Dashboards/Low-Code Apps - Alarm table component: Enhanced performance when loading history alarms [ID 40696]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

Because of a number of enhancements, overall performance of the *Alarm table* component has increased when loading history alarms.

### Fixes

#### Low-Code Apps - Form component: Dropdown fields containing elements, resources or service definitions would show an incorrect warning message [ID 40399]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

Up to now, dropdown fields defined as `ElementFieldDescriptor`, `ResourceFieldDescriptor` or `ServiceDefinitionFieldDescriptor` would display all items. However, when there were more than 100 items, an incorrect message would appear, stating that not all values were being displayed.

This behavior has now changed:

- If a dropdown field is defined as `ElementFieldDescriptor`, the above-mentioned message will no longer appear. The field will always show all elements.

- If a dropdown field is defined as `ResourceFieldDescriptor` or `ServiceDefinitionFieldDescriptor`, it will now initially show only 100 items. When there are more than 100 items, a message will appear, indicating that there are more items.

Also, dropdown fields defined as `ResourceFieldDescriptor` or `ServiceDefinitionFieldDescriptor` will now use a paging mechanism (in case of the former, only if the DataMiner server version is 10.4.9 or newer).

> [!NOTE]
>
> - If a resource is found in multiple resource pools, it will appear in a dropdown field multiple times (i.e. once for every pool it is found in).
> - If a dropdown field defined as `ResourceFieldDescriptor` or `ServiceDefinitionFieldDescriptor` contains more than 100 items, it is advised to adapt the filter in order to reduce the number of items in the dropdown field.

#### Dashboards app: Folders of which the name contained a slash ('/') or a backslash ('\\') character would stay hidden [ID 40532]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you created a dashboard folder of which the name contained a slash ("/") or a backslash ("\\") character, up to now, the folder would be created, but would stay hidden. It would not appear in the folder structure.

From now on, when you enter a folder name containing a slash ("/") or a backslash ("\\") character, an `Invalid folder name message` will appear.

#### Dashboards app: Inconsistent folder selection behavior [ID 40561]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When a dashboard folder contained child folders, up to now, the main folder would open when you clicked it once, while the child folders would only open when you clicked them twice. From now on, all dashboard folders will open when you click their chevron once.

#### Dashboards/Low-Code Apps - Security: Users would incorrectly not have a profile picture [ID 40617]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you were configuring user access to a dashboard, a dashboard folder or a low-code app, up to now, users would incorrectly not have a profile picture. From now on, every user will have a profile picture.

#### Dashboards/Low-Code Apps - Security: User who duplicated a dashboard would incorrectly not be allowed to edit the newly created duplicate [ID 40627]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

Up to now, when a user duplicated a dashboard with access restrictions, in some cases, that user would incorrectly not be added as editor to the user access settings of the newly created duplicate.

From now on, when a user duplicates a dashboard with access restrictions, that user will always be added as editor to the user access settings of the newly created duplicate.

#### Dashboards app: Problem when trying to delete a dashboard subfolder [ID 40634]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you tried to delete a subfolder of a dashboard folder, in some cases, an error could be thrown. That error would incorrectly state that the folder name cannot be empty.

#### Dashboards app - Security: Not possible to update the access permissions of the root folder [ID 40644]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

In some cases, it would not be possible to update the access permissions of the root folder.

#### Dashboards app: Newly added folder would incorrectly be shown twice in the UI [ID 40649]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you added a new dashboard folder, up to now, that folder would incorrectly be shown twice in the UI.

#### Low-Code Apps: Output feed of a script would not be updated when a 'Launch a script' action was followed by post actions [ID 40664]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When a *Launch a script* action was executed, followed by one or more post actions, the script's output feed would incorrectly not be updated.

#### Low-Code Apps: Components using feeds would not be rendered correctly [ID 40665]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

In some cases, components using feeds would not be rendered correctly.

#### Dashboards app: Parameter states would be empty if their index was not visible [ID 40672]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When a parameter state had an index, but that index was not visible (e.g. a dropped process in Task Manager), up to now, the state itself would not be displayed. From now on, if a state is empty, the text "Not initialized" will be shown instead.

#### Dashboards app: URL would incorrectly not be updated when a selection was made in one of its components [ID 40673]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

In some cases, the URL of a dashboard would incorrectly not be updated when you made a selection in one of its components.

#### Dashboards/Low-Code Apps - Web component: Problem when using a URL pointing to an untrusted source [ID 40685]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

In some cases, a *Web* component would not render a web page correctly when the URL pointed to an untrusted source.

#### Dashboards app: Problem when renaming a dashboard folder after having renamed its parent folder [ID 40688]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you renamed a dashboard folder immediately after having renamed its parent folder, the folder would be renamed in the system but the UI would incorrectly still show the old name.

#### Dashboards/Low-Code Apps - Maps component: Problem when refreshing a map [ID 40697]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When a map was refreshed, in some cases, markers at the edges of the map would incorrectly disappear.

#### Low-Code Apps: New draft would incorrectly be a copy of a draft you discarded earlier [ID 40706]

<!-- MR 10.3.0 [CU20] / 10.4.0 [CU8] - FR 10.4.11 -->

When you discarded a draft of a published low-code app, and then created a new draft of that same app, the new draft would incorrectly not be a copy of the published low-code app. Instead, it would be a copy of the draft you discarded earlier.
