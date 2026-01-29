# <span id="page-0-1"></span>**Tab views**

A tab view presents multiple mutually exclusive panes of content in the same area, which people can switch between using a tabbed control.

![](_page_0_Picture_3.jpeg)

#### **Supported platforms**

![](_page_0_Picture_5.jpeg)

Tab [views](#page-0-1) Best [practices](#page-0-0) [Anatomy](#page-1-0) Platform [considerations](#page-1-1) [Resources](#page-3-0)

[Change](#page-3-1) log

# **Best [practices](#page-0-0)**

**Use a tab view to present closely related areas of content.** The appearance of a tab view provides a strong visual indication of enclosure. People expect each tab to display content that is in some way similar or related to the content in the other tabs.

**Make sure the controls within a pane affect content only in the same pane.** Panes are mutually exclusive, so ensure they're fully self-contained.

<span id="page-0-0"></span>**Provide a label for each tab that describes the contents of its pane.** A good label helps people predict the contents of a pane before clicking or tapping its tab. In general, use nouns or short noun phrases for tab labels. A verb or short verb phrase may make sense in some contexts. Use title-style capitalization for tab labels.

**Avoid using a pop-up button to switch between tabs.** A tabbed control is efficient because it requires a single click or tap to make a selection, whereas a pop-up button requires two. A tabbed control also presents all choices onscreen at the same time, whereas people must click a pop-up button to see its choices. Note that a pop-up button can be a reasonable alternative in cases where there are too many panes of content to reasonably display with tabs.

**Avoid providing more than six tabs in a tab view.** Having more than six tabs can be overwhelming and create layout issues. If you need to present six or more tabs, consider another way to implement the interface. For example, you could instead present each tab as a view option in a pop-up button menu.

# <span id="page-1-0"></span>**[Anatomy](#page-1-0)**

The tabbed control appears on the top edge of the content area. You can choose to hide the control, which is appropriate for an app that switches between panes programmatically.

![](_page_1_Picture_3.jpeg)

When you hide the tabbed control, the content area can be borderless, bezeled, or bordered with a line. A borderless view can be solid or transparent.

**In general, inset a tab view by leaving a margin of window-body area on all sides of a tab view.** This layout looks clean and leaves room for additional controls that aren't directly related to the contents of the tab view. You can extend a tab view to meet the window edges, but this layout is unusual.

# **Platform [considerations](#page-1-1)**

*Not supported in iOS, iPadOS, tvOS, or visionOS.*

### **iOS, [iPadOS](#page-1-2)**

<span id="page-1-1"></span>For similar functionality, consider using a [segmented](https://developer.apple.com/design/human-interface-guidelines/segmented-controls) control instead.

#### **[watchOS](#page-1-3)**

<span id="page-1-3"></span><span id="page-1-2"></span>watchOS displays tab views using page [controls.](https://developer.apple.com/design/human-interface-guidelines/components/presentation/page-controls) For developer guidance, see *[TabView](https://developer.apple.com/documentation/SwiftUI/TabView)* and *[verticalPage](https://developer.apple.com/documentation/SwiftUI/TabViewStyle/verticalPage)*.

![](_page_2_Picture_0.jpeg)

## <span id="page-3-0"></span>**[Resources](#page-3-0)**

#### <span id="page-3-2"></span>**[Related](#page-3-2)**

Tab [bars](https://developer.apple.com/design/human-interface-guidelines/tab-bars)

[Segmented](https://developer.apple.com/design/human-interface-guidelines/segmented-controls) controls

#### **Developer [documentation](#page-3-3)**

<span id="page-3-3"></span>*[TabView](https://developer.apple.com/documentation/SwiftUI/TabView)* — SwiftUI

*[NSTabView](https://developer.apple.com/documentation/AppKit/NSTabView)* — AppKit

# **[Change](#page-3-1) log**

<span id="page-3-1"></span>**Date Changes**

June 5, 2023 Added guidance for using tab views in watchOS.