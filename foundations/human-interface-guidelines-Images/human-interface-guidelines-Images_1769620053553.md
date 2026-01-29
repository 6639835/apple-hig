<span id="page-0-1"></span>**December 16, 2025**

Added guidance for spatial photos and spatial scenes in visionOS.

# **Images**

To make sure your artwork looks great on all devices you support, learn how the system displays content and how to deliver art at the appropriate scale factors.

![](_page_0_Picture_5.jpeg)

# **[Resolution](#page-0-0)**

Different devices can display images at different resolutions. For example, a 2D device displays images according to the resolution of its screen.

A *point* is an abstract unit of measurement that helps visual content remain consistent regardless of how it's displayed. In 2D platforms, a point maps to a number of pixels that can vary according to the resolution of the display; in visionOS, a point is an angular value that allows visual content to scale according to its distance from the viewer.

<span id="page-0-0"></span>When creating bitmap images, you specify a *scale factor* which determines the resolution of an image. You can visualize scale factor by considering the density of pixels per point in 2D displays of various resolutions. For example, a scale factor of 1 (also called @1x) describes a 1:1 pixel density, where one pixel is equal to one point. High-resolution 2D displays have higher pixel densities, such as 2:1 or 3:1. A 2:1 density (called @2x) has a scale factor of 2, and a 3:1 density (called @3x) has a scale factor of 3. Because of higher pixel densities, high-resolution displays demand images with more pixels.

#### **Supported platforms**

![](_page_0_Picture_11.jpeg)

#### [Images](#page-0-1)

[Resolution](#page-0-0)

[Formats](#page-1-0) Best [practices](#page-1-1)

Platform [considerations](#page-2-0)

[Resources](#page-6-0)

[Change](#page-6-1) log

![](_page_1_Picture_0.jpeg)

**Provide high-resolution assets for all bitmap images in your app, for every device you support.** As you add each image to your project's asset catalog, identify its scale factor by appending "@1x," "@2x," or "@3x" to its filename. Use the following values for guidance; for additional scale factors, see [Layout](https://developer.apple.com/design/human-interface-guidelines/layout).

| Platform        | Scale factors                |
|-----------------|------------------------------|
| iPadOS, watchOS | @2x                          |
| iOS             | @2x and @3x                  |
| visionOS        | @2x or higher (see visionOS) |
| macOS, tvOS     | @1x and @2x                  |

**In general, design images at the lowest resolution and scale them up to create highresolution assets.** When you use resizable vectorized shapes, you might want to position control points at whole values so that they're cleanly aligned at 1x. This positioning allows the points to remain cleanly aligned to the raster grid at higher resolutions, because 2x and 3x are multiples of 1x.

# **[Formats](#page-1-0)**

As you create different types of images, consider the following recommendations.

<span id="page-1-0"></span>

| Image type                                                                                   | Format                                            |
|----------------------------------------------------------------------------------------------|---------------------------------------------------|
| Bitmap or raster work                                                                        | De-interlaced PNG files                           |
| PNG graphics that don't require full 24-bit color                                            | An 8-bit color palette                            |
| Photos                                                                                       | JPEG files, optimized as necessary, or HEIC files |
| Stereo or spatial photos                                                                     | Stereo HEIC                                       |
| Flat icons, interface icons, and other flat artwork that<br>requires high-resolution scaling | PDF or SVG files                                  |

# **Best [practices](#page-1-1)**

<span id="page-1-1"></span>**Include a color profile with each image.** Color profiles help ensure that your app's colors appear as intended on different displays. For guidance, see Color [management](https://developer.apple.com/design/human-interface-guidelines/color#Color-management).

**Always test images on a range of actual devices.** An image that looks great at design time may appear pixelated, stretched, or compressed when viewed on various devices.

# <span id="page-2-0"></span>**Platform [considerations](#page-2-0)**

*No additional considerations for iOS, iPadOS, or macOS.*

# **[tvOS](#page-2-1)**

<span id="page-2-1"></span>Layered images are at the heart of the Apple TV user experience. The system combines layered images, transparency, scaling, and motion to produce a sense of realism and vigor that evokes a personal connection as people interact with onscreen content.

### **[Parallax](#page-2-2) effect**

<span id="page-2-2"></span>*Parallax* is a subtle visual effect the system uses to convey depth and dynamism when an element is in focus. As an element comes into focus, the system elevates it to the foreground, gently swaying it while applying illumination that makes the element's surface appear to shine. After a period of inactivity, out-of-focus content dims and the focused element expands.

Layered images are required to support the parallax effect.

![](_page_2_Picture_8.jpeg)

Play

### **[Layered](#page-2-3) images**

<span id="page-2-3"></span>A *layered image* consists of two to five distinct layers that come together to form a single image. The separation between layers, along with use of transparency, creates a feeling of depth. As someone interacts with an image, layers closer to the surface elevate and scale, overlapping lower layers farther back and producing a 3D effect.

#### **Important**

Your tvOS app [icon](https://developer.apple.com/design/human-interface-guidelines/app-icons#tvOS) must use a layered image. For other focusable images in your app, including Top [Shelf](https://developer.apple.com/design/human-interface-guidelines/top-shelf) images, layered images are strongly encouraged, but optional.

You can embed layered images in your app or retrieve them from a content server at runtime. For guidance on adding layered images to your app, see the Parallax [Previewer](https://help.apple.com/itc/parallaxpreviewer/) User Guide.

#### **Developer note**

If your app retrieves layered images from a content server at runtime, you must provide runtime layered images (*.lcr*). You can generate them from LSR files or Photoshop files using the *layerutil* command-line tool that Xcode provides. Runtime layered images are intended to be downloaded — don't embed them in your app.

**Use standard interface elements to display layered images.** If you use standard views and system-provided focus APIs — such as *[FocusState](https://developer.apple.com/documentation/SwiftUI/FocusState)* — layered images automatically get the parallax treatment when people bring them into focus.

**Identify logical foreground, middle, and background elements.** In foreground layers, display prominent elements like a character in a game, or text on an album cover or movie poster. Middle layers are perfect for secondary content and effects like shadows. Background layers are opaque backdrops that showcase the foreground and middle layers without upstaging them.

**Generally, keep text in the foreground.** Unless you want to obscure text, bring it to the foreground layer for clarity.

**Keep the background layer opaque.** Using varying levels of opacity to let content shine through higher layers is fine, but your background layer must be opaque — you'll get an error if it's not. An opaque background layer ensures your artwork looks great with parallax, drop shadows, and system backgrounds.

**Keep layering simple and subtle.** Parallax is designed to be almost unnoticeable. Excessive 3D effects can appear unrealistic and jarring. Keep depth simple to bring your content to life and add delight.

**Leave a safe zone around the foreground layers of your image.** When focused, content on some layers may be cropped as the layered image scales and moves. To ensure that essential content is always visible, keep it within a safe zone. For guidance, see App [icons.](https://developer.apple.com/design/human-interface-guidelines/app-icons)

**Always preview layered images.** To ensure your layered images look great on Apple TV, preview them throughout your design process using Xcode, the Parallax Previewer app for macOS, or the Parallax Exporter plug-in for Adobe Photoshop. Pay special attention as scaling and clipping occur, and readjust your images as needed to keep important content safe. After your layered images are final, preview them on an actual TV for the most accurate representation of what people will see. To download Parallax Previewer and Parallax Exporter, see [Resources](https://developer.apple.com/design/resources/#parallax-previewer).

# **[visionOS](#page-3-0)**

In visionOS, people can view images at a much larger range of sizes than in any other platform, and the system dynamically scales the image resolution to match the current size. Because you can position images at specific angles within someone's surroundings, image pixels may not line up 1:1 with screen pixels.

<span id="page-3-0"></span>**Create a layered app icon.** App icons in visionOS are composed of two to three layers that provide the appearance of depth by moving at subtly different rates when the icon is in focus. For guidance, see Layer [design](https://developer.apple.com/design/human-interface-guidelines/app-icons#Layer-design).

**Prefer vector-based art for 2D images.** Avoid bitmap content because it might not look good when the system scales it up. If you use Core Animation layers, see Drawing sharp [layer-based](https://developer.apple.com/documentation/visionOS/drawing-sharp-layer-based-content) content in [visionOS](https://developer.apple.com/documentation/visionOS/drawing-sharp-layer-based-content) for developer guidance.

**If you need to use rasterized images, balance quality with performance as you choose a resolution.** Although a @2x image looks fine at common viewing distances, its fixed resolution means that the system doesn't dynamically scale it and it might not look sharp from close up. To help a rasterized image look sharp when people view it from a wide range of distances, you can use a higher resolution, but each increase in resolution results in a larger file size and may impact your app's runtime performance, especially for resolutions over @6x. If you use images that have resolutions higher than @2x, be sure to also apply high-quality image filtering to help balance quality and performance (for developer guidance, see *[filters](https://developer.apple.com/documentation/QuartzCore/CALayer/filters)*).

### **Spatial photos and spatial [scenes](#page-4-0)**

<span id="page-4-0"></span>In addition to 2D and stereoscopic images, visionOS apps and games can use RealityKit to display spatial photos and spatial scenes. A *spatial photo* is a stereoscopic photo with additional spatial metadata, as captured on iPhone 15 Pro or later, Apple Vision Pro, or other compatible camera. A *spatial scene* is a 3D image generated from a 2D image to add a parallax effect that responds to head movement. For developer guidance, see *[ImagePresentationComponent](https://developer.apple.com/documentation/RealityKit/ImagePresentationComponent)*.

**Make sure spatial photos render correctly in your app.** Use the stereo High-Efficiency Image Codec (HEIC) format to display a spatial photo in your app. When you add spatial metadata to a stereo HEIC, visionOS recognizes the photo as spatial and includes visual treatments that help minimize common causes of stereo-viewing discomfort.

**Prefer the feathered glass background effect to display text over spatial photos.** If you need to place text over a spatial photo in your app or game, use the feathered glass background effect. The effect adds contrast to make the text readable, and it blurs out detail to help reduce visual discomfort when people view text over spatial photos. For developer guidance, see *[Glass](https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect) [BackgroundEffect](https://developer.apple.com/documentation/SwiftUI/GlassBackgroundEffect)*.

**Take visual comfort into consideration when you make spatial photos from existing 2D content.** When adjusting the spatial metadata of a photo for your app or game, consider how you want people to view your content. Metadata like disparity adjustment can alter how people perceive the 3D scene, and can cause visual discomfort from certain viewing positions. For developer guidance, see Creating spatial photos and videos with spatial [metadata](https://developer.apple.com/documentation/ImageIO/Creating-spatial-photos-and-videos-with-spatial-metadata).

**Display spatial photos and spatial scenes in standalone views.** Avoid displaying spatial photos inline with other content, as this can cause visual discomfort. Instead, showcase spatial photos or spatial scenes in a separate view, like a sheet or window. If you must display stereoscopic images inline, provide generous spacing between the image and any inline content to help people's eyes adjust to the depth changes.

**Use spatial scenes in your app for specific moments.** Each spatial scene can take up to several seconds to generate from an existing image. Design experiences with this limitation in mind. For instance, the Photos app offers an explicit action to create a spatial scene while immersed in a single photo. Avoid displaying too many spatial scenes at once. Instead, use scroll views, pagination, or explicit actions to move to new photos and keep the visual information hierarchy simple.

**When displaying immersively, prefer minimal UI.** For example, the Spatial Gallery app displays a single piece of content with a small caption and a single Back button, relying on swipe gestures to navigate between items.

**Prefer displaying larger spatial scenes that you center in someone's field of view.** When people view a spatial scene, they may move their head laterally to view the parallax effect. Smaller spatial scenes provide less of a parallax effect and may not be as impactful to viewers.

# <span id="page-5-0"></span>**[watchOS](#page-5-0)**

**In general, avoid transparency to keep image files small.** If you always composite an image on the same solid background color, it's more efficient to include the background in the image. However, transparency is necessary in complication images, menu icons, and other interface icons that serve as template images, because the system uses it to determine where to apply color.

**Use autoscaling PDFs to let you provide a single asset for all screen sizes.** Design your image for the 40mm and 42mm screens at 2x. When you load the PDF, WatchKit automatically scales the image based on the device's screen size, using the values shown below:

| Screen size | Image scale |
|-------------|-------------|
| 38mm        | 90%         |
| 40mm        | 100%        |
| 41mm        | 106%        |
| 42mm        | 100%        |
| 44mm        | 110%        |
| 45mm        | 119%        |
| 49mm        | 119%        |

# <span id="page-6-0"></span>**[Resources](#page-6-0)**

### <span id="page-6-2"></span>**[Related](#page-6-2)**

Apple Design [Resources](https://developer.apple.com/design/resources/)

### <span id="page-6-3"></span>**Developer [documentation](#page-6-3)**

Drawing sharp [layer-based](https://developer.apple.com/documentation/visionOS/drawing-sharp-layer-based-content) content in visionOS — visionOS

[Images](https://developer.apple.com/documentation/SwiftUI/Images) — SwiftUI

*[UIImageView](https://developer.apple.com/documentation/UIKit/UIImageView)* — UIKit

*[NSImageView](https://developer.apple.com/documentation/AppKit/NSImageView)* — AppKit

### **[Videos](#page-6-4)**

<span id="page-6-4"></span>![](_page_6_Picture_9.jpeg)

**[Support](https://developer.apple.com/videos/play/wwdc2023/10181) HDR images in your app**

**Get [Started](https://developer.apple.com/videos/play/wwdc2017/821) with Display P3**

# **[Change](#page-6-1) log**

<span id="page-6-1"></span>

| Date               | Changes                                                                                    |
|--------------------|--------------------------------------------------------------------------------------------|
| December 16, 2025  | Added guidance for spatial photos and spatial scenes<br>in visionOS.                       |
| December 5, 2023   | Clarified guidance on choosing a resolution for a ras‐<br>terized image in a visionOS app. |
| June 21, 2023      | Updated to include guidance for visionOS.                                                  |
| September 14, 2022 | Added specifications for Apple Watch Ultra.                                                |