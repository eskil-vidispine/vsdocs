---
title: "Release Notes"
date: 2018-12-29T11:02:05+06:00
icon: "ti-panel"
type : "docs"
weight: "2"
---

The following items on the list encompass breaking changes, features,
and fixes that are relevant for the major release.

Release Notes are divided into the following sections:

# Breaking Changes

None. This is the first released version of VidiEditor.

# Features

The first version of VidiEditor comes with the possibility of basic
video editing in the browser. Please check the Product Overview for
general information about the product.

The following features were implemented in 2020 and offer an overview of
the latest features:

#### **Buffer indicator**

VidiEditor’s source and timeline player now display the streaming buffer
of the streaming backend to the user. An indicator is shown on the
timeline itself. The indicator displays which parts of the video stream
are directly available and which parts need to be loaded still - which
will force latency before a playback is possible.

#### **Audio output on frame steps and scrubbing**

When navigating frame-by-frame, or when scrubbing in the player (source
and timeline), the user will hear the audio output. This feature aids
the user in quickly and easily finding the wanted positions for IN/OUT
points in the source player according to the audio content (e.g.: Start
of an interview).

#### **Direct out possibility **

VidiEditor allows for a specific configuration for audio direct out. If
this configuration is set up correctly, (depending on the shape tag
configuration), all mix options from the timeline will be ignored
and the rendered output file will have the original audio channels of
the video item on top of the tracks. 

Requires Vidispine 5.3.2.

#### **Metrics **

VidiEditor comes with an implementation for Prometheus Metrics that
allows one to aggregate monitoring data using monitoring tools such as
Grafana at an API level. 

#### **Dynamic GUI sizing**

Users are now able to choose between the “Edit” and “Media Management”
views. Depending on the screen resolution, the better view is offered on
default. Also, the user can dynamically size the player area, parts of
the timeline area and collapse the Search/Bin area. The user settings
will be reset to default after a page refresh.

#### **Audio-only support**

VidiEditor supports handling of audio-only media in the source and
timeline preview with the following formats: 

-   Codec: AAC 

-   Container: MP4 \| M4A

-   48 kHz

-   192 kbps 

This includes a waveform preview in the source player as well as usage
in timeline and insert edit workflow. It is used in the mix on publish
depending on the static preset configuration. 

#### **Voice-over recording**

This feature allows a user to record voice-over from a connected
microphone on a dedicated voice-over track. The voice-over can be
ingested to the central media repository for later use. Also, the
voice-over can be selected for mixdown in static configuration of
transcoding presets (shape tag). 

#### **Audio mix down in publish **

Allows one to have the correct audio mix in published media generated in
the transcoding backend of VidiEditor. Furthermore, options are
available to separate voice-over recordings using shape tag
configuration. 

Requires Vidispine: 5.3.2.

#### **Smart rendering **

The timeline playback uses smart rendering to intelligently decide which
areas need rendering and therefore being more efficient on computing
resources. 

Requires Streaming Server 20.2.1-beta.97.

#### **Audio channel duplication **

VidiEditor allows the user to duplicate one audio channel to both sides
of a stereo track as a duplicate. This can be done in the source preview
as well as in the timeline per segment. 

#### **Audio channel selection **

VidiEditor allows one to select audio channels in source player for
insert edit and selection of channels per segment in timeline. 

#### **Frame rate support **

VidiEditor supports following proxy frame rates – in matching projects
for supported video formats: 

-   25 fps 

-   30 fps 

-   29.97 fps 

-   59.94 fps 

One timeline is restricted to one frame rate. All media inside a project
must have the same frame rate. The user can choose which frame rate to
use.

#### **Audio playback **

VidiEditor’s timeline allows one to playback one or multiple audio
tracks, and mix these to 1 stereo pair of audio in the timeline preview.
This mix is also used in the rendering process depending on the
transcoder preset configuration (shape tag). A peak meter indicates the
audio level to the user. 

#### **Camera card container support (Enterprise version only)**

VidiEditor supports camera card container structure ingested using
MediaIngest. The user is able to search those as videos, navigate in the
card structure, and use them in the source player and timeline for
editing. 

#### **Search dialog configuration with metadata fields (Enterprise version only) **

VidiEditor’s search dialog metadata fields can now be configured. The
configuration of the Vidispine metadata fields is then expressed in the
grid columns for the Media Search, Project Search or Media Bin. As a
result, the information can be optimized based on the customer-specific
system design. 

#### **Search and import persisted Vidispine collections **

Specific types of Vidispine collections can now be searched for and used
in VidiEditor. Users are able to batch import videos contained in
these Vidispine collections. This requires collections of the type
“PersistedBin“, otherwise collections will be filtered out in the
search.

#### **Player framework reintegration**

The player framework has been reintegrated with VidiEditor. Several
player functions have now become available in the player. 

-   Original Timecodes 

<!-- -->

-   Fast forward / backward

-   Subtitle support  (No end-to-end Use Case in VidiEditor yet)

-   IN/OUT points 

-   Duration info 

-   Optimized growing file support (requires MXF RDD25 proxy)

<div>

<div>

**Please note** that not all of the framework functionalities have
resulted in an end-to-end functionality in VidiEditor. Additional
functions being expressed in VidiEditor may be added in future
releases. 

</div>

</div>

#### **Close project **

Closing a project in VidiEditor will now save the state of the project,
remove the editing lock, clear the timeline, and return the user
to VidiEditor’s default state. Users can then choose to either create a
new project or search and open an existing one. 

#### **Ripple edit mode  **

By choosing the “Ripple Edit” option, users can adjust the segments in
the timeline while ensuring that subsequent segments in the timeline are
intelligently repositioned and shifted by the same degree. This effect
works when either trimming a segment or extending it to its maximum
length.

**Using a VidiFlow workflow to render output (Enterprise version
only) **

In a joint scenario with VidiFlow, VidiEditor can trigger BPMN
workflows responsible for rendering and publishing the timeline that are
part of VidiFlow. This allows for the customization of process steps
after publishing using VidiFlow. It is important to note that multiple
workflows can be dynamically configured, allowing for a more flexible
workflow design. 

Requires VidiFlow.

#### **Configuring the publish metadata – (Vidinet version) **

Administrators are now given the possibility to configure the
publish dialog by specifying a specific metadata group. This feature
is intended for installation scenarios of a smaller scale. On enterprise
systems this case is covered by the ConfigPortal.

#### **Saving publish dialog metadata to the rendered item **

Whenever an item on the timeline is published, all of the project’s
metadata is automatically copied to the newly created item.  

#### **Project save status indicator “Auto Save”**

Whenever a user interacts with the timeline by performing changes,
the project is saved with an indicator informing the user of the
auto-save status. 

#### **Vidispine 5 Support **

VidiEditor is compatible with Vidispine version 5 - not on Vidispine 4
anymore.

**Configuring create and edit project dialog (Enterprise version
only) **

Via ConfigPortal, users are now able to dynamically control which
metadata fields are visible in VidiEditor for the create and edit
project dialogs. 

**Deletion protection for project media **

Media used in VidiEditor projects is protected from VidiFlow’s automatic
deletion mechanism.  

#### **Publish dialogue redesign**

The publish dialogue has been redesigned in order to provide users
with a cleaner publishing process. Additionally, the new dialog
window allows for a more flexible configuration of metadata, interface
integration with VidiFlow workflows, and alignment with EditMate.  

#### **Configuring publish dialogue (Enterprise version only)**

Via ConfigPortal, users are now able to dynamically control which
metadata fields are visible in VidiEditor for the publish dialog.  

#### **Dynamic context menu enhancements **

When editing in the timeline, users are able to open the context menu
for individual segments. Depending on the segment media type and status,
the context menu will dynamically provide options relevant to the
segment.

# Fixes

<div class="table-wrap">

|             |                                                                                                                               |
|-------------|-------------------------------------------------------------------------------------------------------------------------------|
| **Item \#** | **Item Title**                                                                                                                |
| 179765      | Waveform Handling: Expired Image URL and Placeholder image                                                                    |
| 179837      | Effects panel Tab: Sometime will show up word overlay at the bottom of current tree list                                      |
| 179754      | Moving Timeline Segments: Revert back the changes                                                                             |
| 179790      | Buffer indicator on timeline is not rest after project open                                                                   |
| 178631      | Timeline Move mode asyncs audio video when dropping over segment.out position                                                 |
| 179535      | Gaps are not shown correctly on hovering                                                                                      |
| 179749      | Open project with recent project throws not found (snackbar)                                                                  |
| 179840      | Keyboard: Home/End move to start of segments or end of segments                                                               |
| 173927      | VoiceOver Record must be limited to 1hour max per record action of user                                                       |
| 178843      | Direct Out ShapeTag selection is not send to workflow on publish (VPMS Context)                                               |
| 179353      | Sequence Document is containing an item without a path                                                                        |
| 177319      | Change Name in Licence Info PDF                                                                                               |
| 178246      | Should go to home page when session is expired (VN Context)                                                                   |
| 177069      | Shortcut key: Unable to close sound channel with "ESC" key                                                                    |
| 178931      | Open Project Create date should be in user friendly format                                                                    |
| 177994      | Audio Only Preview: Uncheck Double Singles messes up player functionality                                                     |
| 178496      | Scrubbing in Timeline is laggy compared to Timeline player                                                                    |
| 178999      | Source Player Audio Speed dropdown hidden under timeline                                                                      |
| 178463      | Timeline: When navigation between cuts on end of timeline wrong picture is shown in timeline player                           |
| 178129      | VoiceOver Record Broken in Current Version                                                                                    |
| 178840      | VidiEditor send wrong shape path to streaming server                                                                          |
| 173404      | Moving Segment from one track to another works differently on selected and not selected segments                              |
| 178844      | Multiple publish uses same target item ID again                                                                               |
| 178856      | Styling Whitline under players looks a bit unclean                                                                            |
| 178617      | On Copy Segment - Message is wrong                                                                                            |
| 175548      | Waiting on VE: Timeline Scrubbing (TRP Mode) ignores track ordering                                                           |
| 178620      | After Refresh Token in Vidinet expires the user is in GUI but gets Null Reference Exceptions                                  |
| 178217      | Press "Enter" will not perform search action                                                                                  |
| 178618      | After Idle Time User sees Null Reference Exception as Lock API Call was not successfull (VN Context)                          |
| 178347      | Waveforms just shows up on segement after click on segment                                                                    |
| 178245      | Project Search: only maximum 100 result, even system have more result than that                                               |
| 178498      | Ensure Deployment of VidiEditor works with latest K8S / Ingress version                                                       |
| 178674      | Tweak Trim In/Out area on hovering to be not flickering                                                                       |
| 178638      | Link / Unlink option should show meaningful error message                                                                     |
| 178723      | Segment block not able to move to left that blocked to move                                                                   |
| 178686      | Multiselect and move to start of timeline destroys segment before selected one                                                |
| 178510      | VoiceOver: sound distortion                                                                                                   |
| 178272      | RenderEngine: multiple video tracks don't play correctly                                                                      |
| 170058      | As a ME user I want to navigate through input fields in project edit and publish dialogues through tab and shift +tab         |
| 178824      | InsertEdit on fresh project -&gt; Timeline Player not updated on 1st cut                                                      |
| 178590      | InsertEdit: Last out point not updated correctly in Timeline Player                                                           |
| 178823      | Media cannot be added to Source Player from Bin                                                                               |
| 175742      | Optimize Caching Mechanisms in/for Render Engine                                                                              |
| 178918      | Unselect segments on gap needs to work                                                                                        |
| 176054      | Player: Shortcut key should able to work when video is ended                                                                  |
| 177407      | CP: Adjust Tooltips and Description for Config Switches                                                                       |
| 178134      | VO - Browser ask for MIc if not enabled for VE Webpage - should be earlier                                                    |
| 177844      | Have Audio Only MP4 files with mime type audio/mp4                                                                            |
| 175522      | Source Player Frame for / back with audio playback                                                                            |
| 176696      | Player Styling no linebrake please on long titles                                                                             |
| 177509      | VO Records cannot be added from bin to source via drag and drop                                                               |
| 178008      | Link/Unlink: link/unlink not working for paste item                                                                           |
| 177508      | VoiceOver: Record before existing record not working end to end                                                               |
| 177993      | Search Window has broken styling / too large search box and media dropdown                                                    |
| 175062      | Optimize Waveform load for long/many segments as GUI gets unresponsive at the moment                                          |
| 174022      | Fast Editing in Timline forces very unresponsive GUI                                                                          |
| 178051      | Mark Segment (left click) has latency on timeline with many segments                                                          |
| 177391      | ConcurrentUsers: seem to be reached but not reached - cache need to be cleared                                                |
| 178132      | Blend out audio leveling options and stuff in GUI                                                                             |
| 177397      | GUI Performance: Optimize handling of Gaps                                                                                    |
| 173325      | Project Lock: Null Reference Exception thrown when PUT -&gt; Lock cannot set via API                                          |
| 174193      | Staling: Style the license info button                                                                                        |
| 177498      | Product information modal optimize styling / space                                                                            |
| 177504      | Optimize Error Message on add to source player for config "use presigned pathes" = true but not working                       |
| 177500      | Switch Mode button should evaluate out the active mode user is in                                                             |
| 172354      | ME shows in italic on some workstations                                                                                       |
| 177088      | Player: tooltips are somewhere but not where the button is                                                                    |
| 177093      | Shortcut key: Keyboard key is not working after mouse click on button                                                         |
| 171366      | Validation on Metadata Type Date                                                                                              |
| 177410      | Config Data on Metadata View Builder Not fetched from CP                                                                      |
| 177501      | After being inactive assets cannot be dragged to Timeline anymore                                                             |
| 177324      | ConcurrentUser: MaxconcurrentUser value is not get automatically after user change in configmap                               |
| 176526      | Timeline: selected/moving/resizing blocks should always on (zindex)                                                           |
| 175364      | ME Config: Publish Shape tag selection should be hidden if not set up in VPMS context                                         |
| 176751      | Analyze job was trigger multiple times for the same item                                                                      |
| 170142      | Metadata Mask(s) have default value for created / date without setting it up                                                  |
| 176746      | Timeline: Snap with 2 segment on different layer with same in/out no working                                                  |
| 176103      | CP fixed value option does not work on kendo filtering in Grid                                                                |
| 171110      | ME Search: support to search more than one shapetag                                                                           |
| 174423      | Metadata Dialogues: Use Current Date config from CP as default value                                                          |
| 176715      | Playhead jumps to 00:00:00:00 after using mute / hide options                                                                 |
| 176320      | Timeline: Playhead jumps to position 00:00:00:00 after timeline changes                                                       |
| 176319      | Timeline Drag and drop a segment moves playhead under segment                                                                 |
| 175688      | When resize, the drag move over to left and make segment not align                                                            |
| 175041      | Recently Opened Section: Project title name is not refresh in recently opened project                                         |
| 174789      | Source player add to timeline should scroll set playhead to last cut and scroll timeline                                      |
| 173608      | Timeline Segments Trim, the user needs a better indicator what segment is selected when doing trim via drag and drop          |
| 167148      | Small layout issue (flex) appears when having one expanded mono channel on a layer under a layer with stereo channels         |
| 176226      | Waiting on VE: AAC Audio Only Items ar not playable in Source Player                                                          |
| 176052      | Player: Play backward not working when media has ended                                                                        |
| 174787      | UI: Open Project dialogue will show a horizontal scroll bar if the project name is very long                                  |
| 174355      | Player: Original Timecode Indicator in player has not aligned styling                                                         |
| 175701      | FrameRate: Convert old projects to frame units on open automatically                                                          |
| 174190      | Player: Validation of entering TC Position in Jump to TC broken                                                               |
| 172608      | Source Player Change playback speed with multiple click on Keyboard J and L                                                   |
| 172606      | Player navigation using JKL in Source Player                                                                                  |
| 173250      | Search / Bin / Project Configurable grids are not sortable on metadata fields (in one page)                                   |
| 173048      | Alphanumeric Sorting is not working (Open Project, Project Bin, Search Media)                                                 |
| 175612      | Search Configurable grids are not sortable on metadata fields (over all page)                                                 |
| 174423      | Metadata Dialogues: Use Current Date config from CP as default value                                                          |
| 174290      | Trim in point of Audio Channel in Timeline shifts audio wave form on not selected channel                                     |
| 170752      | ME Analyze Jobs are always failing when triggered from ME                                                                     |
| 173480      | Search: Refresh button should have indicator to be clickable -&gt; hover to change icon to refresh                            |
| 174917      | Basic Authentication was not authenticated keep on logging                                                                    |
| 174300      | Cam Card: Resizing of the Camera Card Child Segment                                                                           |
| 174354      | CamCard: Bin area Collapse/Expand icon not available after add Camera Card - after refresh its displayed                      |
| 174467      | CamCards: Adding to Timeline with many clips takes very long                                                                  |
| 169508      | As an admin I want to see the license info delivered with the MediaEditor version                                             |
| 174191      | Cam Card: Tooltip should combine Parent title and Clipname                                                                    |
| 167141      | Timeline: Double Single of audio layer is not adding correctly into timeline, when timeline is empty                          |
| 174452      | \[Transition\] Previous Gap is still visible after doing undo                                                                 |
| 174192      | Cam Card: Ensure CP Config allows to add Cam Card flag/indicator to ME grids                                                  |
| 174451      | Overlay in the timeline is not properly displayed                                                                             |
| 174304      | Cam Card: Waveform should take from the SegmentDuration                                                                       |
| 174189      | Cam Card: Add parent element adds just one child element of the container                                                     |
| 174484      | Collection: Child item not able to playback in timeline player                                                                |
| 174053      | Logout: browser become not responsive                                                                                         |
| 174291      | Source Player: Audio Selection doesn't work on add to timeline - always uses 1/2                                              |
| 170752      | ME Analyze Jobs are always failing when triggered from ME                                                                     |
| 173300      | SourcePlayer: Add to Timline Button loses ME focus for Keyboard Shortcuts after click                                         |
| 172618      | Setup test scenario on growing files in ME (VPMS Context / SMB Storages only)                                                 |
| 173870      | Project: If the project is deleted from Vidispine, show proper msg.                                                           |
| 173431      | Player: Trick mode can be activate from ME timeline Playhead                                                                  |
| 173333      | Dialogues: Confirm buttons clickable when field set to required are not filled out or invalid                                 |
| 173899      | Timeline Player Spinner wheel stays visible while playback                                                                    |
| 173464      | Timeline position needle jumps to wrong cut on timeline preview play                                                          |
| 171260      | Source player add to timeline with move / overwrite mode.                                                                     |
| 173328      | Multiple video tracks played in wrong order when working in specific order                                                    |
| 173572      | Publish: New transcoded item has last frame doubled.                                                                          |
| 172349      | Timeline Ripple Delete unsyncs audio/video if different gaps are on video and audio.                                          |
| 171225      | Timeline: after resize there are few seconds off.                                                                             |
| 173296      | LogOut: leave site warning should not show.                                                                                   |
| 167145      | Timeline: Paste of multiple videos --&gt; One video has connections to all pasted audio (same for all pasted videos).         |
| 173644      | ContextMenu: open context menu from gap then segment, delete action is not trigger.                                           |
| 173591      | keyboard shortcut: Link/unlink (ctrl+N), open new chrome tab).                                                                |
| 173297      | player: Player should not show loading when drag same items into source player.                                               |
| 173370      | Enum metadata type value issue.                                                                                               |
| 173247      | Project Lock message on Session A (stolen) needs options to close modal.                                                      |
| 173488      | Keyboard Shortcuts Info, rename Blocks to Segments and channel to tracks.                                                     |
| 173105      | NDR: Create/Edit Project with configured metadata required doesn't work.                                                      |
| 172796      | Vidinet Playback and Autosave fails on some items.                                                                            |
| 172489      | Project Metadata get not persisted in Vidispine on save.                                                                      |
| 172473      | \[Waveforms\] - 404 Waveforms URI.                                                                                            |
| 172393      | Should only allow project open at one session.                                                                                |
| 170789      | Import to timeline from source preview player broken.                                                                         |
| 170008      | Optimize Performance on initial Streaming Service playback.                                                                   |
| 172256      | ME Analyze jobs are always trigger for Video only clip.                                                                       |
| 172758      | Item path only able to get if there is item in project bin.                                                                   |
| 172915      | Item in timeline but not in project bin.                                                                                      |
| 172794      | Project Load: Double click shows not supported playback message.                                                              |
| 172795      | Load Project: Double click on result should open project.                                                                     |
| 170130      | No cuts tool can be used on the project "Demo" in VPMS3testsystem.                                                            |
| 172976      | Adding Collection to Project Bin.                                                                                             |
| 172361      | ME keeps on restarting almost every 12-15 mins.                                                                               |
| 172242      | Pressing space, both players start playback.                                                                                  |
| 172244      | JKL short cut in Source Player is not working                                                                                 |
| 172566      | Item duration is not same as the player display duration.                                                                     |
| 171211      | Timeline context menu: showing browser context menu after drag segment from one layer to another and back to original layer.  |
| 171787      | Project Bin: child inside parent cannot be dragged or double clicked.                                                         |
| 171341      | NDR TRANS ME Source Player doesn't show audio channel selection.                                                              |
| 170772      | ME Search media on all media optimization.                                                                                    |
| 171402      | CP does not invalidate cache for resolved config by product GUID.                                                             |
| 171259      | Source Player add to timeline: needle needs to jump to end of cut.                                                            |
| 171507      | Timeline: Keyboard navigation between segments does not work on cut segments.                                                 |
| 170760      | ME Search Media Dialogue optimize paging navigation on scroll.                                                                |
| 170424      | Config: Optimizing the CP Resolve call to still return the resolvable UC Configuration and the logged the error, if there is. |
| 171127      | Storage path: Should remove credential from the path before pass to streaming server.                                         |
| 167149      | Timeline Preview: Timeline preview player does not react to switching of projects.                                            |
| 167139      | Unlink/link -&gt; Resizes the block to the original, if trimmed.                                                              |
| 170038      | ME Publish/CreateProject: Change labels / headers in Publish and Project dialogue.                                            |
| 170041      | Config: Adjust ME UseCase Page "General" in VPMSContext.                                                                      |
| 170389      | Config: On deployment project config UC defintion is not pushed to CP                                                         |
| 170061      | As a ME user I want fill out date fields in metadata masks without seperator characters                                       |
| 170837      | MediaEditor ignores configured deletion lock duration from CP UseCase                                                         |
| 169838      | In Vidipsine context, should re-get the vidispine properties after re login                                                   |
| 169982      | Timeline: Select multiple segment/block, when trim it should not trim all the segments.                                       |
| 169908      | Workflow name is shorten - for no reason.                                                                                     |
| 167150      | Scroll appears and disappears when removing items from project bin.                                                           |
| 169368      | SequenceDocument: segment from same track should part under same track in seq doc, not each segment new track.                |
| 168468      | In VPMS context Publish dialog does not show enum values.                                                                     |
| 168433      | Keyboard short cut info is broken.                                                                                            |

</div>
