# USPTO-Dark-Reader-Fixes
The USPTO has approved the installation of the Dark Reader browser extension for Chrome and Edge, which modifies the CSS of webpages to force them into a "dark" color scheme. Dark Reader, however, is imperfect, and so various websites have "fixes" that fine-tune how Dark Reader functions on that specific site.

Normally, these fixes are submitted by community members and then merged into the codebase by the Dark Reader maintainers so that all users have access to them. However, understandably, the Dark Reader team doesn't accept fixes for websites that aren't publicly accessible, and so this repository contains a number of fixes for internal webtools only available to USPTO personnel.

Unfortunately, it also means that the fixes have to be installed and maintained manually by each user on a per-site basis. But at least the newest versions of the fixes will be instantly available to all who are interested in using them.

In the future, I may add a tool to automatically update the fixes, if it is even possible.

## How to Add a Website Fix to Dark Reader
1. Click the little Dark Reader icon in your browser to open the Dark Reader panel. Go to the bottom and click "Dev tools". This should bring up a second window where you can add fixes for the various modes Dark Reader can operate in.
2. The fixes in this repo are for Dynamic mode, so go to that tab and select the per-site editor.
3. Look at the file for the website you want to fix and copy the first line of text. That line is the url pattern that the fixes will apply to (e.g., dav.uspto.gov/webapp). Paste that line into the search bar. It should come up empty for search results, so click "Create new fix" to add your own.
4. Copy the entire text file (including the first line!) and paste it into the editor window that opens up.
5. Click "Apply" at the bottom of the screen, and then reload the webpage if you have it open already. The fixes should now be applied! UwU

To update an existing fix, follow the same procedure, except in step 3 the search should come up with the fix you already have installed. Once you click on the correct url, overwrite the entire contents of the fix in the devtools window with the content of the updated text file.

## Known Issues

### General
- **Fixes Not Applying on Startup:** The first time you open your browser after turning on your computer, the Dark Reader fixes from this repo will sometimes not be applied. If this occurs, open the DevTools panel and click "Apply", then reload the webpage.

### PE2E-Search
- **Custom Gadget Colors:** PE2E-Search is one of the few tools that allows for color customization. In the user preferences, the background, text, and hyperlink colors for a number of gadgets can be modified. Unfortunately, Dark Reader inverts these custom colors and ruins them. Due to limitations of the Dark Reader fixes, this can only be repaired in the Search Results, Document Viewer, Notes Viewer, Tagged Documents, and Document Filters gadgets. For the Search History, Collections, and Hit Terms gadgets, I have instead chosen to overwrite the incorrectly inverted colors with a default dark gray background and white text. Unless PE2E-Search changes how these colors work in the future, it is unlikely that this will ever be resolved.
- **Document Viewer Highlights:** In the Document Viewer, due to limiations of the Dark Reader fixes, it is currently impossible to revert the inverted highlight colors for the hit terms.