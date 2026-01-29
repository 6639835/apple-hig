# <span id="page-0-1"></span>**VoiceOver**

VoiceOver is a screen reader that lets people experience your app's interface without needing to see the screen.

![](_page_0_Picture_3.jpeg)

**Supported platforms**

![](_page_0_Picture_5.jpeg)

[VoiceOver](#page-0-1) [Descriptions](#page-0-0) [Navigation](#page-1-0) Platform [considerations](#page-2-0) [Resources](#page-3-0)

[Change](#page-3-1) log

By supporting VoiceOver, you help people who are blind or have low vision access information in your app and navigate its interface and content when they can't see the display.

VoiceOver is supported in apps and games built for Apple platforms. It's also supported in apps and games developed in Unity using Apple's Unity [plug-ins](https://github.com/apple/unityplugins). For related guidance, see [Accessibility.](https://developer.apple.com/design/human-interface-guidelines/accessibility)

## **[Descriptions](#page-0-0)**

You inform VoiceOver about your app's content by providing alternative text that explains your app's interface and the content it displays.

**Provide alternative labels for all key interface elements.** VoiceOver uses alternative labels (which aren't visible onscreen) to audibly describe your app's interface. System-provided controls have generic labels by default, but you should provide more descriptive labels that convey your app's functionality. Add labels to any custom elements your app defines. Be sure to keep your descriptions up-to-date as your app's interface and content change. For developer guidance, see [Accessibility](https://developer.apple.com/documentation/SwiftUI/View-Accessibility) modifiers.

<span id="page-0-0"></span>**Describe meaningful images.** If you don't describe key images in your app's content, people can't use VoiceOver to fully experience them within your app. Because VoiceOver helps people understand the interface surrounding images too, such as nearby captions, describe only the information the image itself conveys.

**Make charts and other infographics fully accessible.** Provide a concise description of each infographic that explains what it conveys. If people can interact with the infographic to get more or different information, make these interactions available to people using VoiceOver, too. The accessibility APIs offer ways to represent custom interactive elements so that assistive technologies can help people use them. For guidance, see [Charts.](https://developer.apple.com/design/Human-Interface-Guidelines/charts#Enhancing-the-accessibility-of-a-chart)

**Exclude purely decorative images from VoiceOver.** It's unnecessary to describe images that are decorative and don't convey useful or actionable information. Excluding these images shows respect for people's time and reduces cognitive load when they use VoiceOver. For developer guidance, see *[accessibilityHidden\(\\_:\)](https://developer.apple.com/documentation/SwiftUI/View/accessibilityHidden(_:))*, *[accessibilityElement](https://developer.apple.com/documentation/AppKit/NSAccessibility-c.protocol/accessibilityElement)*, and *[is](https://developer.apple.com/documentation/UIKit/UIAccessibilityElement/isAccessibilityElement) [AccessibilityElement](https://developer.apple.com/documentation/UIKit/UIAccessibilityElement/isAccessibilityElement)*.

## **[Navigation](#page-1-0)**

<span id="page-1-0"></span>**Use titles and headings to help people navigate your information hierarchy.** The title is the first information someone receives from an assistive technology when arriving on a page or screen in your app. Offer unique titles that succinctly describe each page's content and purpose. Likewise, use accurate section headings that help people build a mental model of each page's information hierarchy.

**Specify how elements are grouped, ordered, or linked.** Proximity, alignment, and other visible contextual cues help sighted people perceive the relationships between elements. Examine your app for places where relationships among elements are visual only. Then, describe these relationships to VoiceOver.

VoiceOver reads elements in the same order people read content in the their active language and locale. For example, in US English, this is top-to-bottom, left-to-right. In the ungrouped example below, VoiceOver describes each image before moving on to the captions. In the grouped example, VoiceOver describes each image with its respective caption.

![](_page_1_Picture_6.jpeg)

Ungrouped related elements make it hard for VoiceOver to accurately describe the UI.

![](_page_1_Picture_8.jpeg)

Grouped related elements help VoiceOver accurately describe the UI.

![](_page_1_Picture_10.jpeg)

![](_page_1_Picture_11.jpeg)

For developer guidance, see *[shouldGroupAccessibilityChildren](https://developer.apple.com/documentation/ObjectiveC/NSObject-swift.class/shouldGroupAccessibilityChildren)*.

**Inform VoiceOver when visible content or layout changes occur.** People may find an unexpected content or layout change confusing because it means their mental map of the content is no longer accurate. It's crucial to report visible changes so VoiceOver and other assistive technologies can help people update their understanding of the content. For developer guidance, see *[AccessibilityNotification](https://developer.apple.com/documentation/Accessibility/AccessibilityNotification)*.

**Support the VoiceOver rotor when possible.** People can use an interface element called the VoiceOver rotor to navigate a document or webpage by headings, links, and other content types. You can help people navigate content in your app by identifying these elements to the rotor. The rotor can also bring up the braille keyboard. For developer guidance, see *[Accessibility](https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry) [RotorEntry](https://developer.apple.com/documentation/SwiftUI/AccessibilityRotorEntry)* (SwiftUI), *[UIAccessibilityCustomRotor](https://developer.apple.com/documentation/UIKit/UIAccessibilityCustomRotor)* (UIKit), and *[NSAccessibility](https://developer.apple.com/documentation/AppKit/NSAccessibilityCustomRotor) [CustomRotor](https://developer.apple.com/documentation/AppKit/NSAccessibilityCustomRotor)* (AppKit).

# <span id="page-2-0"></span>**Platform [considerations](#page-2-0)**

*No additional considerations for iOS, iPadOS, macOS, tvOS, or watchOS.*

### **[visionOS](#page-2-1)**

<span id="page-2-1"></span>**Be mindful that custom gestures aren't always accessible.** When VoiceOver is turned on in visionOS, apps and games that define custom gestures don't receive hand input by default. This ensures people can explore the interface using their voice, without an app responding to hand input at the same time. A person can opt out of this behavior by enabling Direct Gesture mode, which disables standard VoiceOver gestures and lets apps process hand input directly. For developer guidance, see Improving [accessibility](https://developer.apple.com/documentation/visionOS/improving-accessibility-support-in-your-app) support in your visionOS app.

## <span id="page-3-0"></span>**[Resources](#page-3-0)**

#### <span id="page-3-2"></span>**[Related](#page-3-2)**

[Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)

[Inclusion](https://developer.apple.com/design/human-interface-guidelines/inclusion)

#### **Developer [documentation](#page-3-3)**

<span id="page-3-3"></span>[Accessibility](https://developer.apple.com/documentation/Accessibility)

[VoiceOver](https://developer.apple.com/documentation/Accessibility/voiceover)

[Supporting](https://developer.apple.com/documentation/UIKit/supporting-voiceover-in-your-app) VoiceOver in your app

#### **[Videos](#page-3-4)**

<span id="page-3-4"></span>![](_page_3_Picture_9.jpeg)

![](_page_3_Picture_10.jpeg)

![](_page_3_Picture_11.jpeg)

**Tailor the VoiceOver [experience](https://developer.apple.com/videos/play/wwdc2021/10121) in your data-rich apps**

![](_page_3_Picture_13.jpeg)

**[VoiceOver](https://developer.apple.com/videos/play/wwdc2020/10116) efficiency with custom rotors**

# **[Change](#page-3-1) log**

**Date Changes**

<span id="page-3-1"></span>March 7, 2025 New page.