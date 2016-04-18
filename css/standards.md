#CSS Best practices and Standards

##Standards

CSS declarations should be formatted like so.

All delivered CSS should be tested at all widths down to at least 320px and preferably 240px. Supporting the smallest screens can be seen as a form of serving content to those who can't afford high-resolutions screens.

Root font size should be set to the html element in px, preferably 16px for desktop, and if needed, media query adjustments can be made to that base size to scale up/down for readability in mobile, using rems to handle scaling for font sizes that should be relative to the base size. px should not be used to set font sizes except where it is needed to override the root font size in limited use-cases.

##Best Practices
Prefer %s to other measures.