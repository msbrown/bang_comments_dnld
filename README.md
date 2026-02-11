

This is a variation of v 1.1 code from Facebook Comment Scraper Userscript https://github.com/disrex-group/FB-Comments-Exporter-User-script

Makes these modifications: 
 - It adds url being scraped (postUrlScraped), and using the format of that url, it extracts the name of the account (accountName) and the post ID (postId) and all three are added to the top of the Json file for analysis later. 
    - Assumed logic for parsing url is http://www.facebook.com/{accountName}/posts/{postId}
- Filename: it uses the accountName (extracted from url) and the datetime to name the json 
  - In cases where the account name contains . it replaces those with - in the filename. 

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

# Usage 
1. **Log into Facebook**
2. **Open any Facebook post** with comments (the modal window will come up)
3. **Set maximum number of comments** then **click "Scrape Modal"** in the floating panel (top-right corner)
4. **Watch it work** - The script will automatically:
   - Expand comment sections
   - Load more comments
   - Expand replies (including nested replies)
   - Detect comment depth and hierarchy
   - Collect comprehensive comment data
5. **Auto-Export** - JSON file downloads automatically when complete using naming convention: {accountName}__{datetime}.json


The exported json file include:
- original url 
- account name (parsed from url)
- post id (parsed from url)

- **Author Name**: Commenter's display name
- **Profile URL**: Link to commenter's Facebook profile
- **Profile Image**: URL to profile picture
- **Comment Text**: Full comment content
- **Timestamp**: When the comment was posted
- **Likes**: Number of reactions
- **Depth**: Nesting level (0=main comment, 1=direct reply, 2=reply to reply, etc.)
- **Detection Method**: How the depth was determined
- **Hierarchical Structure**: Nested replies under parent comments
- **Parent ID**: Reference to parent comment
- **Reply To Author**: Name of the author being replied to
