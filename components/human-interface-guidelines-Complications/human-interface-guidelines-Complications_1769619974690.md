<span id="page-0-1"></span>**[Design](https://developer.apple.com/design/)** [Overview](https://developer.apple.com/design/) [What's](https://developer.apple.com/design/whats-new/) New Get [Started](https://developer.apple.com/design/get-started/) [Guidelines](https://developer.apple.com/design/human-interface-guidelines) [Resources](https://developer.apple.com/design/resources/)

# **Complications**

A complication displays timely, relevant information on the watch face, where people can view it each time they raise their wrist.

![](_page_0_Figure_3.jpeg)

**Supported platforms**

![](_page_0_Picture_5.jpeg)

#### [Complications](#page-0-1)

Best [practices](#page-0-0)

Visual [design](#page-1-0)

[Circular](#page-2-0)

[Corner](#page-4-0)

[Inline](#page-5-0)

[Rectangular](#page-5-1)

Legacy [templates](#page-6-0)

Platform [considerations](#page-9-0)

[Resources](#page-10-0)

[Change](#page-10-1) log

People often prefer apps that provide multiple, powerful complications, because it gives them quick ways to view the data they care about, even when they don't open the app.

Most watch faces can display at least one complication; some can display four or more.

Starting in watchOS 9, the system organizes complications (also known as *accessories*) into several families — like [circular](#page-2-0) and [inline](#page-5-0) — and defines some recommended layouts you can use to display your complication data. A watch face can specify the family it supports in each complication slot. Complications that work in earlier versions of watchOS can use the [legacy](#page-6-0) [templates,](#page-6-0) which define nongraphic complication styles that don't take on a wearer's selected color.

**Developer note**

Prefer using [WidgetKit](https://developer.apple.com/documentation/WidgetKit) to develop complications for watchOS 9 and later. For guidance, see Migrating ClockKit [complications](https://developer.apple.com/documentation/WidgetKit/Converting-A-ClockKit-App) to WidgetKit. To support earlier versions of watchOS, continue to implement the ClockKit complication data source protocol (see *[CLKComplicationDataSource](https://developer.apple.com/documentation/ClockKit/CLKComplicationDataSource)*).

### **Best [practices](#page-0-0)**

<span id="page-0-0"></span>**Identify essential, dynamic content that people want to view at a glance.** Although people can use a complication to quickly launch an app, the complication behavior they appreciate more is

the display of relevant information that always feels up to date. A static complication that doesn't display meaningful data may be less likely to remain in a prominent position on the watch face.

**Support all complication families when possible.** Supporting more families means that your complications are available on more watch faces. If you can't display useful information for a particular complication family, provide an image that represents your app — like your app icon that still lets people launch your app from the watch face.

**Consider creating multiple complications for each family.** Supporting multiple complications helps you take advantage of shareable watch faces and lets people configure a watch face that's centered on an app they love. For example, an app that helps people train for triathlons could offer three circular complications — one for each segment of the race — each of which deeplinks to the segment-specific area in the app. This app could also offer a shareable watch face that's preconfigured to include its swimming, biking, and running complications and to use its custom images and colors. When people choose this watch face, they don't have to do any configuration before they can start using it. For guidance, see [Watch](https://developer.apple.com/design/human-interface-guidelines/watch-faces) faces.

**Define a different deep link for each complication you support.** It works well when each complication opens your app to the most relevant area. If all the complications you support open the same area in your app, they can seem less useful.

**Keep privacy in mind.** With the Always-On Retina display, information on the watch face might be visible to people other than the wearer. Make sure you help people prevent potentially sensitive information from being visible to others. For guidance, see [Always](https://developer.apple.com/design/human-interface-guidelines/always-on) On.

**Carefully consider when to update data.** You provide a complication's data in the form of a timeline where each entry has a value that specifies the time at which to display your data on the watch face. Different data sets might require different time values. For example, a meeting app might display information about an upcoming meeting an hour before the meeting starts, but a weather app might display forecast information at the time those conditions are expected to occur. You can update the timeline a limited number of times each day, and the system stores a limited number of timeline entries for each app, so you need to choose times that enhance the usefulness of your data. For developer guidance, see Migrating ClockKit [complications](https://developer.apple.com/documentation/WidgetKit/Converting-A-ClockKit-App#Configure-your-timeline-provider) to [WidgetKit.](https://developer.apple.com/documentation/WidgetKit/Converting-A-ClockKit-App#Configure-your-timeline-provider)

### **Visual [design](#page-1-0)**

**Choose a ring or gauge style based on the data you need to display.** Many families support a ring or gauge layout that provides consistent ways to represent numerical values that can change over time. For example:

- The closed style can convey a value that's a percentage of a whole, such as for a battery gauge.
- <span id="page-1-0"></span>The open style works well when the minimum and maximum values are arbitrary — or don't represent a percentage of the whole — like for a speed indicator.
- Similar to the open style, the segmented style also displays values within an app-defined range, and can convey rapid value changes, such as in the Noise complication.

**Make sure images look good in tinted mode.** In tinted mode, the system applies a solid color to a complication's text, gauges, and images, and desaturates full-color images unless you provide tinted versions of them. For developer guidance, see *[WidgetRenderingMode](https://developer.apple.com/documentation/WidgetKit/WidgetRenderingMode)*. (If you're using legacy templates, tinted mode applies only to graphic complications.) To help your complications perform well in tinted mode:

Avoid using color as the only way to communicate important information. You want people to get the same information in tinted mode as they do in nontinted mode.

When necessary, provide an alternative tinted-mode version of a full-color image. If your fullcolor image doesn't look good when it's desaturated, you can supply a different version of the image for the system to use in tinted mode.

**Recognize that people might prefer to use tinted mode for complications, instead of viewing them in full color.** When people choose tinted mode, the system automatically desaturates your complication, converting it to grayscale and tinting its images, gauges, and text using a single color that's based on the wearer's selected color.

**When creating complication content, generally use line widths of two points or greater.** Thinner lines can be difficult to see at a glance, especially when the wearer is in motion. Use line weights that suit the size and complexity of the image.

**Provide a set of static placeholder images for each complication you support.** The system uses placeholder images when there's no other content to display for your complication's data. For example, when people first install your app, the system can display a static placeholder while it checks to see if your app can generate a localized placeholder to use instead. Placeholder images can also appear in the carousel from which people select complications. Note that complication image sizes vary per layout (and per legacy template) and the size of a placeholder image may not match the size of the actual image you supply for that complication. For developer guidance, see *[placeholder\(in:\)](https://developer.apple.com/documentation/WidgetKit/TimelineProvider/placeholder(in:))*.

### **[Circular](#page-2-0)**

Circular layouts can include text, gauges, and full-color images in circular areas on the Infograph and Infograph Modular watch faces. The circular family also defines extra-large layouts for displaying content on the X-Large watch face.

<span id="page-2-0"></span>![](_page_2_Picture_6.jpeg)

You can also add text to accompany a regular-size circular image, using a design that curves the text along the bezel of some watch faces, like Infograph. The text can fill nearly 180 degrees of the bezel before truncating.

#### Closed gauge image

As you design images for a regular-size circular complication, use the following values for guidance.

| Image        | 40mm               | 41mm           | 44mm               | 45mm/49mm          |
|--------------|--------------------|----------------|--------------------|--------------------|
| Image        | 42x42 pt (84x84 px | 44.5x44.5 pt   | 47x47 pt (94x94 px | 50x50 pt (100x100  |
|              | @2x)               | (89x89 px @2x) | @2x)               | px @2x)            |
| Closed gauge | 27x27 pt (54x54 px | 28.5x28.5 pt   | 31x31 pt (62x62 px | 32x32 pt (64x64 px |
|              | @2x)               | (57x57 px @2x) | @2x)               | @2x)               |

| Image            | 40mm               | 41mm                | 44mm               | 45mm/49mm          |
|------------------|--------------------|---------------------|--------------------|--------------------|
| Open gauge       | 11x11 pt (22x22 px | 11.5x11.5 pt (23x23 | 12x12 pt (24x24 px | 13x13 pt (26x26 px |
|                  | @2x)               | px @2x)             | @2x)               | @2x)               |
| Stack (not text) | 28x14 pt (56x28 px | 29.5x15 pt (59X30   | 31x16 pt (62x32px  | 33.5x16.5 pt       |
|                  | @2x)               | px @2x)             | @ 2x)              | (67x33 px @2x)     |

#### **Note**

The system applies a circular mask to each image.

A SwiftUI view that implements a regular-size circular complication uses the following default text values:

Style: Rounded

Weight: Medium

Text size: 12 pt (40mm), 12.5 pt (41mm), 13 pt (44mm), 14.5 pt (45mm/49mm)

If you want to design an oversized treatment of important information that can appear on the X-Large watch face — for example, the Contacts complication, which features a contact photo use the extra-large versions of the circular family's layouts. The following layouts let you display full-color images, text, and gauges in a large circular region that fills most of the X-Large watch face. Some of the text fields can support multicolor text.

| Closed gauge image | Closed gauge text | Open gauge image | Open gauge text |
|--------------------|-------------------|------------------|-----------------|
|                    |                   |                  |                 |
| Open gauge range   | Image             | Stack image      | Stack text      |

Use the following values for guidance as you create images for an extra-large circular complication.

| Image        | 40mm               | 41mm               | 44mm               | 45mm/49mm          |
|--------------|--------------------|--------------------|--------------------|--------------------|
| Image        | 120x120 pt         | 127x127 pt         | 132x132 pt         | 143x143 pt         |
|              | (240x240 px @2x)   | (254x254 px @2x)   | (264x264 px @2x)   | (286x286 px @2x)   |
| Open gauge   | 31x31 pt (62x62 px | 33x33 pt (66x66 px | 33x33 pt (66x66 px | 37x37 pt (74x74 px |
|              | @2x)               | @2x)               | @2x)               | @2x)               |
| Closed gauge | 77x77 pt (154x154  | 81.5x81.5 (163x163 | 87x87 pt (174x174  | 91.5x91.5 (183x183 |
|              | px @2x)            | px @2x)            | px @2x)            | px @2x)            |
| Stack        | 80x40 pt (160x80   | 85x42 (170x84 px   | 87x44 pt (174x88   | 95x48 pt (190x96   |
|              | px @2x)            | @2x)               | px @2x)            | px @2x )           |

#### **Note**

The system applies a circular mask to the circular, open-gauge, and closed-gauge images.

Use the following values to create no-content placeholder images for your circular-family complications.

| Layout      | 38mm | 40mm/42mm                         | 41mm                              | 44mm                              | 45mm/49mm                         |
|-------------|------|-----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|
| Circular    | –    | 42x42 pt<br>(84x84 px @2x)        | 44.5x44.5 pt<br>(89x89 px @2x)    | 47x47 pt<br>(94x94 px @2x)        | 50x50 pt<br>(100x100 px<br>@2x)   |
| Bezel       | –    | 42x42 pt<br>(84x84 px @2x)        | 44.5x44.5 pt<br>(89x89 px @2x)    | 47x47 pt<br>(94x94 px @2x)        | 50x50 pt<br>(100x100 px<br>@2x)   |
| Extra Large | –    | 120x120 pt<br>(240x240 px<br>@2x) | 127x127 pt<br>(254x254 px<br>@2x) | 132x132 pt<br>(264x264 px<br>@2x) | 143x143 pt<br>(286x286 px<br>@2x) |

A SwiftUI view that implements an extra-large circular layout uses the following default text values:

Style: Rounded

Weight: Medium

Text size: 34.5 pt (40mm), 36.5 pt (41mm), 36.5 pt (44mm), 41 pt (45mm/49mm)

### **[Corner](#page-4-0)**

<span id="page-4-0"></span>Corner layouts let you display full-color images, text, and gauges in the corners of the watch face, like Infograph. Some of the templates also support multicolor text.

| Circular image | Gauge image | Gauge text |
|----------------|-------------|------------|
|                |             |            |
|                |             |            |
| Stack text     | Text image  |            |

As you design images for a corner complication, use the following values for guidance.

| Image    | 40mm               | 41mm               | 44mm               | 45mm/49mm          |
|----------|--------------------|--------------------|--------------------|--------------------|
| Circular | 32x32 pt (64x64 px | 34x34 pt (68x68    | 36x36 pt (72x72 px | 38x38 pt (76x76 px |
|          | @2x)               | px @2x)            | @2x)               | @2x )              |
| Gauge    | 20x20 pt (40x40 px | 21x21 pt (42x42 px | 22x22 pt (44x44 px | 24x24 pt (48x48 px |
|          | @2x)               | @2x)               | @2x)               | @2x)               |
| Text     | 20x20 pt (40x40 px | 21x21 pt (42x42 px | 22x22 pt (44x44 px | 24x24 pt (48x48 px |
|          | @2x)               | @2x)               | @2x)               | @2x)               |

**Note**

The system applies a circular mask to each image.

Use the following values to create no-content placeholder images for your corner-family complications.

| 38mm | 40mm/42mm          | 41mm               | 44mm               | 45mm/49mm          |
|------|--------------------|--------------------|--------------------|--------------------|
| –    | 20x20 pt (40x40 px | 21x21 pt (42x42 px | 22x22 pt (44x44 px | 24x24 pt (48x48 px |
|      | @2x)               | @2x)               | @2x)               | @2x)               |

A SwiftUI view that implements a corner layout uses the following default text values:

Style: Rounded

Weight: Semibold

Text size: 10 pt (40mm), 10.5 pt (41mm), 11 pt (44mm), 12 pt (45mm/49mm)

## **[Inline](#page-5-0)**

<span id="page-5-0"></span>Inline layouts include utilitarian small and large layouts.

Utilitarian small layouts are intended to occupy a rectangular area in the corner of a watch face, such as the Chronograph and Simple watch faces. The content can include an image, interface icon, or a circular graph.

| Flat | Ring image | Ring text | Square |
|------|------------|-----------|--------|
|      |            |           |        |

As you design images for a utilitarian small layout, use the following values for guidance.

| Content | 38mm                            | 40mm/42mm                           | 41mm                              | 44mm           | 45mm/49mm                           |
|---------|---------------------------------|-------------------------------------|-----------------------------------|----------------|-------------------------------------|
| Flat    | 9-21x9 pt (18-<br>42x18 px @2x) | 10-22x10 pt<br>(20-44x20 px<br>@2x) | 10.5-23.5x21 pt<br>(21-47x21 @2x) | N/A            | 12-26x12 pt<br>(24-52x24 px<br>@2x) |
| Ring    | 14x14 pt                        | 14x14 pt                            | 15x15 pt                          | 16x16 pt       | 16.5x16.5 pt                        |
|         | (28x28 px @2x)                  | (28x28 px @2x)                      | (30x30 px @2x)                    | (32x32 px @2x) | (33x33 px @2x)                      |
| Square  | 20x20 pt                        | 22x22 pt                            | 23.5x23.5 pt                      | 25x25 pt       | 26x26 pt                            |
|         | (40x40 px @2x)                  | (44x44 px @2x)                      | (47x47 px @2x)                    | (50x50 px @2x) | (52x52 px @2x)                      |

The utilitarian large layout is primarily text-based, but also supports an interface icon placed on the leading side of the text. This layout spans the bottom of a watch face, like the Utility or Motion watch faces.

Large flat

As you design images for a utilitarian large layout, use the following values for guidance.

| Content | 38mm                            | 40mm/42mm                           | 41mm                                      | 44mm | 45mm/49mm                           |
|---------|---------------------------------|-------------------------------------|-------------------------------------------|------|-------------------------------------|
| Flat    | 9-21x9 pt (18-<br>42x18 px @2x) | 10-22x10 pt<br>(20-44x20 px<br>@2x) | 10.5-23.5x10.5<br>pt (21-47x21 px<br>@2x) | N/A  | 12-26x12 pt<br>(24-52x24 px<br>@2x) |

### <span id="page-5-1"></span>**[Rectangular](#page-5-1)**

Rectangular layouts can display full-color images, text, a gauge, and an optional title in a large rectangular region. Some of the text fields can support multicolor text.

The large rectangular region works well for showing details about a value or process that changes over time, because it provides room for information-rich charts, graphs, and diagrams. For example, the Heart Rate complication displays a graph of heart-rate values within a 24-hour period. The graph uses high-contrast white and red for the primary content and a lower-contrast gray for the graph lines and labels, making the data easy to understand at a glance.

Starting with watchOS 10, if you have created a rectangular layout for your watchOS app, the system may display it in the Smart Stack. You can optimize this presentation in a few ways:

- By supplying background color or content that communicates information or aids in recognition
- By using [intents](https://developer.apple.com/documentation/appintents/app-intents) to specify relevancy, and help ensure that your widget is displayed in the Smart Stack at times that are most appropriate and useful to people
- By creating a custom layout of your information that is optimized for the Smart Stack

For developer guidance, see *[WidgetFamily.accessoryRectangular](https://developer.apple.com/documentation/WidgetKit/WidgetFamily/accessoryRectangular)*. See [Widgets](https://developer.apple.com/design/human-interface-guidelines/widgets) for additional guidance on designing widgets for the Smart Stack.

Standard body Text gauge Large image

Use the following values for guidance as you create images for a rectangular layout.

| Content              | 40mm               | 41mm                | 44mm                | 45mm/49mm           |
|----------------------|--------------------|---------------------|---------------------|---------------------|
| Large image with ti‐ | 150x47 pt (300x94  | 159x50 pt (318x100  | 171x54 pt (342x108  | 178.5x56 pt         |
| tle *                | px @2x)            | px @2x)             | px @2x)             | (357x112 px @2x)    |
| Large image with‐    | 162x69 pt          | 171.5x73 pt         | 184x78 pt           | 193x82 pt           |
| out title *          | (324x138 px @2x)   | (343x146 px @2x)    | (368x156 px @2x)    | (386x164 px @2x)    |
| Standard body        | 12x12 pt (24x24 px | 12.5x12.5 pt (25x25 | 13.5x13.5 pt (27x27 | 14.5x14.5 pt (29x29 |
|                      | @2x)               | px @2x)             | px @2x)             | px @2x)             |
| Text gauge           | 12x12 pt (24x24 px | 12.5x12.5 pt (25x25 | 13.5x13.5 pt (27x27 | 14.5x14.5 pt (29x29 |
|                      | @2x)               | px @2x)             | px @2x)             | px @2x)             |

#### **Note**

Both large-image layouts automatically include a four-point corner radius.

A SwiftUI view that implements a rectangular layout uses the following default text values:

Style: Rounded

Weight: Medium

Text size: 16.5 pt (40mm), 17.5 pt (41mm), 18 pt (44mm), 19.5 pt (45mm/49mm)

# **Legacy [templates](#page-6-0)**

#### <span id="page-6-1"></span><span id="page-6-0"></span>**[Circular](#page-6-1) small**

Circular small templates display a small image or a few characters of text. They appear in the corner of the watch face (for example, in the Color watch face).

| Ring image  | Ring text   | Simple image |
|-------------|-------------|--------------|
|             |             |              |
| Simple text | Stack image | Stack text   |

As you design images for a circular small complication, use the following values for guidance.

| Image       | 38mm           | 40mm/42mm      | 41mm           | 44mm           | 45mm/49mm      |
|-------------|----------------|----------------|----------------|----------------|----------------|
| Ring        | 20x20 pt       | 22x22 pt       | 23.5x23.5 pt   | 24x24 pt       | 26x26 pt       |
|             | (40x40 px @2x) | (44x44 px @2x) | (47x47 px @2x) | (48x48 px @2x) | (52x52 px @2x) |
| Simple      | 16x16 pt       | 18x18 pt       | 19x19 pt       | 20x20 pt       | 21.5x21.5 pt   |
|             | (32x32 px @2x) | (36x36 px @2x) | (38x38 px @2x) | (40x40 px @2x) | (43x43 px @2x) |
| Stack       | 16x7 pt (32x14 | 17x8 pt (34x16 | 18x8.5 pt      | 19x9 pt (38x18 | 19x9.5 pt      |
|             | px @2x)        | px @2x)        | (36x17 px @2x) | px @2x)        | (38x19 px @2x) |
| Placeholder | 16x16 pt       | 18x18x pt      | 19x19 pt       | 20x20 pt       | 21.5x21.5 pt   |
|             | (32x32 px @2x) | (36x36 px @2x) | (38x38 px @2x) | (40x40 px @2x) | (43x43 px @2x) |

**Note**

In each stack measurement, the width value represents the maximum size.

#### **[Modular](#page-7-0) small**

Modular small templates display two stacked rows consisting of an icon and content, a circular graph, or a single larger item (for example, the bottom row of complications on the Modular watch face).

<span id="page-7-0"></span>

| Columns text | Ring image  | Ring text  | Simple image |
|--------------|-------------|------------|--------------|
|              |             |            |              |
| Simple text  | Stack image | Stack text |              |
|              |             |            |              |

As you design icons and images for a modular small complication, use the following values for guidance.

| Image  | 38mm           | 40mm/42mm      | 41mm           | 44mm            | 45mm/49mm      |
|--------|----------------|----------------|----------------|-----------------|----------------|
| Ring   | 18x18 pt       | 19x19 pt       | 20x20 pt       | 21x21 pt (42x42 | 22.5x22.5 pt   |
|        | (36x36 px @2x) | (38x38 px @2x) | (40x40 px @2x) | px @2x)         | (45x45 px @2x) |
| Simple | 26x26 pt       | 29x29 pt       | 30.5x30.5 pt   | 32x32 pt        | 34.5x34.5 pt   |
|        | (52x52 px @2x) | (58x58 px @2x) | (61x61 px @2x) | (64x64 px @2x)  | (69x69 px @2x) |
| Stack  | 26x14 pt       | 29x15 pt       | 30.5x16 pt     | 32x17 pt        | 34.5x18 pt     |
|        | (52x28 px @2x) | (58x30 px @2x) | (61x32 px @2x) | (64x34 px @2x)  | (69x36 px @2x) |

| Image       | 38mm           | 40mm/42mm      | 41mm           | 44mm           | 45mm/49mm      |
|-------------|----------------|----------------|----------------|----------------|----------------|
| Placeholder | 26x26 pt       | 29x29 pt       | 30.5x30.5 pt   | 32x32 pt       | 34.5x34.5 pt   |
|             | (52x52 px @2x) | (58x58 px @2x) | (61x61 px @2x) | (64x64 px @2x) | (69x69 px @2x) |

**Note**

In each stack measurement, the width value represents the maximum size.

#### **[Modular](#page-8-0) large**

<span id="page-8-0"></span>Modular large templates offer a large canvas for displaying up to three rows of content (for example, in the center of the Modular watch face).

| Columns | Standard body |  |  |
|---------|---------------|--|--|
|         |               |  |  |
| Table   | Tall body     |  |  |

As you design icons and images for a modular large complication, use the following values for guidance.

| Content       | 38mm         | 40mm/42mm    | 41mm            | 44mm         | 45mm/49mm       |
|---------------|--------------|--------------|-----------------|--------------|-----------------|
| Columns       | 11-32x11 pt  | 12-37x12 pt  | 12.5-39x12.5 pt | 14-42x14 pt  | 14.5-44x14.5 pt |
|               | (22-64x22 px | (24-74x24 px | (25-78x25 px    | (28-84x28 px | (29-88x29 px    |
|               | @2x)         | @2x)         | @2x)            | @2x)         | @2x)            |
| Standard body | 11-32x11 pt  | 12-37x12 pt  | 12.5-39x12.5 pt | 14-42x14 pt  | 14.5-44x14.5 pt |
|               | (22-64x22 px | (24-74x24 px | (25-78x25 px    | (28-84x28 px | (29-88x29 px    |
|               | @2x)         | @2x)         | @2x)            | @2x)         | @2x)            |
| Table         | 11-32x11 pt  | 12-37x12 pt  | 12.5-39x12.5 pt | 14-42x14 pt  | 14.5-44x14.5 pt |
|               | (22-64x22 px | (24-74x24 px | (25-78x25 px    | (28-84x28 px | (29-88x29 px    |
|               | @2x)         | @2x)         | @2x)            | @2x)         | @2x)            |

# **[Extra](#page-8-1) large**

Extra large templates display larger text and images (for example, on the X-Large watch faces).

| Ring image  | Ring text   | Simple image |  |
|-------------|-------------|--------------|--|
|             |             |              |  |
| Simple text | Stack image | Stack text   |  |

<span id="page-8-1"></span>As you design icons and images for an extra large complication, use the following values for guidance.

| Image       | 38mm        | 40mm/42mm      | 41mm           | 44mm        | 45mm/49mm     |
|-------------|-------------|----------------|----------------|-------------|---------------|
| Ring        | 63x63 pt    | 66.5x66.5 pt   | 70.5x70.5 pt   | 73x73 pt    | 79x79 pt      |
|             | (126x126 px | (133x133 px    | (141x141 px    | (146x146 px | (158x158 px   |
|             | @2x)        | @2x)           | @2x)           | @2x)        | @2x)          |
| Simple      | 91x91 pt    | 101.5x101.5 pt | 107.5x107.5 pt | 112x112 pt  | 121x121 pt    |
|             | (182x182 px | (203x203 px    | (215x215 px    | (224x224 px | (242x242 px   |
|             | @2x)        | @2x)           | @2x)           | @2x)        | @2x )         |
| Stack       | 78x42 pt    | 87x45 pt       | 92x47.5 pt     | 96x51 pt    | 103.5x53.5 pt |
|             | (156x84 px  | (174x90 px     | (184x95 px     | (192x102 px | (207x107 px   |
|             | @2x)        | @2x)           | @2x)           | @2x)        | @2x)          |
| Placeholder | 91x91 pt    | 101.5x101.5 pt | 107.5x107.5 pt | 112x112 pt  | 121x121 pt    |
|             | (182x182 px | (203x203 px    | (215x215 px    | (224x224 px | (242x242 px   |
|             | @2x)        | @2x)           | @2x)           | @2x)        | @2x)          |

**Note**

In each stack measurement, the width value represents the maximum size.

### **Platform [considerations](#page-9-0)**

<span id="page-9-0"></span>*Not supported in iOS, iPadOS, macOS, tvOS, or visionOS.*

### <span id="page-10-0"></span>**[Resources](#page-10-0)**

<span id="page-10-2"></span>**[Related](#page-10-2)**

[Watch](https://developer.apple.com/design/human-interface-guidelines/watch-faces) faces

<span id="page-10-3"></span>**Developer [documentation](#page-10-3)**

[WidgetKit](https://developer.apple.com/documentation/WidgetKit)

**[Videos](#page-10-4)**

<span id="page-10-4"></span>![](_page_10_Picture_6.jpeg)

### **[Change](#page-10-1) log**

<span id="page-10-1"></span>

| Date               | Changes                                                                                          |
|--------------------|--------------------------------------------------------------------------------------------------|
| October 24, 2023   | Replaced links to deprecated ClockKit documentation<br>with links to WidgetKit documentation.    |
| June 5, 2023       | Updated guidance for rectangular complications to<br>support them as widgets in the Smart Stack. |
| September 14, 2022 | Added specifications for Apple Watch Ultra.                                                      |