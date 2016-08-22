# Font Privacy for Chrome
Stop your fonts from being fingerprinted or interrogated. Protect your privacy by only using white-listed fonts.

##Why ?
Your list of fonts can help identify your browser and allows you to be tracked. See https://panopticlick.eff.org

By adding elements to the page with different fonts and then measuring the width on the page, a website can use JavaScript to identify which fonts you have. This plugin is an attempt to minimise tracking without blocking all javascript.

This plugin enforces a whitelist of `font-family`s on DOM elements modified using:

- `CSSStyleDeclaration.setProperty`
- `CSSStyleDeclaration.fontFamily`
- `CSSStyleDeclaration.cssText`
- `Element.setAttribute`
- `Element.innerHTML`
- `Element.outerHTML`
- `Node.appendChild`

There are still some ways around it, but this is super-effective for the current fingerprinting libraries.

##Configure
The whitelist contains the array `commonFonts` and any webfonts downloaded by the page. You can modify the array to appear as a different system, although the fonts must actually exist on your system for them to be identified by the tracker.

##Installation
I'm not in the mood to pay Google the $5 for Chrome Web Store registration today so for now we will use an unpacked extension.

1. Clone the repo somewhere ```git clone https://github.com/bcaller/font-privacy-chrome.git```
2. Go to chrome://extensions
3. Enable developer mode
4. Click Load unpacked extension
5. Select the font-privacy-chrome folder
6. Also optionally check the box "Allow in incognito" next to the Font Privacy

##Flash & Java
It is also recommended that you turn off Flash autorun to prevent your fonts from being fingerprinted more extensively. You will then need to right-click on a Flash element to load it. To do this go to Settings; Show advanced settings; Privacy; Content Settings; Plug-ins; Let me choose when to run plug-in content.

##TODO
- `font` as well as `font-family`
- `CanvasRenderingContext2D.font`
