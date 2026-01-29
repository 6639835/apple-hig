<span id="page-0-1"></span>**December 16, 2025** Updated guidance for Liquid Glass.

# **Color**

Judicious use of color can enhance communication, evoke your brand, provide visual continuity, communicate status and feedback, and help people understand information.

![](_page_0_Picture_4.jpeg)

The system defines colors that look good on various backgrounds and appearance modes, and can automatically adapt to vibrancy and accessibility settings. Using system colors is a convenient way to make your experience feel at home on the device.

You may also want to use custom colors to enhance the visual experience of your app or game and express its unique personality. The following guidelines can help you use color in ways that people appreciate, regardless of whether you use system-defined or custom colors.

## **Best [practices](#page-0-0)**

**Avoid using the same color to mean different things.** Use color consistently throughout your interface, especially when you use it to help communicate information like status or interactivity. For example, if you use your brand color to indicate that a borderless button is interactive, using the same or similar color to stylize noninteractive text is confusing.

<span id="page-0-0"></span>**Make sure all your app's colors work well in light, dark, and increased contrast contexts.** iOS, iPadOS, macOS, and tvOS offer both light and [dark](https://developer.apple.com/design/human-interface-guidelines/dark-mode) appearance settings. [System](#page-2-0) colors vary subtly depending on the system appearance, adjusting to ensure proper color differentiation and

#### **Supported platforms**

![](_page_0_Picture_11.jpeg)

[Color](#page-0-1) Best [practices](#page-0-0) [Inclusive](#page-2-1) color [System](#page-2-0) colors [Liquid](#page-3-0) Glass color Color [management](#page-4-0) Platform [considerations](#page-4-1) [Specifications](#page-7-0) [Resources](#page-10-0) [Change](#page-10-1) log

contrast for text, symbols, and other elements. With the Increase Contrast setting turned on, the color differences become far more apparent. When possible, use system colors, which already define variants for all these contexts. If you define a custom color, make sure to supply light and dark variants, and an increased contrast option for each variant that provides a significantly higher amount of visual differentiation. Even if your app ships in a single appearance mode, provide both light and dark colors to support Liquid Glass adaptivity in these contexts.

![](_page_1_Picture_1.jpeg)

![](_page_1_Picture_2.jpeg)

Default (light) Increased contrast (light)

![](_page_1_Picture_5.jpeg)

![](_page_1_Picture_7.jpeg)

Default (dark) Increased contrast (dark)

**Test your app's color scheme under a variety of lighting conditions.** Colors can look different when you view your app outside on a sunny day or in dim light. In bright surroundings, colors look darker and more muted. In dark environments, colors appear bright and saturated. In visionOS, colors can look different depending on the colors of a wall or object in a person's physical surroundings and how it reflects light. Adjust app colors to provide an optimal viewing experience in the majority of use cases.

**Test your app on different devices.** For example, the True Tone display — available on certain iPhone, iPad, and Mac models — uses ambient light sensors to automatically adjust the white point of the display to adapt to the lighting conditions of the current environment. Apps that primarily support reading, photos, video, and gaming can strengthen or weaken this effect by specifying a white point adaptivity style (for developer guidance, see *[UIWhitePoint](https://developer.apple.com/documentation/BundleResources/Information-Property-List/UIWhitePointAdaptivityStyle) [AdaptivityStyle](https://developer.apple.com/documentation/BundleResources/Information-Property-List/UIWhitePointAdaptivityStyle)*). Test tvOS apps on multiple brands of HD and 4K TVs, and with different display settings. You can also test the appearance of your app using different color profiles on a Mac — such as P3 and Standard RGB (sRGB) — by choosing a profile in System Settings > Displays. For guidance, see Color [management](#page-4-0).

**Consider how artwork and translucency affect nearby colors.** Variations in artwork sometimes warrant changes to nearby colors to maintain visual continuity and prevent interface elements

from becoming overpowering or underwhelming. Maps, for example, displays a light color scheme when in map mode but switches to a dark color scheme when in satellite mode. Colors can also appear different when placed behind or applied to a translucent element like a toolbar.

**If your app lets people choose colors, prefer system-provided color controls where available.** Using built-in color pickers provides a consistent user experience, in addition to letting people save a set of colors they can access from any app. For developer guidance, see *[ColorPicker](https://developer.apple.com/documentation/SwiftUI/ColorPicker)*.

### <span id="page-2-1"></span>**[Inclusive](#page-2-1) color**

**Avoid relying solely on color to differentiate between objects, indicate interactivity, or communicate essential information.** When you use color to convey information, be sure to provide the same information in alternative ways so people with color blindness or other visual disabilities can understand it. For example, you can use text labels or glyph shapes to identify objects or states.

**Avoid using colors that make it hard to perceive content in your app.** For example, insufficient contrast can cause icons and text to blend with the background and make content hard to read, and people who are color blind might not be able to distinguish some color combinations. For guidance, see [Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility).

**Consider how the colors you use might be perceived in other countries and cultures.** For example, red communicates danger in some cultures, but has positive connotations in other cultures. Make sure the colors in your app send the message you intend.

![](_page_2_Figure_6.jpeg)

Green indicates a positive trend in the Stocks app in English.

![](_page_2_Figure_8.jpeg)

Red indicates a positive trend in the Stocks app in Chinese.

### **[System](#page-2-0) colors**

**Avoid hard-coding system color values in your app.** Documented color values are for your reference during the app design process. The actual color values may fluctuate from release to release, based on a variety of environmental variables. Use APIs like *[Color](https://developer.apple.com/documentation/SwiftUI/Color)* to apply system colors.

iOS, iPadOS, macOS, and visionOS also define sets of *dynamic system colors* that match the color schemes of standard UI components and automatically adapt to both light and dark contexts. Each dynamic color is semantically defined by its purpose, rather than its appearance or color values. For example, some colors represent view backgrounds at different levels of hierarchy and other colors represent foreground content, such as labels, links, and separators.

<span id="page-2-0"></span>**Avoid redefining the semantic meanings of dynamic system colors.** To ensure a consistent experience and ensure your interface looks great when the appearance of the platform changes, use dynamic system colors as intended. For example, don't use the [separator](https://developer.apple.com/documentation/uikit/uicolor/separator) color as a text color, or [secondary](https://developer.apple.com/documentation/uikit/uicolor/secondarylabel) text label color as a background color.

## <span id="page-3-0"></span>**[Liquid](#page-3-0) Glass color**

By default, [Liquid](https://developer.apple.com/design/human-interface-guidelines/materials#Liquid-Glass) Glass has no inherent color, and instead takes on colors from the content directly behind it. You can apply color to some Liquid Glass elements, giving them the appearance of colored or stained glass. This is useful for drawing emphasis to a specific control, like a primary call to action, and is the approach the system uses for prominent button styling. Symbols or text labels on Liquid Glass controls can also have color.

Controls can use color in the Liquid Glass background, like in a primary action button.

Symbols and text that appear on Liquid Glass can have color, like in a selected tab bar item.

By default, Liquid Glass picks up the color from the content layer behind it.

For smaller elements like toolbars and tab bars, the system can adapt Liquid Glass between a light and dark appearance in response to the underlying content. By default, symbols and text on these elements follow a monochromatic color scheme, becoming darker when the underlying content is light, and lighter when it's dark. Liquid Glass appears more opaque in larger elements like sidebars to preserve legibility over complex backgrounds and accommodate richer content on the material's surface.

**Apply color sparingly to the Liquid Glass material, and to symbols or text on the material.** If you apply color, reserve it for elements that truly benefit from emphasis, such as status indicators or primary actions. To emphasize primary actions, apply color to the background rather than to symbols or text. For example, the system applies the app accent color to the background in prominent buttons — such as the Done button — to draw attention and elevate their visual prominence. Refrain from adding color to the background of multiple controls.

![](_page_3_Picture_7.jpeg)

**Avoid using similar colors in control labels if your app has a colorful background.** While color can make apps more visually appealing, playful, or reflective of your brand, too much color can be overwhelming and make control labels more difficult to read. If your app features colorful backgrounds or visually rich content, prefer a monochromatic appearance for toolbars and tab bars, or choose an accent color with sufficient visual differentiation. By contrast, in apps with primarily monochromatic content or backgrounds, choosing your brand color as the app accent color can be an effective way to tailor your app experience and reflect your company's identity.

**Be aware of the placement of color in the content layer.** Make sure your interface maintains sufficient contrast by avoiding overlap of similar colors in the content layer and controls when possible. Although colorful content might intermittently scroll underneath controls, make sure its default or resting state — like the top of a screen of scrollable content — maintains clear legibility.

### <span id="page-4-0"></span>**Color [management](#page-4-0)**

A *color space* represents the colors in a *color model* like RGB or CMYK. Common color spaces sometimes called *gamuts* — are sRGB and Display P3.

A *color profile* describes the colors in a color space using, for example, mathematical formulas or tables of data that map colors to numerical representations. An image embeds its color profile so that a device can interpret the image's colors correctly and reproduce them on a display.

**Apply color profiles to your images.** Color profiles help ensure that your app's colors appear as intended on different displays. The sRGB color space produces accurate colors on most displays.

**Use wide color to enhance the visual experience on compatible displays.** Wide color displays support a P3 color space, which can produce richer, more saturated colors than sRGB. As a result, photos and videos that use wide color are more lifelike, and visual data and status indicators that use wide color can be more meaningful. When appropriate, use the Display P3 color profile at 16 bits per pixel (per channel) and export images in PNG format. Note that you need to use a wide color display to design wide color images and select P3 colors.

**Provide color space–specific image and color variations if necessary.** In general, P3 colors and images appear fine on sRGB displays. Occasionally, it may be hard to distinguish two very similar P3 colors when viewing them on an sRGB display. Gradients that use P3 colors can also sometimes appear clipped on sRGB displays. To avoid these issues and to ensure visual fidelity on both wide color and sRGB displays, you can use the asset catalog of your Xcode project to provide different versions of images and colors for each color space.

### **Platform [considerations](#page-4-1)**

### **iOS, [iPadOS](#page-4-2)**

<span id="page-4-1"></span>iOS defines two sets of dynamic background colors — *system* and *grouped* — each of which contains primary, secondary, and tertiary variants that help you convey a hierarchy of information. In general, use the grouped background colors (*[systemGroupedBackground](https://developer.apple.com/documentation/UIKit/UIColor/systemGroupedBackground)*, *[secondarySystemGroupedBackground](https://developer.apple.com/documentation/UIKit/UIColor/secondarySystemGroupedBackground)*, and *[tertiarySystemGroupedBackground](https://developer.apple.com/documentation/UIKit/UIColor/tertiarySystemGroupedBackground)*) when you have a grouped table view; otherwise, use the system set of background colors (*[systemBackground](https://developer.apple.com/documentation/UIKit/UIColor/systemBackground)*, *[secondarySystemBackground](https://developer.apple.com/documentation/UIKit/UIColor/secondarySystemBackground)*, and *[tertiarySystem](https://developer.apple.com/documentation/UIKit/UIColor/tertiarySystemBackground) [Background](https://developer.apple.com/documentation/UIKit/UIColor/tertiarySystemBackground)*).

<span id="page-4-2"></span>With both sets of background colors, you generally use the variants to indicate hierarchy in the following ways:

- Primary for the overall view
- Secondary for grouping content or elements within the overall view
- Tertiary for grouping content or elements within secondary elements

For foreground content, iOS defines the following dynamic colors:

| Color                                                                 | Use for…                                       | UIKit API<br>label |  |
|-----------------------------------------------------------------------|------------------------------------------------|--------------------|--|
| Label                                                                 | A text label that contains primary<br>content. |                    |  |
| A text label that contains sec‐<br>Secondary label<br>ondary content. |                                                | secondaryLabel     |  |

| Color            | Use for…                                                                | UIKit API       |  |
|------------------|-------------------------------------------------------------------------|-----------------|--|
| Tertiary label   | A text label that contains tertiary<br>content.                         | tertiaryLabel   |  |
| Quaternary label | A text label that contains quater‐<br>nary content.                     | quaternaryLabel |  |
| Placeholder text | Placeholder text in controls or text<br>views.                          | placeholderText |  |
| Separator        | A separator that allows some un‐<br>derlying content to be visible.     | separator       |  |
| Opaque separator | A separator that doesn't allow any<br>underlying content to be visible. | opaqueSeparator |  |
| Link             | Text that functions as a link.                                          | link            |  |

### **[macOS](#page-5-0)**

macOS defines the following dynamic system colors (you can also view them in the Developer palette of the standard Color panel):

<span id="page-5-0"></span>

| Color                                    | Use for…                                                                                                                | AppKit API                             |  |
|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|----------------------------------------|--|
| Alternate selected control text<br>color | The text on a selected surface in a<br>list or table.                                                                   | alternateSelectedControl<br>TextColor  |  |
| Alternating content background<br>colors | The backgrounds of alternating<br>rows or columns in a list, table, or<br>collection view.                              | alternatingContent<br>BackgroundColors |  |
| Control accent                           | The accent color people select in<br>System Settings.                                                                   | controlAccentColor                     |  |
| Control background color                 | The background of a large inter‐<br>face element, such as a browser or<br>table.                                        | controlBackgroundColor                 |  |
| Control color                            | The surface of a control.                                                                                               | controlColor                           |  |
| Control text color                       | The text of a control that is<br>available.                                                                             | controlTextColor                       |  |
| Current control tint                     | The system-defined control tint.                                                                                        | currentControlTint                     |  |
| Unavailable control text color           | The text of a control that's<br>unavailable.                                                                            | disabledControlTextColor               |  |
| Find highlight color                     | The color of a find indicator.                                                                                          | findHighlightColor                     |  |
| Grid color                               | The gridlines of an interface ele‐<br>ment, such as a table.                                                            | gridColor                              |  |
| Header text color                        | The text of a header cell in a table.                                                                                   | headerTextColor                        |  |
| Highlight color                          | The virtual light source onscreen.                                                                                      | highlightColor                         |  |
| Keyboard focus indicator color           | The ring that appears around the<br>currently focused control when us‐<br>ing the keyboard for interface<br>navigation. | keyboardFocusIndicator<br>Color        |  |

| Color                                             | Use for…                                                                                                                                              | AppKit API                                     |  |
|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------|--|
| Label color                                       | The text of a label containing pri‐<br>mary content.                                                                                                  | labelColor                                     |  |
| Link color                                        | A link to other content.                                                                                                                              | linkColor                                      |  |
| Placeholder text color                            | A placeholder string in a control or<br>text view.                                                                                                    | placeholderTextColor                           |  |
| Quaternary label color                            | The text of a label of lesser impor‐<br>tance than a tertiary label, such as<br>watermark text.                                                       | quaternaryLabelColor                           |  |
| Secondary label color                             | The text of a label of lesser impor‐<br>tance than a primary label, such as<br>a label used to represent a sub‐<br>heading or additional information. | secondaryLabelColor                            |  |
| Selected content background color                 | The background for selected con‐<br>tent in a key window or view.                                                                                     | selectedContentBackground<br>Color             |  |
| Selected control color                            | The surface of a selected control.                                                                                                                    | selectedControlColor                           |  |
| Selected control text color                       | The text of a selected control.                                                                                                                       | selectedControlTextColor                       |  |
| Selected menu item text color                     | The text of a selected menu.                                                                                                                          | selectedMenuItemTextColor                      |  |
| Selected text background color                    | The background of selected text.                                                                                                                      | selectedTextBackground<br>Color                |  |
| Selected text color                               | The color for selected text.                                                                                                                          | selectedTextColor                              |  |
| Separator color                                   | A separator between different sec‐<br>tions of content.                                                                                               | separatorColor                                 |  |
| Shadow color                                      | The virtual shadow cast by a raised<br>object onscreen.                                                                                               | shadowColor                                    |  |
| Tertiary label color                              | The text of a label of lesser impor‐<br>tance than a secondary label.                                                                                 | tertiaryLabelColor                             |  |
| Text background color                             | The background color behind text.                                                                                                                     | textBackgroundColor                            |  |
| Text color                                        | The text in a document.                                                                                                                               | textColor                                      |  |
| Under page background color                       | The background behind a docu‐<br>ment's content.                                                                                                      | underPageBackgroundColor                       |  |
| Unemphasized selected content<br>background color | The selected content in a non-key<br>window or view.                                                                                                  | unemphasizedSelected<br>ContentBackgroundColor |  |
| Unemphasized selected text back‐<br>ground color  | A background for selected text in a<br>non-key window or view.                                                                                        | unemphasizedSelectedText<br>BackgroundColor    |  |
| Unemphasized selected text color                  | Selected text in a non-key window<br>or view.                                                                                                         | unemphasizedSelectedText<br>Color              |  |
| Window background color                           | The background of a window.                                                                                                                           | windowBackgroundColor                          |  |
| Window frame text color                           | The text in the window's title bar<br>area.                                                                                                           | windowFrameTextColor                           |  |

#### **App [accent](#page-6-0) colors**

<span id="page-6-0"></span>Beginning in macOS 11, you can specify an *accent color* to customize the appearance of your app's buttons, selection highlighting, and sidebar icons. The system applies your accent color when the current value in General > Accent color settings is *multicolor*.

If people set their accent color setting to a value other than multicolor, the system applies their chosen color to the relevant items throughout your app, replacing your accent color. The exception is a sidebar icon that uses a fixed color you specify. Because a fixed-color sidebar icon uses a specific color to provide meaning, the system doesn't override its color when people change the value of accent color settings. For guidance, see [Sidebars](https://developer.apple.com/design/human-interface-guidelines/sidebars).

### **[tvOS](#page-7-1)**

<span id="page-7-1"></span>**Consider choosing a limited color palette that coordinates with your app logo.** Subtle use of color can help you communicate your brand while deferring to the content.

**Avoid using only color to indicate focus.** Subtle scaling and responsive animation are the primary ways to denote interactivity when an element is in focus.

### **[visionOS](#page-7-2)**

<span id="page-7-2"></span>**Use color sparingly, especially on glass.** Standard visionOS windows typically use the systemdefined glass [material,](https://developer.apple.com/design/human-interface-guidelines/materials) which lets light and objects from people's physical surroundings and their space show through. Because the colors in these physical and virtual objects are visible through the glass, they can affect the legibility of colorful app content in the window. Prefer using color in places where it can help call attention to important information or show the relationship between parts of the interface.

**Prefer using color in bold text and large areas.** Color in lightweight text or small areas can make them harder to see and understand.

**In a fully immersive experience, help people maintain visual comfort by keeping brightness levels balanced.** Although using high contrast can help direct people's attention to important content, it can also cause visual discomfort if people's eyes have adjusted to low light or darkness. Consider making content fully bright only when the rest of the visual context is also bright. For example, avoid displaying a bright object on a very dark or black background, especially if the object flashes or moves.

### **[watchOS](#page-7-3)**

**Use background color to support existing content or supply additional information.**

Background color can establish a sense of place and help people recognize key content. For example, in Activity, each infographic view for the Move, Exercise, and Stand Activity rings has a background that matches the color of the ring. Use background color when you have something to communicate, rather than as a solely visual flourish. Avoid using full-screen background color in views that are likely to remain onscreen for long periods of time, such as in a workout or audio-playing app.

<span id="page-7-3"></span>**Recognize that people might prefer graphic complications to use tinted mode instead of full color.** The system can use a single color that's based on the wearer's selected color in a graphic complication's images, gauges, and text. For guidance, see [Complications.](https://developer.apple.com/design/human-interface-guidelines/complications)

## **[Specifications](#page-7-0)**

### <span id="page-7-0"></span>**[System](#page-2-0) colors**

| Name   | SwiftUI API | Default (light) | Default (dark) | Increased con‐<br>trast (light) | Increased con‐<br>trast (dark) |
|--------|-------------|-----------------|----------------|---------------------------------|--------------------------------|
| Red    | red         |                 |                |                                 |                                |
| Orange | orange      |                 |                |                                 |                                |
| Yellow | yellow      |                 |                |                                 |                                |
| Green  | green       |                 |                |                                 |                                |
| Mint   | mint        |                 |                |                                 |                                |
| Teal   | teal        |                 |                |                                 |                                |
| Cyan   | cyan        |                 |                |                                 |                                |
| Blue   | blue        |                 |                |                                 |                                |
| Indigo | indigo      |                 |                |                                 |                                |
| Purple | purple      |                 |                |                                 |                                |
| Pink   | pink        |                 |                |                                 |                                |
| Brown  | brown       |                 |                |                                 |                                |

visionOS system colors use the default dark color values.

### **iOS, [iPadOS](#page-8-0) system gray colors**

<span id="page-8-0"></span>

| Name     | UIKit API   | Default (light) | Default (dark) | Increased con‐<br>trast (light) | Increased con‐<br>trast (dark) |
|----------|-------------|-----------------|----------------|---------------------------------|--------------------------------|
| Gray     | systemGray  |                 |                |                                 |                                |
| Gray (2) | systemGray2 |                 |                |                                 |                                |
| Gray (3) | systemGray3 |                 |                |                                 |                                |
| Gray (4) | systemGray4 |                 |                |                                 |                                |

| Name     | UIKit API   | Default (light) | Default (dark) | Increased con‐<br>trast (light) | Increased con‐<br>trast (dark) |
|----------|-------------|-----------------|----------------|---------------------------------|--------------------------------|
| Gray (5) | systemGray5 |                 |                |                                 |                                |
| Gray (6) | systemGray6 |                 |                |                                 |                                |

In SwiftUI, the equivalent of *systemGray* is *[gray](https://developer.apple.com/documentation/SwiftUI/Color/gray)*.

### <span id="page-10-0"></span>**[Resources](#page-10-0)**

#### <span id="page-10-2"></span>**[Related](#page-10-2)**

Dark [Mode](https://developer.apple.com/design/human-interface-guidelines/dark-mode)

[Accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)

[Materials](https://developer.apple.com/design/human-interface-guidelines/materials)

Apple Design [Resources](https://developer.apple.com/design/resources/)

#### **Developer [documentation](#page-10-3)**

<span id="page-10-3"></span>*[Color](https://developer.apple.com/documentation/SwiftUI/Color)* — SwiftUI

*[UIColor](https://developer.apple.com/documentation/UIKit/UIColor)* — UIKit

[Color](https://developer.apple.com/documentation/AppKit/color) — AppKit

#### **[Videos](#page-10-4)**

<span id="page-10-4"></span>![](_page_10_Picture_11.jpeg)

**Meet [Liquid](https://developer.apple.com/videos/play/wwdc2025/219) Glass**

### **[Change](#page-10-1) log**

<span id="page-10-1"></span>

| Date               | Changes                                                                                                                                   |  |  |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------|--|--|
| December 16, 2025  | Updated guidance for Liquid Glass.                                                                                                        |  |  |
| June 9, 2025       | Updated system color values, and added guidance for<br>Liquid Glass.                                                                      |  |  |
| February 2, 2024   | Distinguished UIKit and SwiftUI gray colors in iOS and<br>iPadOS, and added guidance for balancing brightness<br>levels in visionOS apps. |  |  |
| September 12, 2023 | Enhanced guidance for using background color in<br>watchOS views, and added color swatches for tvOS.                                      |  |  |
| June 21, 2023      | Updated to include guidance for visionOS.                                                                                                 |  |  |
| June 5, 2023       | Updated guidance for using background color in<br>watchOS.                                                                                |  |  |
| December 19, 2022  | Corrected RGB values for system mint color (Dark<br>Mode) in iOS and iPadOS.                                                              |  |  |