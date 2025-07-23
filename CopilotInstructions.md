# The Center Wire Static HTML Website

Please execute these instructions.

## AI Instructions: Creating New Articles from Generated Content
**CRITICAL REMINDER: Use template.html AS-IS with NO styling modifications**

### Overview
Use these step-by-step instructions to convert generated news content into a properly formatted HTML article for The Center Wire website using the template.html file.

**⚠️ STYLING WARNING: The template.html file is configured to work perfectly with styles.css. Do NOT add any `<style>` blocks or inline CSS. All styling is handled externally.**

### Prerequisites
- Access to template.html file
- Access Generated content with article text, sources, and metadata in file GeneratedContent.txt
- Basic understanding of HTML structure

### Step-by-Step Process

#### Step 1: Prepare Your Content
1. **Review the generated content** and identify:
   - Article title/headline
   - Publication date (if not provided, assume today is the publication date)
   - Estimated read time (calculate ~200-250 words per minute)
   - Main article text with different perspective sections (if no perspectives, determine appropriate sections)
   - Key quotes from sources
   - Source links and citations
   - Article category (Politics, Business, World, Technology, Health, etc.)
   - Featured image URL and caption
   - **Image source attribution** (photographer name, platform, license information for proper crediting)
   - **Social media summary** (2-3 sentences for Facebook/Twitter sharing)
   - **SEO keywords** (relevant topics, people, places for search optimization)
   - **Image dimensions** (width and height for optimal social media display)

#### Step 2: Copy Template File
1. **Create a new file** by copying `template.html`
   - **IMPORTANT**: The template.html file contains NO inline `<style>` blocks - all styling comes from styles.css
   - **NOTE**: CSS variables are defined in the main styles.css file and should never be redefined inline
2. **Rename the file** using the format: `article-title-keywords.html`
   - Use lowercase letters
   - Replace spaces with hyphens
   - Keep it concise but descriptive
   - Example: `federal-court-blocks-citizenship-order.html`

#### Step 3: Update Meta Information
1. **Update the page title** (line ~6):
   ```html
   <title>[ARTICLE TITLE] - The Center Wire</title>
   ```
   Replace `[ARTICLE TITLE]` with the actual article headline

2. **Update Open Graph meta tags for social media sharing** (lines ~8-16):
   ```html
   <meta property="og:title" content="[ARTICLE TITLE]">
   <meta property="og:description" content="[ARTICLE SUMMARY]">
   <meta property="og:image" content="[FEATURED IMAGE URL]">
   <meta property="og:image:width" content="[IMAGE WIDTH]">
   <meta property="og:image:height" content="[IMAGE HEIGHT]">
   <meta property="og:url" content="https://thecenterwire.com/[ARTICLE FILENAME].html">
   ```
   - Replace `[ARTICLE SUMMARY]` with 2-3 sentence description for social media
   - Use the same featured image URL from your content
   - Include actual image dimensions (e.g., "1900" x "1267")
   - Replace `[ARTICLE FILENAME]` with your HTML filename

3. **Update Twitter Card meta tags** (lines ~18-22):
   ```html
   <meta name="twitter:title" content="[ARTICLE TITLE]">
   <meta name="twitter:description" content="[ARTICLE SUMMARY]">
   <meta name="twitter:image" content="[FEATURED IMAGE URL]">
   ```
   - Use the same title, summary, and image as Open Graph tags

4. **Update standard SEO meta tags** (lines ~24-27):
   ```html
   <meta name="description" content="[ARTICLE SUMMARY]">
   <meta name="keywords" content="[RELEVANT KEYWORDS]">
   ```
   - Use same summary as social media description
   - Replace `[RELEVANT KEYWORDS]` with comma-separated list (e.g., "Texas floods, Camp Mystic, emergency response, evacuation delay")

5. **Update social sharing button URLs** (in the social-sharing section):
   ```html
   <!-- Replace [ARTICLE_URL] with full URL to article (properly URL-encoded) -->
   <!-- Replace [ARTICLE_TITLE] with the article headline -->
   ```
   - Replace `[ARTICLE_URL]` with `https://thecenterwire.com/[FILENAME].html`
   - **For Facebook**: Use URL-encoded version: `https%3A//thecenterwire.com/[FILENAME].html`
   - Replace `[ARTICLE_TITLE]` with the article headline (URL-encoded for Twitter)
   - Example: `https://thecenterwire.com/texas-floods-camp-mystic-tragedy.html`

6. **Update Facebook Comments URL** (in the comments-section):
   ```html
   <div class="fb-comments" data-href="[ARTICLE_URL]" ...>
   ```
   - Replace `[ARTICLE_URL]` with the same full URL used for social sharing
   - Comments are automatically scoped to this specific URL

#### Step 4: Update Article Metadata
1. **Find the article-meta section** (~line 185) and update:
   ```html
   <span class="category">POLITICS</span>  <!-- Update category -->
   <span class="date">[DATE]</span>        <!-- Update with publication date -->
   <span class="read-time">[X] min read</span>  <!-- Update read time -->
   ```

2. **Update the main article title** (~line 188):
   ```html
   <h1 class="article-title">[ARTICLE TITLE]</h1>
   ```

#### Step 5: Customize Perspective Navigation
1. **Update perspective buttons** (~line 191-195) based on your content:
   ```html
   <div class="perspective-nav">
       <a href="#section1" class="perspective-button active">[Perspective 1]</a>
       <a href="#section2" class="perspective-button">[Perspective 2]</a>
       <a href="#section3" class="perspective-button">[Perspective 3]</a>
   </div>
   ```
   - Replace with relevant perspective names (e.g., "Legal Analysis", "Conservative View", "Liberal Response")
   - Ensure IDs match the section headings you'll create later

#### Step 6: Add Featured Image
1. **Update the image section** (~line 200-204):
   ```html
   <div class="article-image-full">
       <img src="[IMAGE_URL]" alt="[IMAGE_DESCRIPTION]">
       <div class="article-image-caption">[Image caption]</div>
   </div>
   ```

#### Step 6.5: Download Image Locally (Recommended)
1. **Capture image source information BEFORE downloading**:
   - **Record photographer name** (if available from Unsplash, Pexels, or other platforms)
   - **Note the platform** (Unsplash, Pexels, Getty Images, etc.)
   - **Save the original URL** and any photo ID numbers for reference
   - **Check license requirements** (Creative Commons, attribution needed, etc.)
   - Example: "Photo by John Smith on Unsplash (Photo ID: 1589994965851-a8f479c573a9)"

2. **Download external images to local directory**:
   - Use curl or similar tool to download images from external URLs (Unsplash, etc.)
   - Save with descriptive filename: `article-topic-image.jpg`
   - Example: `curl -o "ice-deportation-image.jpg" "[EXTERNAL_IMAGE_URL]"`

3. **Update all image references**:
   - **Article featured image**: Change `src="[EXTERNAL_URL]"` to `src="local-image.jpg"`
   - **Open Graph meta tag**: Update `og:image` content to `https://thecenterwire.com/local-image.jpg`
   - **Twitter Card meta tag**: Update `twitter:image` content to `https://thecenterwire.com/local-image.jpg`
   - **Homepage featured section**: Update featured article image reference if applicable

#### Step 7: Structure Article Content
1. **Replace the opening paragraph** with your article's lead paragraph
2. **Create sections** using h3 headings with matching IDs:
   ```html
   <h3 id="section1">[Section 1 Title]</h3>
   <p>[Content for first perspective/section]</p>
   ```
   - Ensure IDs match the perspective navigation buttons
   - Use clear, descriptive section titles

#### Step 8: Add Quote Blocks
1. **Insert quote blocks** for important statements:
   ```html
   <div class="quote-block">
       "[Important quote from a key figure or expert]"
       <br><strong>— [Attribution: Name, Title/Organization]</strong>
   </div>
   ```
   - Use for impactful quotes that highlight different perspectives
   - Include proper attribution

#### Step 9: Add Bias Rating
1. **Update the bias rating section** (~line 240):
   ```html
   <div class="bias-rating">
       <strong>BIAS RATING: [NEUTRAL/LEFT-LEANING/RIGHT-LEANING]</strong><br>
       [Brief explanation of the bias assessment]
   </div>
   ```

#### Step 10: Update Sources Section
1. **Replace placeholder sources** (~line 247-253) with actual references:
   ```html
   <ol class="sources-list">
       <li><a href="[URL]" target="_blank">[Source Title] – [Publication] – [Date]</a></li>
       <!-- Add more sources as needed -->
   </ol>
   ```
   - Include all sources referenced in the article
   - Use full, accurate URLs
   - Format: "Title – Publication – Date"

2. **Add image credit section** after the main sources:
   ```html
   <h4>Image Credit</h4>
   <p>Featured image: [IMAGE_DESCRIPTION] by <a href="[PHOTOGRAPHER_PROFILE_URL]" target="_blank">[PHOTOGRAPHER_NAME]</a> on <a href="[PLATFORM_URL]" target="_blank">[PLATFORM]</a> ([Photo ID or reference if available])</p>
   ```
   - Example: `Featured image: Government building photograph by John Smith on <a href="https://unsplash.com/" target="_blank">Unsplash</a> (Photo ID: 1589994965851-a8f479c573a9)`
   - If photographer name unavailable: `Featured image: [IMAGE_DESCRIPTION] from <a href="[PLATFORM_URL]" target="_blank">[PLATFORM]</a> ([Photo ID])`


#### Step 10.b: Critical CSS and Styling Verification
   **⚠️ CRITICAL: Prevent CSS Conflicts and Styling Issues**

   **DO NOT add any `<style>` blocks to the HTML file!** All styling is handled by the external styles.css file. Adding inline styles will cause conflicts and break the website's appearance.

   **Common CSS mistakes to avoid:**
   1. **Never add `<style>` tags** - Use only external CSS file (styles.css)
   2. **Don't override `.article-page` padding** - It's correctly set in styles.css as `padding: 2rem` and `max-width: 1000px`
   3. **Don't duplicate Facebook SDK** - Should only be in `<body>`, not in `<head>`
   4. **Don't mix CSS variable references with hardcoded values** - Use CSS variables like `var(--primary-blue)`

   **Double-check verification steps:**
   1. **Verify NO `<style>` blocks exist** in the HTML file - search for `<style>` and `</style>` tags
   2. **Compare styling with existing articles** like `fbi-epstein-video-three-minutes-missing.html`
   3. **Check article structure** matches the pattern:
      ```html
      <main class="main">
          <div class="container">
              <div class="article-page">
                  <a href="index.html" class="back-to-home">← Back to Home</a>
                  <div class="article-header">
      ```
   4. **Verify proper header structure** - should use external styles.css, no inline styles
   5. **Check footer structure** - should be consistent with homepage
   6. **Test social sharing buttons** - all 5 buttons (Facebook, Twitter, LinkedIn, Email, Copy) should be present and positioned correctly

   **If you catch yourself about to add CSS:**
   - STOP and use the external styles.css file instead
   - All article styling is already defined in styles.css
   - The template.html should only contain HTML structure and placeholder content


#### Step 11: Final Review Checklist
**Before considering the article complete, verify each item:**

**Content Requirements:**
- [ ] All `[PLACEHOLDER]` text has been replaced with actual content
- [ ] Perspective navigation IDs match section headings (e.g., `#section1` → `id="section1"`)
- [ ] All links are working and point to correct URLs
- [ ] Read time is realistic (calculate word count ÷ 225)
- [ ] Category matches content appropriately (POLITICS, BUSINESS, WORLD, etc.)

**Image and Media:**
- [ ] Featured image loads properly with appropriate alt text
- [ ] Local images are downloaded and all references updated (featured image, Open Graph, Twitter Card)
- [ ] Image captions are descriptive and relevant
- [ ] Image credit section includes photographer attribution

**Technical Verification:**
- [ ] **NO `<style>` tags exist anywhere in the HTML file**
- [ ] External CSS link `<link rel="stylesheet" href="styles.css">` is present
- [ ] Back button `<a href="index.html" class="back-to-home">← Back to Home</a>` exists
- [ ] Facebook SDK appears only once in `<body>` section
- [ ] All 5 social sharing buttons are present (Facebook, Twitter, LinkedIn, Email, Copy)

**Content Quality:**
- [ ] Sources are properly formatted and linked
- [ ] Bias rating is included with explanation
- [ ] Quote blocks use proper attribution format
- [ ] Multiple perspectives are represented in content

**Meta Data:**
- [ ] Page title follows format: `[ARTICLE TITLE] - The Center Wire`
- [ ] Open Graph tags completed with actual URLs and descriptions
- [ ] Twitter Card meta tags match Open Graph data
- [ ] SEO keywords are relevant and comprehensive
- [ ] Facebook Comments URL matches article URL exactly

#### Step 12: Integration with Homepage
1. **Add the new article to index.html**:
   - Replace one of the placeholder news cards
   - Update the card image, title, summary, and link
   - Ensure the link points to your new HTML file
   - Add appropriate read time and perspectives

#### Step 13: Update Featured Article on Homepage
**⚠️ IMPORTANT: Work from bottom to top to avoid losing content!**

**Primary Approach: Chronological Shift (Recommended)**
This maintains proper content hierarchy with newest articles at top-left, aging out to bottom-right.

1. **Remove the oldest article** (Article 9):
   - from index.html: delete the entire last `news-card` article to make space
   - This article "ages out" of the homepage
   - Move the physical file to OlderNews Folder.  Be sure to include any local images if present into the OlderNews Folder.
   - update arhive-list.txt to list every file in OlderNews directory in date descending order so the newest files are at the top and the oldest files are at the bottom.  This file is a simple text file that lists all files in OlderNews directory in the following format: <filename>|Month day, year|Headline

   ex:
      texas-floods-camp-mystic-tragedy.html|July 9, 2025|Devastating Texas Floods Leave 160+ Missing, 100+ Dead
      trump-withdraws-national-guard-los-angeles.html|July 16, 2025|Trump Administration Orders Withdrawal of 2,000 National Guard Troops from Los Angeles

   

2. **Shift all articles down/right** (work backwards to avoid overwrites):
   - **Article 8 → Article 9 position**: Move 8th news card to 9th position
   - **Article 7 → Article 8 position**: Move 7th news card to 8th position
   - **Article 6 → Article 7 position**: Move 6th news card to 7th position
   - **Article 5 → Article 6 position**: Move 5th news card to 6th position
   - **Article 4 → Article 5 position**: Move 4th news card to 5th position  
   - **Article 3 → Article 4 position**: Move 3rd news card to 4th position
   - **Article 2 → Article 3 position**: Move 2nd news card to 3rd position
   - **Article 1 → Article 2 position**: Move 1st news card to 2nd position
   - **Featured → Article 1 position**: Convert current featured article to news card format

3. **Convert current featured article to news card**:
   - Copy information from the `featured-article` section
   - Format as news card and place in Article 1 position:
     ```html
     <article class="news-card">
         <div class="card-image">
             <a href="[CURRENT_FEATURED_ARTICLE].html">
                 <img src="[CURRENT_FEATURED_IMAGE]" alt="[ALT_TEXT]">
             </a>
         </div>
         <div class="card-content">
             <div class="card-meta">
                 <span class="category">[CATEGORY]</span>
                 <span class="date">[DATE]</span>
                 <span class="read-time">[READ_TIME]</span>
             </div>
             <h4 class="card-title"><a href="[ARTICLE_LINK]" style="color: inherit; text-decoration: none;">[TITLE]</a></h4>
             <p class="card-summary">[SUMMARY]</p>
             <div class="card-perspectives">
                 <span class="perspective-tag">[Perspective 1]</span>
                 <span class="perspective-tag">[Perspective 2]</span>
                 <span class="perspective-tag">[Perspective 3]</span>
             </div>
         </div>
     </article>
     ```

4. **Add new article as featured**:
   - Update the `featured-article` section (~line 47-75) with your new article:
     ```html
     <article class="featured-article">
         <div class="article-image">
             <a href="[NEW_ARTICLE].html">
                 <img src="[NEW_FEATURED_IMAGE]" alt="[NEW_ALT_TEXT]">
             </a>
         </div>
         <div class="article-content">
             <div class="article-meta">
                 <span class="category">[NEW_CATEGORY]</span>
                 <span class="date">[NEW_DATE]</span>
                 <span class="read-time">[NEW_READ_TIME]</span>
             </div>
             <h2 class="article-title"><a href="[NEW_ARTICLE].html" style="color: inherit; text-decoration: none;">[NEW_TITLE]</a></h2>
             <p class="article-summary">[NEW_SUMMARY]</p>
             <div class="perspective-links">
                 <a href="[NEW_ARTICLE].html#section1" class="perspective-link conservative">[Perspective 1]</a>
                 <a href="[NEW_ARTICLE].html#section2" class="perspective-link liberal">[Perspective 2]</a>
                 <a href="[NEW_ARTICLE].html#section3" class="perspective-link independent">[Perspective 3]</a>
             </div>
         </div>
     </article>
     ```

5. **Update breaking news banner** (optional):
   - If the new article is breaking news, update the banner (~line 40):
     ```html
     <span class="breaking-text">[NEW_BREAKING_NEWS_HEADLINE]</span>
     ```

**Final Content Flow (newest to oldest)**:
- **Featured**: New article (most prominent display)
- **Article 1**: Previous featured article  
- **Article 2**: Previous Article 1
- **Article 3**: Previous Article 2
- **Article 4**: Previous Article 3
- **Article 5**: Previous Article 4
- **Article 6**: Previous Article 5
- **Article 7**: Previous Article 6
- **Article 8**: Previous Article 7
- **Article 9**: Previous Article 8
- **Removed**: Previous Article 9 (aged out)

6. **Double check your work**
   - Go back and check your work.  Did you do Step 1?  Did you do Step 2?  What about Step 3?  What about Step 4? Step 5?  If anything is wrong, please correct it.
   - double check the sources in your new article and the sources in Generated Content.  Did you use placeholders?  Don't.  Fix it.

### Content Guidelines

#### Writing Style
- **Neutral tone**: Avoid loaded language or emotional appeals
- **Multiple perspectives**: Include viewpoints from different sides
- **Factual basis**: Stick to verifiable information
- **Clear structure**: Use headings to organize different viewpoints

#### Perspective Organization
- **Section 1**: Often factual background or main development
- **Section 2**: First major perspective (e.g., Conservative, Industry, Legal)
- **Section 3**: Opposing or alternative perspective (e.g., Liberal, Environmental, Public)
- **Additional sections** as needed for complex stories

#### Source Requirements
- **Minimum 3 sources** from different perspectives
- **Include mainstream sources** from various political leanings
- **Link to original articles** when possible
- **Use recent sources** (within days/weeks of publication)

### Common Mistakes to Avoid
1. **Adding any `<style>` blocks to HTML files** - Use external styles.css only
2. **Overriding CSS with inline styles** - All styling is pre-defined in styles.css
3. **Duplicating Facebook SDK declarations** - Should only be in `<body>`, not `<head>`
4. **Forgetting to update navigation IDs** - causes broken internal links
5. **Missing perspective in content** - undermines site's mission
6. **Inaccurate read times** - misleads users
7. **Broken source links** - damages credibility
8. **Inconsistent formatting** - looks unprofessional
9. **Missing bias rating explanation** - reduces transparency
10. **Conflicting CSS values between inline styles and external CSS** - creates visual inconsistencies
11. **Missing back button** - `<a href="index.html" class="back-to-home">← Back to Home</a>`
12. **Using placeholder URLs in sources** - Replace all `[URL]` placeholders with actual source links from GeneratedContent.txt
13. **Incorrect bias rating** - Double-check bias assessment against article tone and provide honest explanation
14. **Facebook sharing URL not encoded** - Use `https%3A//thecenterwire.com/...` format for Facebook sharing buttons
15. **Missing Open Graph meta tags** - Include og:image:type, article:published_time, article:author, article:section for proper social media sharing
16. **Not testing social sharing URLs** - Verify Facebook and Twitter sharing links work before considering article complete
17. **Facebook sharing cache issues** - If Facebook shows "404 page not found" when sharing, use Facebook's Sharing Debugger (https://developers.facebook.com/tools/debug/) to force refresh the page cache

### File Naming Convention
- Use descriptive keywords from the headline
- Keep under 50 characters when possible
- Use hyphens instead of spaces
- Avoid special characters or numbers unless necessary
- Examples:
  - `climate-summit-reaches-agreement.html`
  - `tech-regulation-bipartisan-support.html`
  - `economic-policy-market-response.html`

### CSS Troubleshooting Guide
**If styling looks broken after article creation:**

1. **Check for `<style>` blocks**: Search the HTML file for `<style>` tags and remove them completely
2. **Verify external CSS link**: Ensure `<link rel="stylesheet" href="styles.css">` is present in `<head>`
3. **Compare with reference article**: Use `fbi-epstein-video-three-minutes-missing.html` as structural template
4. **Check back button**: Ensure `<a href="index.html" class="back-to-home">← Back to Home</a>` exists after `<div class="article-page">`
5. **Validate HTML structure**: Main content should follow this pattern:
   ```html
   <main class="main">
       <div class="container">
           <div class="article-page">
               <a href="index.html" class="back-to-home">← Back to Home</a>
               <div class="article-header">
   ```
6. **Test social sharing**: All 5 buttons should display correctly (Facebook, Twitter, LinkedIn, Email, Copy)

**Common fixes:**
- Page too wide → Check `.article-page` isn't being overridden with custom padding
- Missing back button → Add `<a href="index.html" class="back-to-home">← Back to Home</a>`
- Wrong background color → Remove any inline background-color styles
- Social buttons mispositioned → Remove any inline social sharing styles

