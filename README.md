# Marketing Landing Page Template 
##### v1.2 (January 2017)

The new marketing landing page template (MLP)[put link to github here] is based off of the [Eventbrite Design System (EDS)](https://admin.eventbrite.com/admin/eds/). MLP uses the EDS grid, color system, and spacing. There are two reasons we have separate styles for MLP: 1. EDS was not fully built at the time of MLP creation 2. Due to the more expressive nature of marketing projects there is a need for a wider range of ways to express marketing content from landing pages to marketing microsites. This is the code base for that expression.

This documentation is therefore a description of the extra marketing CSS classes that exist and how to use them. Beside the creation of a few new structures, the majority of html is EDS and will be maintained and found in the EDS system.

This project is a living, breathing guide. If you would like to contribute changes to either html or css, please bring them up in our weekly development meeting or make a fork on GitHub. [link to github here]. Also feel free to ask any other questions or submit bugs to [kmartin@eventbrite.com](mailto:kmartin@eventbrite.com).

## Getting Started
Download the MLP template here [ link to github here]. Save this template in the code section of your Jira Folder. Next create a new test page for your project in the admin section of evbqa.com. Here is the path: evbqa.com > log in > user dropdown menu > admin > marketing > landing pages > create landing page.  This is the place where you will copy-paste your updated MLP template code and view your new marketing page. 

The goal is to keep this code as clean as possible, this includes adding the minimal amount of CSS to the style tag of this document. The ideal amount of css would be background images that are unique to this page. If you find yourself constantly adding CSS and think it should be global on marketing pages then we should add this to core.

## Visual Reference of Modules
For a visual reference of all the modules you can go [here](https://www.eventbrite.com/l/brandcomm-master-template/).

For the master template code you can go [here](
https://github.com/eventbrite/BrandComm/blob/master/templates/master-template.html).

## Glossary of terms

| Term | Meaning |
|------|---------|
| EDS | Eventbrite Design System |
| MLP |  Marketing Landing Page |

## Utilities
- [Color](#color)
- [Grid](#grid)
- [Alignment](#alignment)
- [Icons](#icons)
- [Spacing](#spacing) 
- [Typography](#typography)

## Components
- [Buttons](#buttons)
- [Links](#links)
- [Header & Footer images](#header)
- [Form & Header box overlap](#forms)
- [Cards](#cards)
- [Masonry layouts](#masonry)
- [Background color with overlap](#background)

## Color
Color documentation is in EDS and can be found [here](https://admin.eventbrite.com/admin/eds/color).

##### Grey Gradient Background Color
Use `.mktg-bg-gradient--grey-100` for the grey-100 to grey-200 background gradient. This can be used to differentiate section backgrounds when you need the cards to be light grey still and not just white.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/grey-gradient.png "Grey Gradient")

<br>
## Grid <a id="grid"></a>
Grid documentation is in EDS and can be found [here](https://admin.eventbrite.com/admin/eds/grid). The new EDS grid is 100% width with no fixed container. If you don't want your content to span the entire width of the page I would suggest wrapping it in a div that is 10 out of 12 columns.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/grid.png "Full width grid")

<br>
##### Constraining the grid
For very reserved cases, like forms or blog articles, use `.mktg-grid-container` which creates a container with a max width of 1200px. 


![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/grid-container.png "Grid container")

```
<section class="eds-bg-color--grey-100 mktg-l-pad-vert-60">
	<div class="mktg-grid-container">
		<div class="eds-g-cell eds-g-cell-12-12 eds-g-offset-0-12 eds-g-cell-sw-10-12 eds-g-offset-sw-1-12 eds-g-cell-md-8-12 eds-g-offset-md-2-12">
			<div class="eds-g-grid">
				<div class="eds-g-group eds-l-pad-hor-3">
					<p class="eds-text-bl eds-text-color--grey-900">Paragraph 1 text....</p>
					<div class="eds-l-pad-top-6">
						<p class="eds-text-bl eds-text-color--grey-900">Paragraph 2 text...</p>
					</div>
				</div>
			</div>
		</div>
	</div>	
</section>
```

<br>
## Alignment
Base alignment can be found in EDS [here](https://admin.eventbrite.com/admin/eds/helpers) but we have additional flexbox alignment for the MLP. Marketing alignment classes use [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) to align left, right, bleed and stacked. In the small tablet and mobile view, content is always stacked.

<br>
##### Left alignment
Use `mktg-layout-align--left` for an image on the left and text on the right.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/align-left.png "Flexbox left align")

```
<div class="mktg-layout-align--left mktg-l-pad-vert-80 eds-g-cell-10-12 eds-g-offset-1-12">
    <div class="l-align-center eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/event_page_android.png" class="g-img mktg-img hide-small">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/event_page_android_mobile.png" class="g-img mktg-img show-small">
    </div>
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-sm-mar-top-6 eds-l-mn-mar-left-6 eds-l-md-mar-left-6 eds-l-sw-mar-left-6">
        <h3 class="eds-text-hm eds-text-color--grey-900">Simplify your planning and set yourself up for success.</h3>
        <div class="eds-l-mar-top-6">
            <p class="eds-text-bl eds-text-color--grey-700"><span class="mktg-text-medium">Delight your guests</span> with a simple purchase flow and gorgeous event pages that look great on any device.</p>
        </div> 
    </div>
</div>
```
<br>
##### Right alignment
Use `mktg-layout-align--right` for an image on the right and text on the left.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/align-right.png "Flexbox right align")

```
<div class="mktg-layout-align--right mktg-l-pad-vert-80 eds-g-cell-10-12 eds-g-offset-1-12 l-section">
    <div class="l-align-center eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-mn-mar-left-6 eds-l-md-mar-left-6 eds-l-sw-mar-left-6">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/facebook_purchase_iphone.png" class="g-img mktg-img hide-small">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/facebook_purchase_iphone_mobile.png" class="g-img mktg-img show-small">
    </div>
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-sm-mar-top-6">
        <h3 class="eds-text-hm eds-text-color--grey-900">Grow your event every year.</h3>
        <div class="eds-l-mar-top-6">
            <p class="eds-text-bl eds-text-color--grey-700"><span class="mktg-text-medium">Reach new audiences</span> by tapping Eventbrite’s 75 million active  ticket buyers.</p>
        </div>
    </div>
</div>
```
<br>
##### Center alignment
Use `mktg-layout-align--center` for text on the top and an image on the bottom.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/align-center.png "Flexbox center align")

```
<div class="mktg-layout-align--center mktg-l-pad-vert-80 eds-g-cell-10-12 eds-g-offset-1-12">
    <div class="l-align-center eds-g-cell-1-1 eds-l-md-mar-top-6 mktg-l-md-pad-top-60">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/organizerApp.png" class="g-img mktg-img">
    </div>
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-l-sm-mar-top-6 eds-text--center eds-l-mn-mar-bot-6 eds-l-md-mar-bot-6 eds-l-sw-mar-bot-6">
        <h3 class="eds-text-hm eds-text-color--grey-800">Header text</h3>
        <div class="eds-l-mar-top-6">
            <p class="eds-text-bl eds-text-color--grey-600">Paragraph 1 text</p>
        </div>
    </div>
</div>
```

<br>
##### Left bleed
Use `mktg-layout-align--bleed--left` for an image that bleeds off the left side and text on the right.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/bleed-left.png "Flexbox bleed left align")

```
<div class="mktg-layout-align--bleed--left mktg-l-block--padded-v-80 eds-g-cell-10-12 eds-g-offset-1-12 eds-g-cell-sw-12-12 eds-g-offset-sw-0-12">
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/eb_music_microsite/product_1_desktop.png" class="g-img mktg-img-bleed eds-hide-sm eds-hide-sn">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/eb_music_microsite/product_1_mobile.png" class="g-img mktg-img eds-hide-sw eds-hide-mn eds-hide-md eds-hide-mw eds-hide-ln eds-hide-lg eds-hide-lw">
    </div>
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-sn-mar-top-6 eds-l-sm-mar-top-6 eds-g-offset-md-1-12 eds-l-md-pad-right-6 eds-l-mw-pad-right-6 eds-l-ln-pad-right-6 eds-l-lg-pad-right-6 eds-l-lw-pad-right-6">
        <div class="eds-l-sw-mar-hor-6 eds-l-mn-mar-hor-6 eds-l-md-mar-right-6 eds-l-mw-mar-right-6 eds-l-ln-mar-right-6 eds-l-lg-mar-right-6 eds-l-lw-mar-right-6">
            <h3 class="eds-text-hm eds-text-color--grey-900">Simplify operations to scale your festival</h3>
            <div class="eds-l-mar-top-6">
                <p class="eds-text-bl eds-text-color--grey-700">Streamline your box office and gates with the battle-tested speed and offline reliability of Eventbrite Organizer and Eventbrite's RFID technology</p>
            </div>
        </div>
    </div>
</div>

```


<br>
##### Right bleed
Use `mktg-layout-align--bleed--right` for an image that bleeds off the right side and text on the right.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/bleed-right.png "Flexbox bleed left align")

```
<div class="mktg-layout-align--bleed--right mktg-l-block--padded-v-80 eds-g-cell-10-12 eds-g-offset-1-12 eds-g-cell-sw-12-12 eds-g-offset-sw-0-12">
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/eb_music_microsite/resources_card_8.jpeg" class="g-img mktg-img-bleed eds-hide-sm eds-hide-sn">
        <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/eb_music_microsite/resources_card_8.jpeg" class="g-img mktg-img eds-hide-sw eds-hide-mn eds-hide-md eds-hide-mw eds-hide-ln eds-hide-lg eds-hide-lw">
    </div>
    <div class="eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-sn-mar-top-6 eds-l-sm-mar-top-6 eds-g-offset-md-1-12 eds-l-md-pad-right-6 eds-l-mw-pad-right-6 eds-l-ln-pad-right-6 eds-l-lg-pad-right-6 eds-l-lw-pad-right-6">
        <div class="eds-l-sw-mar-hor-6 eds-l-mn-mar-hor-6 eds-l-md-mar-right-6 eds-l-mw-mar-right-6 eds-l-ln-mar-right-6 eds-l-lg-mar-right-6 eds-l-lw-mar-right-6">
            <h3 class="eds-text-hm eds-text-color--white">Simplify operations to scale your festival</h3>
                <div class="eds-l-mar-top-6">
                    <p class="eds-text-bl eds-text-color--white">Streamline your box office and gates with the battle-tested speed and offline reliability of Eventbrite Organizer and Eventbrite's RFID technology</p>
                </div>
        </div>
    </div>
</div>
```

<br>
## Icons
Icons are in progress. Right now we are using individual SVG icons with PNG backups. Once we finish our icon style, we will upload all the marketing icons to one folder on s3 and follow the same naming convention. That way it'll be easy for designers and coders to use and reference icons. The folder that we store all the marketing icons is in Amazon s3 and the path is: eventbrite-s3/marketing/landingpage/mlp-icons.

<br>
## Spacing
Small increment spacing is based off EDS which can be found [here](https://admin.eventbrite.com/admin/eds/spacing). We have a lot of added spacing however for marketing since we have layouts which require more whitespace. For consistency I've tried to use a similar naming convention to what EDS uses. All of these values become smaller on tablet and mobile.

<br>
##### 80px spacing
| Example | Class |
|------|---------|
| Padding top of 80px | mktg-l-pad-top-80 |
| Padding bottom of 80px |  mktg-l-pad-bot-80 |
| Padding top & bottom of 80px |  mktg-l-pad-vert-80 |

<br>
##### 60px spacing
| Example | Class |
|------|---------|
| Padding top of 60px | mktg-l-pad-top-60 |
| Padding bottom of 60px |  mktg-l-pad-bot-60 |
| Padding top & bottom of 60px |  mktg-l-pad-vert-60 |

<br>
##### 40px spacing
| Example | Class |
|------|---------|
| Padding top of 40px | mktg-l-pad-top-40 |
| Padding bottom of 40px |  mktg-l-pad-bot-40 |
| Padding top & bottom of 40px |  mktg-l-pad-vert-40 |


<br>
## Typography
All of the typography sizes are from EDS and can be found [here](https://admin.eventbrite.com/admin/eds/typography). EDS has weight built into each type class however, so I've written some classes to override in case you want your type to be light or medium.

<br>
##### Light text
Use `mktg-text-light` to override the text weight to light.

<br>
##### Medium text
Use `mktg-text-medium` to override the text weight to medium.

<br>
##### Hanging indent
Use `mktg-hanging-indent` to create a hanging indent for quote block text.

<br>
##### Letter spacing
Use `mktg-letter-spacing` to create letter spacing on small type that is in all caps.

<br>
## Buttons
While our default button color is orange, one should always try to use buttons that have maximum contrast on the page. Try to use the orange button when possible but if it is surrounded by orange, use the deepsea blue button.

<br>
##### Orange button (primary)
Use `mktg-btn` to get our primary, orange button. Always use this button for music.

```
<div class="eds-l-mar-top-6">
    <a class="mktg-btn eds-text--center" href="https://www.eventbrite.com/l/contact-eventbrite-music">Get Started</a>
</div>
```

<br>
##### Dark blue button (secondary)
Use `mktg-btn--deepsea-blue-500` to get our secondary, deepsea blue button.
```
<div class="eds-l-mar-top-6">
    <a class="mktg-btn mktg-btn-block mktg-btn--deepsea-blue-500 eds-text--center" href="https://www.eventbrite.com/l/contact-eventbrite-music">Get Started</a>
</div>
```

<br>
##### Responsive button
Use `mktg-btn-block` to make your button take up 100% width of it's container.
```
<div class="eds-l-mar-top-6">
    <a class="mktg-btn mktg-btn-block eds-text--center" href="https://www.eventbrite.com/l/contact-eventbrite-music">Get Started</a>
</div>
```

<br>
## Links
On standard marketing pages, our primary color is deapsea blue for the most contrast. If there is a link on a color background we have a white link you can use. Finally, for music, we have orange links and white links with orange hover effects.

##### Deapsea blue link (primary)
`a` is our primary, deapsea blue link.
```
<a href="https://www.eventbrite.com/l/contact-eventbrite-music">Get Started</a>
```

<br>
## Header/footer hero images
There are two different heights for marketing hero imagery, regular and small. These images are also set to cover the entire background so make sure you are cropping them no less than 1400px wide for desktop. You should also create a separate tablet/mobile image that is smaller in size and also cropped for portrait. For quality photography, video, and illustration use our standard image height which is taller. For patterns or supercrops which can fit in a smaller window use the small size.

<br>
##### Primary hero image size
Use `mktg-landing-hero-cover` on the header & footer div to get our primary hero size which is 85vh. This div or section does not need any content to be in it to create height since it has a height. This is because it was designed to have the sign up form or header type overlapping. If you want the header and footer to have the same image you can put the image in this class in the css. If you want them to be different, just add a class to the footer container and put the footer image in that class in the css. 

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/hero-primary.png "Hero primary")
```
<section class="mktg-landing-hero-cover"></section>
```

<br>
##### Small hero image size
Use `mktg-landing-hero-cover-small` on the header or footer div to get our smaller hero size. This is 55vh.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/hero-small.png "Hero small")

<br>
##### Background image cover
The two classes above are already set to have the image cover the whole background. Use `mktg-img-cover` on a div that you want an image to cover the background that is not one of the above classes.

<br>
## Form & Header box overlap
The following classes create solid white to white opaque box backgrounds that will overlap either the header or footer image. These boxes then can either contain a sign up form or header text and button depending on what marketing wants.

<br>
##### Header box overlap 
Use `mktg-form-bg` to create a white to opaque white box (bottom to top) that will overlap the image above it. The code below will create this white overlap box and also contains a signup form.
```
<div class="eds-g-cell-10-12 eds-g-offset-1-12 mktg-form-bg">
	<div class="mktg-form-inner">
	    <div class="eds-l-pad-hor-2 eds-l-mar-bot-6">
	        <h2 class="eds-text-hs eds-text--center">Sign up for free to create your first event.</h2>
	    </div>
	    <form name="signupForm" method="post" action="/signup?nomo=1" class="mktg-responsive-form responsive-form js-validate-signup">
	    <!-- Hidden input fields... signup_page value is page specific -->
	        <input type="hidden" name="signup_page" value="us_music">
	        <input type="hidden" name="submitted" value="1">
	        <input type="hidden" name="forward" value="/create">
	    <!-- END: Hidden input fields... signup_page value is page specific -->
	        <div class="eds-g-cell eds-g-cell-1-1 eds-g-cell-ln-1-3 eds-g-cell-lg-1-3 eds-l-mar-top-3 eds-l-pad-hor-1">
	            <input type="email" name="email" placeholder="Email" class="eds-textinput__input" />
	        </div>
	        <div class="eds-g-cell eds-g-cell-1-1 eds-g-cell-ln-1-3 eds-g-cell-lg-1-3 eds-l-mar-top-3 eds-l-pad-hor-1">
	            <input type="password" name="passwd1" placeholder="Password" class="eds-textinput__input" />
	        </div>
	        <div class="eds-g-cell eds-g-cell-1-1 eds-g-cell-ln-1-3 eds-g-cell-lg-1-3 eds-l-mar-top-3 eds-l-pad-hor-1">
	            <input type="submit" class="mktg-btn mktg-btn-block" value="Get started">
	        </div>   
	    </form>
	    <div class="eds-l-mar-top-2 eds-l-pad-hor-2">
	        <p class="eds-text-bs">By clicking 'Get Started', I confirm that I agree with the Eventbrite <a href="/tos/" class="">terms of service</a>, <a href="/privacypolicy/" class="">privacy policy</a>, and <a href="/cookies/" class="">cookie policy</a>.</p>
	</div>
</div>
```

`mktg-form-inner` creates inner padding specifically to pad the form above. 

`mktg-responsive-form` is also specifically for the form above. It forces the form fields and button into a row on desktop and column on tablet and mobile. 

<br>
##### Footer box overlap 
Use `mktg-form-footer-bg` to create a white to opaque white box that will overlap the image below it. The different between this class and the one above is that this box will go downward and the white to opaque gradient goes from top to bottom.

<br>
## Cards
Below are classes for the different marketing cards. There are a few different styles in order to differentiation the various types of marketing content. The cards can be various sizes, from one large card, 2 across or 3 across. Just use the grid classes in the html to set these sizes. I would suggest on desktop and below however, to not use 4 cards across or more due to poor type breaks.

<br>
##### Customer quote card
Use `mktg-quote-card` to create a standard card for just logo and type. This will give the box a slight shadow and hover effect. The background color of this card is not specified here but must be specified in the html. This was done in order to give the designer flexibility in case they need to use the card on dark backgrounds for music.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/quote-card.png "Quote card")

```
<div class="mktg-quote-card eds-bg-color--white">
    <a href="https://www.eventbrite.com/blog/academy/whole-foods-market-and-eventbrite/" target="_blank">
        <div class="eds-l-pad-all-6">
            <div class="mktg-quote-card_logo eds-l-pad-bot-6">
                <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/whole_foods_logo.svg" onerror="this.src='https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/whole_foods_logo.png';this.onerror=null;" class="mktg-org-logo-w">
            </div>
	        <div class="eds-l-mar-vert-6">
	            <p class="eds-text-bm eds-text-color--grey-900">“Eventbrite cut down check-in time by about 66%. There are no lines at the door and nobody is frustrated.”</p>
	            <div class="eds-l-mar-top-2">
	                <p class="eds-text-bs eds-text-color--grey-900"><span class="mktg-text-medium text-stressed">— Gabriella Graceffa-Bunker,</span> EA to the President of Whole Foods NA</p>
	            </div>
	        </div>
	        <div class="mktg-icon-link">
	            <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/quote_icon.svg" onerror="this.src='https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/quote_icon.png';this.onerror=null;" class="eds-l-mar-right-2">
	            <p class="eds-text-bm">Read the Whole Foods case study</p>
	        </div>
        </div>  
    </a>
</div>   
```

`mktg-quote-card_logo` creates a small grey line under the logo. 

`mktg-org-logo-w` constrains wide logos to max-width 80px.

`mktg-org-logo-t` constrains tall logos to max-height 50px.

`mktg-icon-link` horizontally aligns the small quote icon with the link text.

<br>
##### Video card
Use `mktg-video-card` paired up with the quote card classes to create a video card. This card follows the same design as the quote card with the addition of an image on the top with a play button in it. The body content can be modified to include whatever is appropriate, wheather a customer quote or just a short video description. Upon clicking the play button, a video will play in our lightbox on the page. 

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/video-card.png "Video card")

```
<div class="mktg-video-card mktg-quote-card">
    <a href="https://www.youtube.com/watch?v=sCJjs6Vnikc" target="_blank" class="js-d-modal" data-d-modal-options='{"disableOn": 700, "type": "iframe", "mainClass": "mfp-fade", "removalDelay": 160, "preloader": false, "fixedContentPos": false}'>
        <div class="mktg-video-card__header">
            <div class="mktg-video-card__image baconandbeer_vido-card">
                <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/play_large_icon.svg" class="">   
            </div>
        </div>
        <div class="eds-l-pad-all-6 eds-bg-color--white">
            <div class="mktg-quote-card_logo eds-l-pad-bot-6">
                <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/baconandbeer_logo.png">
        	</div>
        	<div class="eds-l-mar-vert-6">
            	<p class="eds-text-bm eds-text-color--grey-900">“Eventbrite has helped us so much...they really seem to care about our company and the success of it.”</p>
        		<div class="eds-l-mar-top-2">
                	<p class="eds-text-bs eds-text-color--grey-900"><span class="mktg-text-medium text-stressed">— Kate Levenstien,</span> founder and CEO of Cannonball Productions</p>
            	</div>
        	</div>
        	<div class="mktg-icon-link">
            	<img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/play_icon_sm.svg" onerror="this.src='https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlpTemplate/play_icon_sm.png';this.onerror=null;" class="eds-l-mar-right-2">
            	<p class="eds-text-bm">Watch the video</p>
        	</div>
        </div>
    </a>
</div> 
```

`mktg-video-card__header` creates the height for the image to appear. 

`mktg-video-card__image` positions the image and makes it cover 100% of the div. This is also the container you should create a class in order to place your image in the css. 


<br>
##### Overlap card
Use `mktg-context-card` to create an overlap card. This card has a top with an image, illustration or icon in it and then a description box that overlaps it. The code below will create an overlap card with an icon in the top. 

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/overlap-card.png "Overlap card")

```
<div class="eds-g-cell eds-g-cell--has-overflow eds-g-cell-1-1 eds-g-cell-md-1-2 eds-g-cell-lg-1-2 eds-l-pad-all-3">
    <div class="mktg-context-card eds-text--center">
        <div class="mktg-context-card__header eds-bg-color--grey-200">
            <div class="mktg-context-card__image">
                <img src="https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mktg-icons/mktg-icon--headset-o-lg.svg" onerror="this.src='https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mktg-icons/mktg-icon--headset-o-lg.png';this.onerror=null;" class="mktg-context-img">   
            </div>
        </div>
        <div class="eds-bg-color--white mktg-context-card_body match-height2">
            <p class="eds-text-bl eds-text-color--grey-800 mktg-text-medium">Get in touch</p>
            <div class="eds-l-mar-vert-6">
                <p class="eds-text-bl eds-text-color--grey-600">Hosting a large or complex event? Schedule a chat with one of our seasoned event experts.</p>
            </div>
            <div class="eds-text--center">
                <p class="eds-text-bl"><a href="https://www.eventbrite.com/blog/academy/contact-eventbrite/?ref=mlp" target="_blank">Contact Sales</a></p>
            </div>
        </div>
    </div>
</div>
```

`mktg-context-card__header` creates the height for the image to appear.

`mktg-context-card__image` positions the image and makes it cover 100% of the div. This is also the container you should create a class in order to place your image in the css.  

`mktg-context-card_body` creates a box that will overlap the top box. It also will have a slight shadow appear on hover.

`mktg-context-img` this class should only be used if there is an icon in the top box. It makes that icon 25% of the width of the box.

<br>
## Masonry layouts
These are styles for creating a Pinterest style masonry layout with cards so that they can be different heights with no big gaps. We have sizing for 2 and 3 across. These styles do not work on very old browsers including Explorer 8 and before. For a fully populated code example, see the masonry layout in the example page.

<br>
##### Masonry layout 3 across
Use `mktg-masonry-container` to create the basic outer shell for any masonry layout whether 2 or 3 across. For 3 across add `mktg-masonry-inner-container-3` to specify you want 3 divs across. Last, each item in your masonry layout needs to have `mktg-masonry-item` on it.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/masonry-3.png "Masonry 3")

```
<div class="eds-g-group eds-l-pad-top-6 mktg-masonry-container">
    <ul class="mktg-masonry-inner-container-3">
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
    </ul>
</div>
```

<br>
##### Masonry layout 2 across
Use `mktg-masonry-container` to create the basic outer shell for any masonry layout whether 2 or 3 across. For 3 across add `mktg-masonry-inner-container-2` to specify you want 3 divs across. Last, each item in your masonry layout needs to have `mktg-masonry-item` on it.

```
<div class="eds-g-group eds-l-pad-top-6 mktg-masonry-container">
    <ul class="mktg-masonry-inner-container-2">
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
        <li class="mktg-masonry-item eds-l-pad-vert-3">
        </li>
    </ul>
</div>
```

<br>
##### Grid layout
Use these classes for the individual squares along with the vertical group classes in [EDS](https://admin.eventbrite.com/admin/eds/grid) to create this square grid layout. This layout was specifically designed for partner apps but I could see being used creatively for any content we might want in this grid. Each square should have it's own class name for the background image that appears in the css. This particular example makes each square link out to the company page but feel free to remove this if you don't want that functionality.

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/square-grid.png "Square layout")

```
<div class="eds-g-grid">
    <div class="eds-g-group eds-l-pad-top-6 eds-l-md-pad-right-2 eds-l-mw-pad-right-2 eds-l-ln-pad-right-2 eds-l-lg-pad-right-2">
        <div class="eds-g-cell eds-vertical-group eds-g-cell-8-12 eds-g-cell-sw-4-12 eds-l-pad-hor-2">
            <div class="eds-g-cell-8-8 eds-g-cell-sw-4-4 mktg-square-large eds-l-mar-top-2 eds-l-mar-bottom-2">
                <a href="https://www.eventbrite.com/spectrum/zapier/" target="_blank">
                    <div class="mktg-app-bg-7 mktg-square-inner"></div> 
                </a>  
        	</div>   
        </div>
        <div class="eds-g-cell eds-vertical-group eds-g-cell-4-12 eds-g-cell-sw-2-12 eds-l-pad-hor-2">
            <div class="eds-g-cell-4-4 eds-g-cell-sw-2-2 mktg-square-small-top eds-l-mar-top-2 eds-l-mar-bottom-2">
                <a href="https://www.eventbrite.com/spectrum/dandelion/" target="_blank">
                    <div class="mktg-app-bg-8 mktg-square-inner"></div> 
                </a>   
            </div>
        	<div class="eds-g-cell-4-4 eds-g-cell-sw-2-2 mktg-square-large eds-l-mar-top-2 eds-l-mar-bottom-2">
            	<a href="https://www.eventbrite.com/spectrum/emma/" target="_blank">
                	<div class="mktg-app-bg-9 mktg-square-inner"></div> 
                </a>   
            </div>    
        </div>
        <div class="eds-g-cell eds-vertical-group eds-g-cell-8-12 eds-g-cell-sw-4-12 eds-l-sm-pad-top-2 eds-l-pad-hor-2">
            <div class="eds-g-cell-8-8 eds-g-cell-sw-4-4 mktg-square-large mktg-l-sn-moz-mar-top-4 eds-l-sn-mar-top-4 eds-l-sm-mar-top-3 eds-l-sw-mar-top-2 eds-l-mn-mar-top-2 eds-l-md-mar-top-2 eds-l-mw-mar-top-2 eds-l-ln-mar-top-2 eds-l-lg-mar-top-2 eds-l-lw-mar-top-2 eds-l-mar-bottom-2">
                <a href="https://www.eventbrite.com/spectrum/doubledutch/" target="_blank">
                    <div class="mktg-app-bg-10 mktg-square-inner"></div> 
                </a>  
            </div>   
        </div>
        <div class="eds-g-cell eds-vertical-group eds-g-cell-4-12 eds-g-cell-sw-2-12 eds-l-sm-pad-top-2 eds-l-pad-hor-2">
            <div class="eds-g-cell-4-4 eds-g-cell-sw-2-2 mktg-square-small-top mktg-l-sn-moz-mar-top-4 eds-l-sn-mar-top-4 eds-l-sm-mar-top-3 eds-l-sw-mar-top-2 eds-l-mn-mar-top-2 eds-l-md-mar-top-2 eds-l-mw-mar-top-2 eds-l-ln-mar-top-2 eds-l-lg-mar-top-2 eds-l-lw-mar-top-2 eds-l-mar-bottom-2">
                <a href="https://www.eventbrite.com/spectrum/sessions/" target="_blank">
                    <div class="mktg-app-bg-11 mktg-square-inner"></div> 
                </a>  
            </div>
            <div class="eds-g-cell-4-4 eds-g-cell-sw-2-2 mktg-square-large eds-l-mar-top-2 eds-l-mar-bottom-2">
                <a href="https://www.eventbrite.com/spectrum/teespring/" target="_blank">
                    <div class="mktg-app-bg-12 mktg-square-inner"></div> 
                </a>   
            </div>    
        </div>             
    </div>
</div>
```

`mktg-square-large` creates the square shape. 

`mktg-square-small-top` creates space between the two small squares. 

`mktg-square-inner` makes the image cover the square and centers it. This is also the div you should create your individual class name for placing the image in css.

<br>
## Background color with overlap
This code creates a div with a background color that is placed behind content that slides off of it on the bottom. This code needs 2 pieces to work. It needs `mktg-bg-overlap--outer` on the outside container and then it needs a closed div right after that with `mktg-bg-overlap--bot` and whatever background color you want the div to be. After the closed div, you can code your content that will overlap the box.  

![alt text](https://s3.amazonaws.com/eventbrite-s3/marketing/landingpages/mlp_documentation/bg-overlap.png "Background overlap")

```
<section class="mktg-l-pad-top-80 eds-bg-color--grey-100 mktg-bg-overlap--outer">
    <div class="eds-bg-color--sunrise-orange-gradient mktg-bg-overlap--bot"></div>
</section>
```

`mktg-bg-overlap--outer` creates an absolutely positioned container for your color background.

`mktg-bg-overlap--bot` creates the hieght for your box and absolutely positions it behind your content.  


