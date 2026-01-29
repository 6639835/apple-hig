# <span id="page-0-1"></span>**Loading**

The best content-loading experience finishes before people become aware of it.

![](_page_0_Picture_3.jpeg)

**Supported platforms**

![](_page_0_Picture_5.jpeg)

[Loading](#page-0-1) Best [practices](#page-0-0) Showing [progress](#page-1-0) Platform [considerations](#page-1-1) [Resources](#page-2-0) [Change](#page-2-1) log

If your app or game loads assets, levels, or other content, design the behavior so it doesn't disrupt or negatively impact the user experience.

## **Best [practices](#page-0-0)**

**Show something as soon as possible.** If you make people wait for loading to complete before displaying anything, they can interpret the lack of content as a problem with your app or game. Instead, consider showing placeholder text, graphics, or animations as content loads, replacing these elements as content becomes available.

**Let people do other things in your app or game while they wait for content to load.** Loading content in the background helps give people access to other actions. For example, a game could load content in the background while players learn about the next level or view an in-game menu. For developer guidance, see Improving the player [experience](https://developer.apple.com/documentation/GameKit/improving-the-player-experience-for-games-with-large-downloads) for games with large [downloads.](https://developer.apple.com/documentation/GameKit/improving-the-player-experience-for-games-with-large-downloads)

<span id="page-0-0"></span>**If loading takes an unavoidably long time, give people something interesting to view while they wait.** For example, you might provide gameplay hints, display tips, or introduce people to new features. Gauge the remaining loading time as accurately as possible to help you avoid giving people too little time to enjoy your placeholder content or having so much time that you need to repeat it.

**Improve installation and launch time by downloading large assets in the background.** Consider using the [Background](https://developer.apple.com/documentation/BackgroundAssets) Assets framework to schedule asset downloads — like game level packs, 3D character models, and textures — to occur immediately after installation, during updates, or at other nondisruptive times.

## <span id="page-1-0"></span>**Showing [progress](#page-1-0)**

**Clearly communicate that content is loading and how long it might take to complete.** Ideally, content displays instantly, but for situations where loading takes more than a moment or two, you can use system-provided components — called *progress indicators* — to show that loading is ongoing. In general, you use a *determinate* progress indicator when you know how long loading will take, and you use an *indeterminate* progress indicator when you don't. For guidance, see Progress [indicators.](https://developer.apple.com/design/human-interface-guidelines/progress-indicators)

**For games, consider creating a custom loading view.** Standard progress indicators work well in most apps, but can sometimes feel out of place in a game. Consider designing a more engaging experience by using custom animations and elements that match the style of your game.

## **Platform [considerations](#page-1-1)**

*No additional considerations for iOS, iPadOS, macOS, tvOS, or visionOS.*

#### <span id="page-1-1"></span>**[watchOS](#page-1-2)**

<span id="page-1-2"></span>**As much as possible, avoid showing a loading indicator in your watchOS experience.** People expect quick interactions with their Apple Watch, so aim to display content immediately. In situations where content needs a second or two to load, it's better to display a loading indicator than a blank screen.

## <span id="page-2-0"></span>**[Resources](#page-2-0)**

#### <span id="page-2-2"></span>**[Related](#page-2-2)**

[Launching](https://developer.apple.com/design/human-interface-guidelines/launching)

Progress [indicators](https://developer.apple.com/design/human-interface-guidelines/progress-indicators)

#### **Developer [documentation](#page-2-3)**

<span id="page-2-3"></span>[Background](https://developer.apple.com/documentation/BackgroundAssets) Assets

#### **[Videos](#page-2-4)**

<span id="page-2-4"></span>![](_page_2_Picture_7.jpeg)

**Discover [Apple-Hosted](https://developer.apple.com/videos/play/wwdc2025/325) Background Assets**

## **[Change](#page-2-1) log**

<span id="page-2-1"></span>

| Date          | Changes                                                                                          |
|---------------|--------------------------------------------------------------------------------------------------|
| June 9, 2025  | Revised guidance for storing downloads to reflect<br>downloading large assets in the background. |
| June 10, 2024 | Added guidelines for showing progress and storing<br>downloads, and enhanced guidance for games. |