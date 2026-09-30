# Synchronized Hero Spotlight Reveal

## Scope
Update only the main headline animation inside the existing three-slide hero. Keep the layout, typography, images, orbital image movement, supporting copy, calls to action, controls, navigation, and all other sections unchanged.

## Implementation
- Register GSAP SplitText alongside the existing ScrollTrigger plugin.
- Create one managed SplitText instance for each slide headline after the hero mounts.
- Replace the incoming headline line-motion with a character-level reveal that begins during the existing incoming image segment, around 40% into its entrance.
- Animate characters from the center outward from low opacity, reduced scale, and blur to sharp, full-opacity text at scale 1.
- Keep outgoing text behavior and supporting-copy timing intact.
- Use the existing shared slide transition timeline so scrolling and arrow navigation trigger the same synchronized effect.
- Preserve the reduced-motion path without animated blur or scaling.
- Revert SplitText instances and GSAP state when the hero unmounts to prevent duplicate wrappers or animations.

## Validation
- Check all three slides through scroll-driven and arrow-driven navigation.
- Confirm headline characters finish sharp and fully visible while image movement remains unchanged.
- Confirm the preview builds without errors and no duplicate SplitText wrappers appear after repeated navigation.
