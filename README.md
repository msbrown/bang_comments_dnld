

This is a variation of v 1.1 code from Facebook Comment Scraper Userscript https://github.com/disrex-group/FB-Comments-Exporter-User-script

Modifies name of file to formate {account}__{postid}__datetime.json It uses the url to extract the account and post id assuming this logic: https://www.facebook.com/{accountname}/posts/{postid}
- Replaces . with - for naming. 

# Install 
1. **Install Extension & check permissions**: [Tampermonkey](https://tampermonkey.net/) (Chrome/Edge) or [Greasemonkey](https://addons.mozilla.org/en-US/firefox/addon/greasemonkey/) (Firefox)
    - You may also have to go choose "Manage Extensions" from the toolbar
        - In the new window, ensure that "Developer Mode" in upper right is enabled
        - Choose the tampermonkey extention and in the new window: 
            - "Allow User Scripts" is toggled on, and  
            - "Allow access to file URLs" is toggled on.
2. **Install Script**: [Click here to install the userscript](https://github.com/msbrown/bang_comments_dnld/raw/refs/heads/main/bang_comments_dnld.user.js)
    - If the click does not work, go to the Tampermonkey extension, click Dashboard
    - in the new Dashboard window, click Utilities in upper right and scroll down to find "Import from URL"
    and paste this link and click install: [https://github.com/msbrown/bang_comments_dnld/raw/refs/heads/main/bang_comments_dnld.user.js](https://github.com/msbrown/bang_comments_dnld/raw/refs/heads/main/bang_comments_dnld.user.js)
3. **Open any Facebook post** with comments
4. **Set maximum number of comments** then **click "Scrape Modal"** in the floating panel (top-right corner)
5. **Watch it work** - automatically expands replies, detects nesting depth, highlights comments
6. **Auto-Export** - JSON file downloads automatically when complete. 