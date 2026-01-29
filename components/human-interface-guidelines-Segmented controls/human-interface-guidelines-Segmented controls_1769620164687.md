<span id="page-0-1"></span>**[Design](https://developer.apple.com/design/)** [Overview](https://developer.apple.com/design/) [What's](https://developer.apple.com/design/whats-new/) New Get [Started](https://developer.apple.com/design/get-started/) [Guidelines](https://developer.apple.com/design/human-interface-guidelines) [Resources](https://developer.apple.com/design/resources/)

# **Segmented controls**

A segmented control is a linear set of two or more segments, each of which functions as a button.

![](_page_0_Picture_3.jpeg)

**Supported platforms**

![](_page_0_Picture_5.jpeg)

[Segmented](#page-0-1) controls

Best [practices](#page-0-0)

[Content](#page-1-0)

Platform [considerations](#page-1-1)

[Resources](#page-4-0)

[Change](#page-4-1) log

Within a segmented control, all segments are usually equal in width. Like [buttons,](https://developer.apple.com/design/human-interface-guidelines/buttons) segments can contain text or images. Segments can also have text labels beneath them (or beneath the control as a whole).

A segmented control offers a single choice from among a set of options, or in macOS, either a single choice or multiple choices. For example, in macOS Keynote people can select only one segment in the alignment options control to align selected text. In contrast, people can choose multiple segments in the font attributes control to combine styles like bold, italics, and underline. The toolbar of a Keynote window also uses a segmented control to let people show and hide various editing panes within the main window area.

![](_page_0_Picture_14.jpeg)

In addition to representing the state of a single or multiple-choice selection, a segmented control can function as a set of buttons that perform actions without showing a selection state. For example, the Reply, Reply all, and Forward buttons in macOS Mail. For developer guidance, see *[isMomentary](https://developer.apple.com/documentation/UIKit/UISegmentedControl/isMomentary)* and *[NSSegmentedControl.SwitchTracking.momentary](https://developer.apple.com/documentation/AppKit/NSSegmentedControl/SwitchTracking/momentary)*.

## <span id="page-0-0"></span>**Best [practices](#page-0-0)**

**Use a segmented control to provide closely related choices that affect an object, state, or view.** For example, a segmented control in an inspector could let people choose one or more attributes to apply to a selection, or a segmented control in a toolbar could offer a set of actions to perform on the current view.

![](_page_1_Figure_1.jpeg)

In the iOS Health app, a segmented control provides a choice of time ranges for the activity graphs to display.

**Consider a segmented control when it's important to group functions together, or to clearly show their selection state.** Unlike other button styles, segmented controls preserve their grouping regardless of the view size or where they appear. This grouping can also help people understand at a glance which controls are currently selected.

**Keep control types consistent within a single segmented control.** Don't assign actions to segments in a control that otherwise represents selection state, and don't show a selection state for segments in a control that otherwise performs actions.

**Limit the number of segments in a control.** Too many segments can be hard to parse and timeconsuming to navigate. Aim for no more than about five to seven segments in a wide interface and no more than about five segments on iPhone.

**In general, keep segment size consistent.** When all segments have equal width, a segmented control feels balanced. To the extent possible, it's best to keep icon and title widths consistent too.

## **[Content](#page-1-0)**

**Prefer using either text or images — not a mix of both — in a single segmented control.** Although individual segments can contain text labels or images, mixing the two in a single control can lead to a disconnected and confusing interface.

**As much as possible, use content with a similar size in each segment.** Because all segments typically have equal width, it doesn't look good if content fills some segments but not others.

<span id="page-1-0"></span>**Use nouns or noun phrases for segment labels.** Write text that describes each segment and uses title-style [capitalization.](https://support.apple.com/guide/applestyleguide/c-apsgb744e4a3/web#apdca93e113f1d64) A segmented control that displays text labels doesn't need introductory text.

# **Platform [considerations](#page-1-1)**

<span id="page-1-1"></span>*Not supported in watchOS.*

## <span id="page-2-0"></span>**iOS, [iPadOS](#page-2-0)**

**Consider a segmented control to switch between closely related subviews.** A segmented control can be useful as a way to quickly switch between related subviews. For example, the segmented control in Calendar's New Event sheet switches between the subviews for creating a new event and a new reminder. For switching between completely separate sections of an app, use a tab [bar](https://developer.apple.com/design/human-interface-guidelines/tab-bars) instead.

![](_page_2_Figure_2.jpeg)

### **[macOS](#page-2-1)**

**Consider using introductory text to clarify the purpose of a segmented control.** When the control uses symbols or interface icons, you could also add a label below each segment to clarify its meaning. If your app includes tooltips, provide one for each segment in a segmented control.

<span id="page-2-1"></span>**Use a tab view in the main window area — instead of a segmented control — for view switching.** A tab [view](https://developer.apple.com/design/human-interface-guidelines/tab-views) supports efficient view switching and is similar in appearance to a [box](https://developer.apple.com/design/human-interface-guidelines/boxes) combined with a segmented control. Consider using a segmented control to help people switch views in a toolbar or inspector pane.

![](_page_3_Figure_0.jpeg)

**Consider supporting spring loading.** On a Mac equipped with a Magic Trackpad, spring loading lets people activate a segment by dragging selected items over it and force clicking without dropping the selected items. People can also continue dragging the items after a segment activates.

### **[tvOS](#page-3-0)**

**Consider using a split view instead of a segmented control on screens that perform content filtering.** People generally find it easy to navigate back and forth between content and filtering options using a split view. Depending on its placement, a segmented control may not be as easy to access.

<span id="page-3-0"></span>**Avoid putting other focusable elements close to segmented controls.** Segments become selected when focus moves to them, not when people click them. Carefully consider where you position a segmented control relative to other interface elements. If other focusable elements are too close, people might accidentally focus on them when attempting to switch between segments.

### **[visionOS](#page-3-1)**

<span id="page-3-1"></span>When people look at a segmented control that uses icons, the system displays a tooltip that contains the descriptive text you supply.

## <span id="page-4-0"></span>**[Resources](#page-4-0)**

#### <span id="page-4-2"></span>**[Related](#page-4-2)**

Split [views](https://developer.apple.com/design/human-interface-guidelines/split-views)

#### <span id="page-4-3"></span>**Developer [documentation](#page-4-3)**

*[segmented](https://developer.apple.com/documentation/SwiftUI/PickerStyle/segmented)* — SwiftUI

*[UISegmentedControl](https://developer.apple.com/documentation/UIKit/UISegmentedControl)* — UIKit

*[NSSegmentedControl](https://developer.apple.com/documentation/AppKit/NSSegmentedControl)* — AppKit

## **[Change](#page-4-1) log**

<span id="page-4-1"></span>**Date Changes**

June 21, 2023 Updated to include guidance for visionOS.