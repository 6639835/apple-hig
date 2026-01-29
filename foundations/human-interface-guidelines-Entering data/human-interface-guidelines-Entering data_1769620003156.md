# <span id="page-0-1"></span>**Entering data**

When you need information from people, design ways that make it easy for them to provide it without making mistakes.

![](_page_0_Picture_3.jpeg)

**Supported platforms**

![](_page_0_Picture_5.jpeg)

[Entering](#page-0-1) data Best [practices](#page-0-0) Platform [considerations](#page-1-0) [Resources](#page-2-0)

[Change](#page-2-1) log

Entering information can be a tedious process regardless of the interaction methods people use. Improve the experience by:

- Pre-gathering as much information as possible to minimize the amount of data that people need to supply
- Supporting all available input methods so people can choose the method that works for them

## **Best [practices](#page-0-0)**

**Get information from the system whenever possible.** Don't ask people to enter information that you can gather automatically — such as from settings — or by getting their permission, such as their location or calendar information.

**Be clear about the data you need.** For example, you might display a prompt in a text field — like "username@company.com" — or provide an introductory label that describes the information, like "Email." You can also prefill fields with reasonable default values, which can minimize decision making and speed data entry.

<span id="page-0-0"></span>**Use a secure text-entry field when appropriate.** If your app or game needs sensitive data, use a field that obscures people's input as they enter it, typically by displaying a small filled circle symbol for each character. For developer guidance, see *[SecureField](https://developer.apple.com/documentation/SwiftUI/SecureField)*. In tvOS, you can also configure a digit [entry](https://developer.apple.com/design/human-interface-guidelines/digit-entry-views) view to obscure the numerals people enter (for developer guidance, see *[isSecureDigitEntry](https://developer.apple.com/documentation/TVUIKit/TVDigitEntryViewController/isSecureDigitEntry)*). When you use the system-provided text field in visionOS, the system shows the entered data to the wearer, but not to anyone else; for example, a secure text field automatically blurs when people use AirPlay to stream their content.

**Never prepopulate a password field.** Always ask people to enter their password or use biometric or keychain authentication. For guidance, see [Managing](https://developer.apple.com/design/human-interface-guidelines/managing-accounts) accounts.

**When possible, offer choices instead of requiring text entry.** It's usually easier and more efficient to choose from lists of options than to type information, even when a keyboard is conveniently available. When it makes sense, consider using a picker, menu, or other selection component to give people an easy way to provide the information you need.

**As much as possible, let people provide data by dragging and dropping it or by pasting it.** Supporting these interactions can ease data entry and make your experience feel more integrated with the rest of the system.

**Dynamically validate field values.** People can get frustrated when they have to go back and correct mistakes after filling out a lengthy form. When you verify values as soon as people enter them — and provide feedback as soon as you detect a problem — you give them the opportunity to correct errors right away. For numeric data in particular, consider using a number formatter, which automatically configures a text field to accept only numeric values. You can also configure a formatter to display the value in a specific way, such as with a certain number of decimal places, as a percentage, or as currency.

**When data entry is necessary, make sure people understand that they must provide the required data before they can proceed.** For example, if you include a Next or Continue button after a set of text fields, make the button available only after people enter the data you require.

## **Platform [considerations](#page-1-0)**

*No additional considerations for iOS, iPadOS, tvOS, visionOS, or watchOS.*

### <span id="page-1-0"></span>**[macOS](#page-1-1)**

<span id="page-1-1"></span>**Consider using an expansion tooltip to show the full version of clipped or truncated text in a field.** An *expansion tooltip* behaves like a regular tooltip, appearing when the pointer rests on top of a field. Apps running in macOS — including iOS and iPadOS apps running on a Mac — can use an expansion tooltip to help people view the complete data they entered when a text field is too small to display it. For guidance, see Offering help > macOS, [visionOS.](https://developer.apple.com/design/human-interface-guidelines/offering-help#macOS-visionOS)

## <span id="page-2-0"></span>**[Resources](#page-2-0)**

#### <span id="page-2-2"></span>**[Related](#page-2-2)**

Text [fields](https://developer.apple.com/design/human-interface-guidelines/text-fields)

Virtual [keyboards](https://developer.apple.com/design/human-interface-guidelines/virtual-keyboards)

[Keyboards](https://developer.apple.com/design/human-interface-guidelines/keyboards)

#### **Developer [documentation](#page-2-3)**

<span id="page-2-3"></span>Input [events](https://developer.apple.com/documentation/SwiftUI/Input-events) — SwiftUI

#### **[Videos](#page-2-4)**

<span id="page-2-4"></span>![](_page_2_Picture_8.jpeg)

**[What's](https://developer.apple.com/videos/play/wwdc2021/10059) new in UIKit**

## **[Change](#page-2-1) log**

**Date Changes**

<span id="page-2-1"></span>

June 21, 2023 Updated to include guidance for visionOS.