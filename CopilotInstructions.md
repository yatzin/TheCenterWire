# The Center Wire Static HTML Website

## AI Instructions: Creating New Articles from Generated Content

### Overview
Use these step-by-step instructions to convert generated news content into a properly formatted HTML article for The Center Wire website using the template.html file.

### Prerequisites
- Access to template.html file
- Generated content with article text, sources, and metadata
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
   - **Social media summary** (2-3 sentences for Facebook/Twitter sharing)
   - **SEO keywords** (relevant topics, people, places for search optimization)
   - **Image dimensions** (width and height for optimal social media display)

#### Step 2: Copy Template File
1. **Create a new file** by copying `template.html`
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
   <!-- Replace [ARTICLE_URL] with full URL to article -->
   <!-- Replace [ARTICLE_TITLE] with the article headline -->
   ```
   - Replace `[ARTICLE_URL]` with `https://thecenterwire.com/[FILENAME].html`
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

#### Step 11: Final Review Checklist
- [ ] All `[PLACEHOLDER]` text has been replaced
- [ ] Perspective navigation IDs match section headings
- [ ] All links are working and accurate
- [ ] Images load properly with appropriate alt text
- [ ] Sources are properly formatted and linked
- [ ] Bias rating is included and explained
- [ ] Read time is realistic (calculate word count ÷ 225)
- [ ] Category matches content appropriately

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

1. **Remove the oldest article** (Article 6):
   - Delete the entire last `news-card` article to make space
   - This article "ages out" of the homepage

2. **Shift all articles down/right** (work backwards to avoid overwrites):
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
- **Removed**: Previous Article 6 (aged out)

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
1. **Forgetting to update navigation IDs** - causes broken internal links
2. **Missing perspective in content** - undermines site's mission
3. **Inaccurate read times** - misleads users
4. **Broken source links** - damages credibility
5. **Inconsistent formatting** - looks unprofessional
6. **Missing bias rating explanation** - reduces transparency

### File Naming Convention
- Use descriptive keywords from the headline
- Keep under 50 characters when possible
- Use hyphens instead of spaces
- Avoid special characters or numbers unless necessary
- Examples:
  - `climate-summit-reaches-agreement.html`
  - `tech-regulation-bipartisan-support.html`
  - `economic-policy-market-response.html`

