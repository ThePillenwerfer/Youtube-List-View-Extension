# YouTube Subscriptions List View

**YouTube Subscriptions List View** is a Chrome Extension (Manifest V3) that forces the YouTube Subscriptions and Home feeds into a classic, readable **List View** layout.

Modern YouTube forces a "Rich Grid" layout that hides video descriptions and truncates metadata. This extension restores the vertical list format, fetches the missing video descriptions, and provides a customizable UI to adjust the layout to your preference.

## 🚀 Features

* **Force List View:** Converts the multi-column grid into a single-column list layout on both the **Subscriptions** and **Home** feeds.
* **Video Descriptions:** Automatically fetches and displays the video description (short snippet) for every video, which is normally hidden in Grid view.
* **Customizable Layout:** A popup menu allows you to adjust:
    * **Container Width:** Control how wide the list is on your screen (50% - 100%).
    * **Thumbnail Size:** Resize video thumbnails (150px - 400px).
    * **Typography:** Adjust the font size for Video Titles and Metadata/Descriptions.
* **Live Preview:** Adjustments made in the popup are reflected instantly on the active tab without needing a reload.
* **Layout Fixes:** Includes logic to handle YouTube's Single Page Application (SPA) navigation and layout reflows.

## 📂 File Structure

* `manifest.json` - Extension configuration (MV3).
* `content.js` - Main logic for DOM manipulation, fetching descriptions, and injecting layout fixes.
* `styles.css` - CSS overrides to force the grid into a list and apply user settings.
* `popup.html` & `popup.js` - The settings interface for customizing the view.

## 🛠️ Installation

Since this is a developer build, you can install it via "Load Unpacked":

1.  **Download** the source files into a folder named `youtube-list-view`.
    * Ensure `manifest.json`, `content.js`, `styles.css`, `popup.html`, and `popup.js` are all in the root of this folder.
2.  Open Google Chrome and navigate to `chrome://extensions/`.
3.  Enable **Developer mode** using the toggle switch in the top right corner.
4.  Click the **Load unpacked** button.
5.  Select the `youtube-list-view` folder you created in Step 1.
6.  The extension is now active! Go to YouTube to see the changes.

## ⚙️ Usage

1.  Navigate to [YouTube.com](https://www.youtube.com).
2.  The extension will automatically convert the Home or Subscriptions feed into a list.
3.  **To customize the look:**
    * Click the extension icon in the Chrome toolbar.
    * Use the **sliders** to adjust the width, thumbnail size, and font sizes.
    * Changes apply immediately.
    * Click **Reset to Defaults** if you want to revert to the original optimized settings.

## 🔧 Technical Notes

* **Permissions:**
    * `storage`: Used to save your UI preferences (width, font size, etc.) so they persist across sessions.
    * `host_permissions` (`https://www.youtube.com/*`): Required to inject the content script and styles into YouTube.
* **Performance:**
    * The extension uses a `MutationObserver` to detect when YouTube loads new videos (infinite scroll) and applies styles dynamically.
    * Video descriptions are fetched via individual `fetch()` requests to the video URL to parse the meta description tag.

## 📈 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=engin0223/Youtube-List-View-Extension&type=Date)](https://star-history.com/#engin0223/Youtube-List-View-Extension&Date)
