/* ==UserStyle==
@name Sequoia
@namespace github.com/Sequoia-Theme/youtube
@homepageURL github.com/Sequoia-Theme/youtube
@version 0.1
@updateURL #
@description Black, elegant, modern and gentle theme for VS Code.
@license MIT

@preprocessor stylus

@var select stylus-deepdark-style "Preset themes" [
	"Moonlight",
	"Monochrome",

]

@var select mainColorDark "Choose Dark accent color" [
	"Stone",
	"Metal",
	"Orange",
	"Pink",
	"Indigo",
	"Blue",
]

@var select mainColorDawn "Choose Serendipity accent color" [
	"Stone",
	"Metal",
	"Orange",
	"Pink",
	"Indigo",
	"Blue",
]
@var checkbox join-color "Use dark join button" 0
@var checkbox subscribe-color "Use dark subscribe button" 0

@var text scrollbar_width "Scrollbar width" 8px
@var color scrollbar_track "Scrollbar background" "rgba(0,0,0, 0)"

==/UserStyle== */

@-moz-document regexp('https?:\\/\\/(?!gaming\\.)(?!music\\.)(?!tv\\.)(?!artists\\.)(?!studio\\.).*youtube(?!kids\\.).*\\.com\\/(?!premium|howyoutubeworks).*$') {
	/* Author     : Theme made by artilate*/
	/* Co-authors : null */
	/* Home       : https://github.com/artilate/youtube */
	/* Licence    : GNU General Public License v3.0 */

	/*Main color variables*/
	:root
	{
		if stylus-deepdark-style == "Monochrome" {
			if mainColorDark == "Metal" {
				--main-color: #E2E4ED;
			}
			else if mainColorDark == "Stone" {
				--main-color: #D3D5DE;
			}
			else if mainColorDark == "Orange" {
				--main-color: #B6BAC8;
			}
			else if mainColorDark == "Pink" {
				--main-color: #999EB2;
			}
			else if mainColorDark == "Indigo" {
				--main-color: #7C829D;
			}
			else if mainColorDark == "Blue" {
				--main-color: #626983;
			}
			--main-background: #111216;
			--second-background: #111216;
			--hover-background: #131317;
			--main-text: #868690;
			--dimmer-text: #575861;
			--shadow: 0 1px 0.5px rgb(0, 0, 0, .13)
		}

		else if stylus-deepdark-style == "Moonlight" {
			if mainColorDawn == "Metal" {
				--main-color: #fdfdfe;
			}
			else if mainColorDawn == "Stone" {
				--main-color: #9898a6;
			}
			else if mainColorDawn == "Orange" {
				--main-color: #ffbb88;
			}
			else if mainColorDawn == "Pink" {
				--main-color: #f58ee0;
			}
			else if mainColorDawn == "Indigo" {
				--main-color: #c58fff;
			}
			else if mainColorDawn == "Blue" {
				--main-color: #8eb6f5;
			}
			--main-background: #111216;
			--second-background: #111216;
			--hover-background: #131317;
			--main-text: #868690;
			--dimmer-text: #575861;
			--shadow: 0 1px 0.5px rgb(0, 0, 0, .13)
		}
	}
	/*Error page*/
	#error-page
	{
		background-color: var(--main-background) !important;
		color: var(--main-text) !important;
	}

	*
	{
		scrollbar-color: var(--main-color) scrollbar_track !important;
		scrollbar-width: thin !important;
		--yt-spec-text-primary: var(--main-text) !important;
		--yt-spec-text-secondary: var(--dimmer-text) !important;
		--paper-spinner-color: var(--dimmer-text) !important;

		--paper-radio-button-unchecked-color: var(--dimmer-text) !important;
		--paper-radio-button-unchecked-background-color: transparent !important;
		--paper-radio-button-checked-color: var(--main-color) !important;
		--paper-radio-button-checked-ink-color:   var(--main-color) !important;
		--paper-radio-button-unchecked-ink-color: var(--main-color) !important;

		--paper-checkbox-unchecked-color: var(--dimmer-text) !important;
		--paper-checkbox-checked-color: var(--main-color) !important;
		--paper-checkbox-checkmark-color: none !important;
		--paper-checkbox-checked-ink-color:   var(--main-color) !important;
		--paper-checkbox-unchecked-ink-color: var(--main-color) !important;
	}
	/*Scrollbar fix for chrome*/
	*:not([hide-scrollbar]) ::-webkit-scrollbar-thumb
	{
		background: var(--main-color) !important;
	}
	*:not([hide-scrollbar]) ::-webkit-scrollbar
	{
		width: scrollbar_width !important;
	}
	/*Scrollbar fix for firefox*/
	::-webkit-scrollbar-track {
		background: scrollbar_track !important;
	}
	::-webkit-scrollbar-thumb {
		background: var(--main-color) !important;
	}

	/*Background for the entire page*/
	html, ytd-browse, ytd-watch, ytd-search, ytd-app, ytd-app[is-watch-page], [class*="ytd-watch-flexy"],
	.style-scope.ytd-page-manager.hide-skeleton,
	.account-container
	{
		background-color: var(--main-background) !important;
	}

	/*Border for the sidemenu*/
	#guide-content.ytd-app
	{
		border-right: 1px solid var(--yt-border-color) !important;
	}

	/*Changed text highlight*/
	::selection
	{
		background: var(--main-color) !important;
		color: var(--main-text) !important;
	}
	::-moz-selection
	{
		background: var(--main-color) !important;
		color: var(--main-text) !important;
	}

	/*Outline for links*/
	a
	{
		outline-color: var(--main-color) !important;
	}
	a:hover
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	/*Outline for comments*/
	#content-text.ytd-comment-renderer
	{
		outline: none !important;
	}

	/*Placeholder image on pages that need an account - such as Subscriptions*/
	ytd-background-promo-renderer .image.ytd-background-promo-renderer,
	ytd-message-renderer yt-icon.ytd-message-renderer
	{
		color: var(--main-text) !important;
	}

	/*Nav bar*/
	ytd-masthead,
	#yt-masthead-container, #masthead-positioner-height-offset /*account page*/
	{
		background-color: var(--second-background) !important;
		border-bottom-color: var(--hover-background) !important;
	}
	yt-icon-button svg {
		fill: var(--dimmer-text) !important;
	}
	yt-icon-button:hover svg
	{
		fill: var(--main-color) !important;
	}
	#logo-icon-container.ytd-topbar-logo-renderer #youtube-paths.ytd-topbar-logo-renderer path.ytd-topbar-logo-renderer
	{
		fill: var(--main-text) !important;
	}
	/*acount settings page*/
	/*logo*/
	.exp-invert-logo.inverted-hdpi #header::before, .exp-invert-logo.inverted-hdpi .ypc-join-family-header .logo, .exp-invert-logo.inverted-hdpi #footer-logo .footer-logo-icon, .exp-invert-logo.inverted-hdpi #yt-masthead #logo-container .logo, .exp-invert-logo.inverted-hdpi #masthead #logo-container, .exp-invert-logo.inverted-hdpi .admin-masthead-logo a, .exp-invert-logo.inverted-hdpi #yt-sidebar-styleguide-logo #logo
	{
		filter: invert(1) grayscale(1);
	}
	/*buttons*/
	#yt-masthead-creation-button
	{
		filter: brightness(220%);
	}
	#yt-masthead-notifications .yt-uix-button-icon-bell
	{
		filter: invert(1) brightness(720%);
	}

	/*YouTube Apps*/
	yt-multi-page-menu-section-renderer.style-scope div ytd-compact-link-renderer a tp-yt-paper-item div yt-icon svg g path[fill="#FF0000"],
	yt-multi-page-menu-section-renderer.style-scope div ytd-compact-link-renderer a tp-yt-paper-item div yt-icon svg g circle[fill="#FF0000"],
	yt-multi-page-menu-section-renderer.style-scope div ytd-compact-link-renderer a tp-yt-paper-item div yt-icon svg g g g path[fill="#F00"]
	{
		fill: var(--main-color) !important;
	}
	/*Upload*/
	ytd-compact-link-renderer.style-scope a paper-item div yt-icon svg g path[fill="#6f6f6f"],
	ytd-compact-link-renderer.style-scope a paper-item div yt-icon svg g path[fill="#f80000"]
	{
		fill: var(--main-color) !important;
	}
	#sections.ytd-multi-page-menu-renderer > .ytd-multi-page-menu-renderer:not(:last-child)
	{
		border-color: var(--hover-background) !important;
	}

	/*Chat in the header*/
	ytd-conversation-switcher-item-renderer
	{
		border-color: var(--hover-background) !important;
	}
	#last-post.ytd-conversation-switcher-item-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*invite friends*/
	#bar.ytd-copy-connection-invite-url-renderer
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	#icon.ytd-copy-connection-invite-url-renderer
	{
		color: var(--main-text) !important;
	}
	/*chat popup*/
	ytd-conversation-section-renderer
	{
		background: var(--second-background) !important;
	}
	#title-bar.ytd-conversation-section-renderer
	{
		border-color: var(--hover-background) !important;
	}
	ytd-conversation-text-item-renderer[justification-style="JUSTIFICATION_START"] #post-text.ytd-conversation-text-item-renderer,
	ytd-conversation-link-item-renderer[justification-style="JUSTIFICATION_START"] #link.ytd-conversation-link-item-renderer,
	#bar.ytd-conversation-link-item-renderer, #thumbnail.ytd-inline-playback-renderer, #video-data.ytd-inline-playback-renderer
	{
		border-color: var(--hover-background) !important;
		background: var(--hover-background) !important;
	}
	#post-text.ytd-conversation-text-item-renderer, textarea.iron-autogrow-textarea
	{
		color: var(--main-text) !important;
	}
	#displayed-text.ytd-conversation-link-item-renderer, #icon.ytd-conversation-link-item-renderer
	{
		color: var(--main-color) !important;
	}
	#metadata.ytd-conversation-metadata-item-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Backgrounds*/
	#like-bar.ytd-sentiment-bar-renderer,#progress.ytd-thumbnail-overlay-resume-playback-renderer,#selectionBar.paper-tabs
	{
		background-color: var(--main-color) !important;
	}

	/*Sidebar*/
	#guide-content.ytd-app, #contentContainer.app-drawer, #guide-wrapper.ytd-app
	{
		background: var(--second-background) !important;
	}
	#endpoint.yt-simple-endpoint.ytd-guide-entry-renderer, #guide-section-title.ytd-guide-section-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-guide-entry-renderer:hover #endpoint.yt-simple-endpoint.ytd-guide-entry-renderer,
	ytd-guide-entry-renderer:hover svg
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	ytd-guide-entry-renderer[active]
	{
		background-color: var(--hover-background) !important;
	}
	#sections.ytd-guide-renderer > .ytd-guide-renderer:not(:last-child), #guide-links-primary.ytd-guide-renderer, #guide-content.ytd-app
	{
		border-color: var(--hover-background) !important;
	}
	#guide-links-primary.ytd-guide-renderer > a, #guide-links-secondary.ytd-guide-renderer > a, #footer.ytd-guide-renderer > #copyright,
	yt-formatted-string.ytd-guide-signin-promo-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#guide-links-primary.ytd-guide-renderer > a:hover, #guide-links-secondary.ytd-guide-renderer > a:hover
	{
		color: var(--main-color) !important;
	}
	/*Compact sidebar fix*/
	ytd-mini-guide-renderer, a.ytd-mini-guide-entry-renderer,
	a.ytd-mini-guide-entry-renderer:hover, a.ytd-mini-guide-entry-renderer:focus
	{
		background-color: var(--second-background) !important;
	}
	ytd-mini-guide-entry-renderer .guide-icon.ytd-mini-guide-entry-renderer,
	a.ytd-mini-guide-entry-renderer .guide-icon,
	a.ytd-mini-guide-entry-renderer.title.ytd-mini-guide-entry-renderer,
	ytd-mini-guide-entry-renderer .title.ytd-mini-guide-entry-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-mini-guide-entry-renderer[active] .guide-icon.ytd-mini-guide-entry-renderer,
	a.ytd-mini-guide-entry-renderer:hover .guide-icon,
	a.ytd-mini-guide-entry-renderer:hover .title.ytd-mini-guide-entry-renderer,
	ytd-mini-guide-entry-renderer[active] .title.ytd-mini-guide-entry-renderer
	{
		color: var(--main-color) !important;
	}
	#newness-dot.ytd-guide-entry-renderer
	{
		background-color: var(--main-color) !important;
	}

	/*Latest YouTube posts*/
	ytd-post-renderer[surface_="backstage-surface-type-home"],
	ytd-post-renderer[uses-compact-lockup]
	{
		background-color: var(--second-background) !important;
	}
	ytd-post-renderer[surface_="backstage-surface-type-home"] #home-content-text.ytd-post-renderer,
	ytd-post-renderer[surface_="backstage-surface-type-home"][attachment="poll"] #vote-count-text.ytd-post-renderer,
	ytd-post-renderer[uses-compact-lockup] #home-content-text.ytd-post-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-post-renderer[surface_="backstage-surface-type-home"] #author-text.yt-simple-endpoint.ytd-post-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-post-renderer[uses-compact-lockup][attachment="poll"] #vote-count-text.ytd-post-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*vote now button*/
	ytd-post-renderer[uses-compact-lockup] ytd-button-renderer.style-suggestive[is-paper-button] #button.ytd-button-renderer
	{
		background-color: var(--main-color) !important;
	}

	/*Main page video hover preview*/
	#video-preview-container.ytd-video-preview
	{
		background: var(--second-background) !important;
	}

	/*Feed filter*/
	#chips-wrapper.ytd-feed-filter-chip-bar-renderer
	{
		background-color: var(--main-background) !important;
		border-color: var(--hover-background) !important;
	}
	yt-chip-cloud-chip-renderer:not([selected])
	{
		background-color: var(--main-background) !important;
		border-color: var(--hover-background) !important;
	}
	yt-chip-cloud-chip-renderer[selected], yt-chip-cloud-chip-renderer:hover
	{
		background-color: var(--hover-background) !important;
	}
	yt-chip-cloud-renderer
	{
		background: transparent !important;
	}
	#text.yt-chip-cloud-chip-renderer
	{
		color: var(--main-text) !important;
	}
	#scroll-container.ytd-feed-filter-chip-bar-renderer::after, #scroll-container.ytd-feed-filter-chip-bar-renderer::before
	{
		background: transparent !important;
	}
	#left-arrow-button.ytd-feed-filter-chip-bar-renderer, #right-arrow-button.ytd-feed-filter-chip-bar-renderer,
	#left-arrow.yt-chip-cloud-renderer, #right-arrow.yt-chip-cloud-renderer,
	#left-arrow-button.yt-chip-cloud-renderer, #right-arrow-button.yt-chip-cloud-renderer
	{
		background: var(--main-background) !important;
	}
	#left-arrow.ytd-feed-filter-chip-bar-renderer::after, #right-arrow.ytd-feed-filter-chip-bar-renderer::before,
	yt-chip-cloud-renderer #right-arrow.yt-chip-cloud-renderer::before,
	yt-chip-cloud-renderer #left-arrow.yt-chip-cloud-renderer::after
	{
		display: none;
	}
	/*new to you filter on video*/
	#content-wrapper.ytd-feed-nudge-renderer
	{
		background-color: var(--second-background) !important;
	}
	yt-chip-cloud-chip-renderer[chip-style="STYLE_REFRESH_TO_NOVEL_CHIP"][selected]
	{
		background-image: none !important;
	}

	/*Covid19 big posts aka rich shelves*/
	/*also other borders*/
	ytd-rich-shelf-renderer, #show-more-button.ytd-rich-shelf-renderer,
	ytd-rich-shelf-renderer[is-show-more-hidden] #dismissible.ytd-rich-shelf-renderer,
	#contents.ytd-rich-shelf-renderer,
	ytd-compact-promoted-item-renderer[view-style="COMPACT_PROMOTED_ITEM_STYLE_RICH_GRID"] #dismissible.ytd-compact-promoted-item-renderer
	{
		border-color: var(--hover-background) !important;
	}

	/* poll results */
	.text-area.ytd-backstage-poll-renderer,
	paper-item.ytd-backstage-poll-renderer[selected] .progress-bar.ytd-backstage-poll-renderer,
	.progress-bar.ytd-backstage-poll-renderer
	{
		background-color: var(--main-color) !important;
	}
	ytd-backstage-poll-renderer:not([is-image-poll]) tp-yt-paper-item.ytd-backstage-poll-renderer .choice-info.ytd-backstage-poll-renderer
	{
		border-color: transparent !important;
	}

	/*Border color for terms and conditions*/
	ytd-consent-bump-renderer
	{
		border-bottom: 1px solid var(--main-color) !important;
	}

	#title.ytd-grid-channel-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Channel page*/
	/*header*/
	#channel-header.ytd-c4-tabbed-header-renderer, #tabs-inner-container.ytd-c4-tabbed-header-renderer
	{
		background: var(--hover-background) !important;
	}
	#channel-title.ytd-c4-tabbed-header-renderer
	{
		color: var(--main-text) !important;
	}
	#subscriber-count.ytd-c4-tabbed-header-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.tab-content.paper-tab, .tab-content.tp-yt-paper-tab
	{
		color: var(--main-text) !important;
	}
	paper-tab:hover .tab-content.paper-tab,
	tp-yt-paper-tab:hover > .tab-content.tp-yt-paper-tab
	{
		color: var(--main-color) !important;
	}
	tp-yt-paper-tabs
	{
		--paper-tabs-selection-bar-color: var(--main-color) !important;
	}
	/*search*/
	.input-content.paper-input-container label, .input-content.paper-input-container .paper-input-label,
	#subtitle,
	.style-scope.tp-yt-paper-input
	{
		color: var(--dimmer-text) !important;
	}
	/*arrow button*/
	iron-icon
	{
		fill: var(--main-text) !important;
	}
	iron-icon:hover
	{
		fill: var(--main-color) !important;
	}
	/*side channels*/
	#title:not([class*="ytd-labs"]):not([class*="upsell-offer"])
	{
		color: var(--main-text) !important;
	}
	.title
	{
		color: var(--main-text) !important;
	}
	.title:hover
	{
		color: var(--main-color) !important;
	}
	#contents > .ytd-browse-secondary-contents-renderer:not(:first-child)
	{
		border-color: var(--hover-background) !important;
	}
	/*videos - uploads*/
	#label-text.yt-dropdown-menu
	{
		color: var(--main-text) !important;
	}
	paper-menu-button.yt-dropdown-menu:hover #label-text.yt-dropdown-menu,
	paper-menu-button.yt-dropdown-menu:hover #label-icon.yt-dropdown-menu svg,
	paper-menu-button.yt-dropdown-menu:hover #icon-label.yt-dropdown-menu
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	/*community*/
	#message.ytd-message-renderer, #content-text.ytd-backstage-post-renderer,
	#repost-content-text.ytd-shared-post-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#author-text,
	.more-button, .less-button,
	.align-by-text.ytd-backstage-comments-renderer,
	#toggle.ytd-grid-renderer,
	#repost-author-text.yt-simple-endpoint.ytd-shared-post-renderer
	{
		color: var(--main-text) !important;
	}
	.more-button:hover, .less-button:hover,
	.align-by-text.ytd-backstage-comments-renderer:hover,
	#toggle.ytd-grid-renderer:hover,
	#author-text.yt-simple-endpoint.ytd-backstage-post-renderer:hover,
	#repost-author-text.yt-simple-endpoint.ytd-shared-post-renderer:hover
	{
		color: var(--main-color) !important;
	}
	#content-attachment ytd-video-renderer
	{
		background: var(--hover-background) !important;
	}
	#poll-votes.ytd-backstage-poll-renderer
	{
		background: transparent !important;
	}
	.vote-percentage.ytd-backstage-poll-renderer, .choice-text.ytd-backstage-poll-renderer,
	#poll-choice-text.ytd-commentbox,
	yt-icon.ytd-backstage-poll-renderer
	{
		color: var(--main-text) !important;
	}
	paper-item[selected].ytd-backstage-poll-renderer #progress-bar.ytd-backstage-poll-renderer
	{
		background: var(--main-color) !important;
	}
	/*about*/
	.subheadline, #right-column .subheadline
	{
		color: var(--main-text) !important;
	}
	#description:not([class*="yt-music"]), #bio, #right-column > yt-formatted-string
	{
		color: var(--dimmer-text) !important;
	}
	#right-column > yt-formatted-string,
	#description-container.ytd-channel-about-metadata-renderer, #bio-container.ytd-channel-about-metadata-renderer,
	#photos-container.ytd-channel-about-metadata-renderer, #details-container.ytd-channel-about-metadata-renderer,
	#links-container.ytd-channel-about-metadata-renderer
	{
		border-color: var(--hover-background) !important;
	}
	#link-list-container a
	{
		color: var(--main-color) !important;
	}
	#link-list-container:hover a
	{
		filter: brightness(110%);
	}
	/*private message*/
	ytd-form-popup-renderer[dialog][dialog][dialog]
	{
		background: var(--main-background) !important;
	}
	#buttons.ytd-form-popup-renderer
	{
		border-color: var(--hover-background) !important;
	}
	ytd-toggle-menu-service-item-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-toggle-menu-service-item-renderer:hover .style-scope.ytd-toggle-menu-service-item-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-toggle-menu-service-item-renderer:hover
	{
		background: var(--hover-background) !important;
	}

	/*Video page*/
	/*title*/
	.title.ytd-video-primary-info-renderer yt-formatted-string.ytd-video-primary-info-renderer
	{
		color: var(--main-text) !important;
	}
	/*views*/
	span.yt-view-count-renderer, span.ytd-video-view-count-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*published date*/
	#date.ytd-video-primary-info-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-video-primary-info-renderer
	{
		border-color: var(--hover-background) !important;
	}
	.content-text.ytd-metadata-with-image-row-renderer
	{
		color: var(--main-text) !important;
	}

	/*Share*/
	paper-dialog, tp-yt-paper-dialog
	{
		background: var(--main-background) !important;
	}
	#share-url
	{
		color: var(--main-text) !important;
	}
	#copy-button:hover #text
	{
		color: var(--main-color) !important;
	}
	#bar.yt-copy-link-renderer
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	ytd-third-party-network-section-renderer ytd-copy-link-renderer.ytd-third-party-network-section-renderer,
	yt-start-at-renderer.yt-third-party-network-section-renderer
	{
		border-color: var(--hover-background) !important;
	}
	yt-formatted-string.yt-start-at-renderer,
	#text.ytd-sender-id-section-renderer
	{
		color: var(--main-text) !important;
	}
	/*share embed*/
	#embed-panel.yt-sharing-embed-renderer
	{
		background: var(--second-background) !important;
	}
	#close-panel-icon.yt-sharing-embed-renderer
	{
		color: var(--main-text) !important;
	}
	#close-panel-icon.yt-sharing-embed-renderer:hover
	{
		color: var(--main-color) !important;
	}
	#title-bar.yt-sharing-embed-renderer,
	#additional-info.yt-sharing-embed-renderer,
	#action-buttons.yt-sharing-embed-renderer
	{
		border-color: var(--hover-background) !important;
	}
	#privacy-mode-info.yt-sharing-embed-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*search for people*/
	#to-field-header.ytd-contact-search-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#name.ytd-suggested-contact-renderer
	{
		color: var(--main-text) !important;
	}

	/*Make a clip*/
	#container.yt-clip-creation-renderer
	{
		background-color: transparent !important;
	}
	input.yt-clip-creation-scrubber-renderer /*time*/
	{
		border-color: var(--dimmer-text) !important;
	}
	#handles.yt-clip-creation-scrubber-view /*preview*/
	{
		border-color: var(--main-color) !important;
	}
	.handle.yt-clip-creation-scrubber-view /*preview*/
	{
		background-color: var(--main-color) !important;
	}
	/*buttons*/
	#footer.yt-clip-creation-renderer
	{
		background-color: var(--second-background) !important;
	}
	yt-clip-section-renderer yt-button-renderer.style-primary[is-paper-button],
	yt-clip-creation-renderer yt-button-renderer.style-primary[is-paper-button],
	yt-clip-section-footer-renderer yt-button-renderer.style-primary[is-paper-button]
	{
		background-color: transparent !important;
	}
	yt-button-renderer.style-primary[disabled][is-paper-button] yt-formatted-string.yt-button-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Playlist creation*/
	#subtext.yt-live-chat-message-renderer,
	#label.yt-live-chat-text-input-field-renderer, .input-content.paper-input-container input,
	.input-content.paper-input-container textarea, .input-content.paper-input-container iron-autogrow-textarea,
	.input-content.paper-input-container .paper-input-input
	{
		color: var(--dimmer-text) !important;
	}
	.add-on-content.is-highlighted.paper-input-container *, paper-input-char-counter
	{
		color: var(--dimmer-text) !important;
	}

	/*Video cards*/
	/*ttile*/
	ytd-grid-video-renderer.use-ellipsis #details.ytd-grid-video-renderer a.ytd-grid-video-renderer,
	ytd-compact-video-renderer.use-ellipsis #video-title.ytd-compact-video-renderer,
	#video-title.ytd-video-renderer,
	h3.ytd-playlist-renderer,
	#video-title.ytd-child-video-renderer, #length.ytd-child-video-renderer,
	#video-title, #unplayableText, #length, #details
	{
		color: var(--main-text) !important;
	}
	#items.yt-horizontal-list-renderer > .yt-horizontal-list-renderer:hover a.ytd-grid-video-renderer,
	ytd-compact-video-renderer:hover #video-title.ytd-compact-video-renderer,
	ytd-video-renderer:hover #video-title.ytd-video-renderer,
	ytd-playlist-renderer:hover h3.ytd-playlist-renderer,
	#content.ytd-playlist-video-renderer:hover #video-title,
	a.yt-simple-endpoint.ytd-playlist-panel-video-renderer:hover #video-title,
	a.yt-simple-endpoint.ytd-playlist-panel-video-renderer:hover #unplayableText,
	.style-scope.ytd-grid-renderer.use-ellipsis:hover #video-title,
	#video-title:hover,
	ytd-grid-video-renderer:hover #video-title.yt-simple-endpoint.ytd-grid-video-renderer
	{
		color: var(--main-color) !important;
	}
	/*author*/
	yt-formatted-string[ellipsis-truncate] a.yt-formatted-string:last-child, #byline.ytd-video-meta-block,
	#channel-title.ytd-channel-renderer span.ytd-channel-renderer,
	#text.ytd-channel-name
	{
		color: var(--main-color) !important;
	}
	/*metadata*/
	#metadata-line.ytd-grid-video-renderer, #metadata-line.ytd-video-meta-block span.ytd-video-meta-block,
	#metadata.ytd-channel-renderer, #description.ytd-channel-renderer,
	#thumbnail-attribution.ytd-grid-channel-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*action buttons*/
	a.yt-simple-endpoint.ytd-toggle-button-renderer, ytd-button-renderer yt-formatted-string.ytd-button-renderer,
	ytd-toggle-button-renderer.style-text[is-icon-button] #text.ytd-toggle-button-renderer /*likes*/
	{
		color: var(--dimmer-text) !important;
	}
	ytd-toggle-button-renderer.style-default-active a.yt-simple-endpoint.ytd-toggle-button-renderer /*active like/dislike buttons count*/
	{
		color: var(--main-color) !important;
	}
	ytd-toggle-button-renderer yt-icon-button.style-default-active button yt-icon svg, /*active like/dislike buttons icons, active bell icon*/
	ytd-toggle-button-renderer yt-icon-button[aria-pressed='true'] button yt-icon svg /*active like/dislike buttons icons, active bell icon*/
	{
		fill: var(--main-color) !important;
	}
	ytd-toggle-button-renderer.style-text[is-icon-button]:hover *, /*like/dislike*/
	ytd-toggle-button-renderer.force-icon-button a.ytd-toggle-button-renderer:hover #text.ytd-toggle-button-renderer,
	ytd-button-renderer[is-icon-button]:hover *, /*share*/
	button.yt-icon-button:hover * /*bell*/
	{
		color: var(--main-color) !important;
	}
	/*description and other metadata*/
	.date.ytd-video-secondary-info-renderer, .content.ytd-video-secondary-info-renderer, #title.ytd-metadata-row-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.content.content-line-height-override.style-scope.ytd-metadata-row-renderer, .content.ytd-metadata-row-header-renderer
	{
		color: var(--main-text) !important;
	}
	/*show more*/
	.more-button, .less-button,
	#show-more-button.ytd-ticket-shelf-renderer > div.ytd-ticket-shelf-renderer,
	#show-less-button.ytd-ticket-shelf-renderer > div.ytd-ticket-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	.more-button:hover, .less-button:hover,
	#show-more-button.ytd-ticket-shelf-renderer > div.ytd-ticket-shelf-renderer:hover,
	#show-less-button.ytd-ticket-shelf-renderer > div.ytd-ticket-shelf-renderer:hover
	{
		color: var(--main-color) !important;
	}
	/*section borders*/
	ytd-video-secondary-info-renderer, ytd-metadata-row-header-renderer[has-divider-line]
	{
		border-color: var(--hover-background) !important;
	}

	/*Recommandation page*/
	/*author*/
	#title.ytd-shelf-renderer
	{
		color: var(--main-color) !important;
	}
	#title-annotation.ytd-shelf-renderer
	{
		color: var(--dimmer-text) !important;
	}
	a.yt-simple-endpoint.yt-formatted-string:only-of-type:hover
	{
		color: var(--main-color) !important;
	}
	a.yt-simple-endpoint.yt-formatted-string:only-of-type
	{
		color: var(--main-text) !important;
	}
	/*Borders*/
	#contents.ytd-section-list-renderer > .ytd-section-list-renderer:not(:last-child):not(ytd-page-introduction-renderer)
	{
		border-color: var(--hover-background) !important;
	}
	/*Next and prev buttons*/
	.arrow.yt-horizontal-list-renderer,
	#scroll-button-forward,
	.arrow.ytd-horizontal-card-list-renderer,
	.ytd-horizontal-card-list-renderer[arrow],
	.scroll-button.yt-third-party-share-target-section-renderer /*share link*/
	{
		background-color: var(--hover-background) !important;
	}

	/*For the outline around the channel name*/
	.style-scope.ytd-comment-renderer.creator
	{
		background-color: var(--main-color) !important;
	}
	.style-scope.ytd-comment-renderer.creator:hover
	{
		background-color: var(--hover-background) !important;
	}
	#name.ytd-author-comment-badge-renderer
	{
		color: var(--main-text) !important;
	}
	#name:hover
	{
		color: var(--main-color) !important;
	}

	/*Accounts*/
	yt-formatted-string.ytd-account-item-section-header-renderer a
	{
		color: var(--dimmer-text) !important;
	}
	.style-scope.ytd-account-item-section-renderer:hover #channel-title.ytd-account-item-renderer
	{
		color: var(--main-color) !important;
	}

	app-drawer.ytd-app:not([persistent]) #header.ytd-app
	{
		border-color: var(--main-color) !important;
	}

	/*How is youtube today*/
	ytd-single-option-survey-renderer[dialog][dialog][dialog], ytd-single-option-survey-renderer,
	ytd-survey-follow-up-renderer[dialog][dialog][dialog], ytd-survey-follow-up-renderer,
	ytd-checkbox-survey-renderer[dialog][dialog][dialog]
	/*TODO: forgot to test if the [dialog] is even needed*/
	{
		background-color: var(--hover-background) !important;
		box-shadow: var(--shadow) !important;
	}
	#header.ytd-single-option-survey-renderer,
	#header.ytd-survey-follow-up-renderer,
	#header.ytd-checkbox-survey-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-single-option-survey-option-renderer,
	#checkboxLabel.paper-checkbox
	{
		color: var(--main-text) !important;
	}
	ytd-single-option-survey-option-renderer:hover
	{
		background-color: var(--hover-background) !important;
	}

	/*rate a video to improve youtube*/
	#star-survey.ytd-inline-survey-renderer
	{
		background-color: var(--second-background) !important;
	}
	#inline-survey-compact-video-renderer.ytd-inline-survey-renderer
	{
		background-color: var(--hover-background) !important;
	}
	ytd-primetime-promo-renderer.ytd-rich-section-renderer, ytd-inline-survey-renderer.ytd-rich-section-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*not sure tell us why followup*/
	#title.ytd-inline-survey-renderer, #follow-up-title.ytd-inline-survey-renderer,
	#selected-response-text.ytd-rating-survey-renderer
	{
		color: var(--main-color) !important;
	}
	/*background and close button*/
	ytd-inline-survey-renderer[expanded] #dismissable.ytd-inline-survey-renderer,
	#dismiss-button.ytd-inline-survey-renderer
	{
		background-color: var(--second-background) !important;
	}
	paper-checkbox.ytd-checkbox-survey-option-renderer
	{
		background-color: var(--hover-background) !important;
	}
	/*thanks*/
	#dismissed.ytd-inline-survey-renderer ytd-message-renderer.ytd-inline-survey-renderer
	{
		background-color: var(--hover-background) !important;
	}

	/*info warning - covid19*/
	ytd-clarification-renderer
	{
		background-color: var(--hover-background) !important;
	}
	ytd-clarification-renderer[has-action-button] .content.ytd-clarification-renderer,
	ytd-clarification-renderer[background-style="info"]
	{
		border-color: var(--hover-background) !important;
	}
	.content-title.ytd-clarification-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-clarification-renderer[clarify-style="medium"] .description.ytd-clarification-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.source.ytd-clarification-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-clarification-renderer yt-button-renderer.style-suggestive[is-paper-button] paper-button.yt-button-renderer
	{
		border-color: var(--main-color) !important;
	}

	/*Change subtitles settings tooltip*/
	.ytp-promotooltip-container
	{
		background-color: var(--hover-background) !important;
		box-shadow: var(--shadow) !important;
		color: var(--main-text) !important;
	}
	.ytp-promotooltip-pointer
	{
		border-color: var(--hover-background) !important;
	}
	/*You are not logged in tooltip*/
	#tooltip.tp-yt-paper-tooltip,
	yt-tooltip-renderer
	{
		background-color: var(--hover-background) !important;
		box-shadow: var(--shadow) !important;
		color: var(--main-text) !important;
	}
	yt-tooltip-renderer::before
	{
		border-color: transparent transparent var(--hover-background) transparent !important;
	}

	/*Join button tooltip*/
	yt-bubble-hint-renderer[style_="BUBBLE_HINT_STYLE_BLUE_TOOLTIP"]
	{
		background-color: var(--second-background) !important;
		box-shadow: var(--shadow) !important;
	}
	yt-bubble-hint-renderer[style_="BUBBLE_HINT_STYLE_BLUE_TOOLTIP"] #text.yt-bubble-hint-renderer:not(:empty),
	yt-bubble-hint-renderer[style_="BUBBLE_HINT_STYLE_BLUE_TOOLTIP"] #details-text.yt-bubble-hint-renderer
	{
		background-color: var(--second-background) !important;
	}
	yt-bubble-hint-renderer[position-type="OPEN_POPUP_POSITION_LEFT"][style_="BUBBLE_HINT_STYLE_BLUE_TOOLTIP"]::before
	{
		border-color: transparent transparent transparent var(--second-background) !important;
	}
	/*window*/
	ytd-sponsorships-offer-renderer[dialog][dialog][dialog]
	{
		background-color: var(--main-background) !important;
	}
	/*title*/
	#top-bar.ytd-sponsorships-offer-renderer
	{
		color: var(--main-text) !important;
	}
	/*price*/
	#above-purchase-button-text.ytd-sponsorships-tier-renderer
	{
		color: var(--main-color) !important;
	}
	/*fine print*/
	.disclaimer.ytd-sponsorships-tier-renderer
	{
		color: var(--main-color) !important;
	}

	/*Super Thanks donations*/
	ytd-pdg-buy-flow-renderer
	{
		background-color: var(--main-background) !important;
	}
	/*remove white image in the header*/
	yt-pdg-buy-flow-header-renderer
	{
		background: transparent !important;
	}
	#container.ytd-pdg-comment-preview-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*bonus*/
	#title-background.ytd-pdg-comment-preview-renderer
	{
		background-color: var(--hover-background) !important;
	}

	/*Progress bar*/
	#progress
	{
		background-color: var(--main-color) !important;
		border-color: var(--main-color) !important;
	}
	yt-page-navigation-progress
	{
		background-color: transparent !important;
	}

	/*Button tooltips*/
	#tooltip.paper-tooltip
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}

	/*Active grid icon*/
	button.ytd-button-renderer[is="paper-icon-button-light"][disabled]
	{
		color: rgb(255,255,255) !important;
	}

	/*Subscribe button and comment button*/
	#subscribe-button:hover ytd-button-renderer yt-formatted-string.ytd-button-renderer, #subscribe-button ytd-button-renderer yt-formatted-string.ytd-button-renderer,
	#subscribe-button:hover .deemphasize.yt-formatted-string, #subscribe-button .deemphasize.yt-formatted-string,
	paper-button.ytd-subscribe-button-renderer[subscribed] yt-formatted-string.ytd-subscribe-button-renderer .deemphasize.yt-formatted-string,
	ytd-button-renderer #button.ytd-button-renderer:hover yt-formatted-string.ytd-button-renderer,
	ytd-button-renderer #button.ytd-button-renderer yt-formatted-string.ytd-button-renderer,
	ytd-subscribe-button-renderer[button-style="COMPACT_GRAY"] paper-button.ytd-subscribe-button-renderer,
	paper-button.ytd-subscribe-button-renderer,
	ytd-sponsorships-tier-renderer yt-button-renderer yt-formatted-string.yt-button-renderer, /*join button in join window*/
	/*as of april 2021*/
	tp-yt-paper-button.ytd-subscribe-button-renderer,
	ytd-button-renderer.style-suggestive[is-paper-button] tp-yt-paper-button.ytd-button-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-button-renderer #button.ytd-button-renderer yt-formatted-string.ytd-button-renderer.style-blue-text
	{
		color: var(--main-color) !important;
	}
	ytd-button-renderer.style-destructive[is-paper-button],
	paper-button.ytd-subscribe-button-renderer,.ytp-sb-subscribe,
	a.ytp-sb-subscribe, ytd-subscribe-button-renderer:not([button-style]) paper-button:not([subscribed]),
	#button[class="style-scope ytd-button-renderer style-compact-gray"],
	ytd-button-renderer.style-compact-gray[is-paper-button] paper-button.ytd-button-renderer,
	ytd-button-renderer.style-suggestive[is-paper-button] paper-button.ytd-button-renderer, /*join button*/
	ytd-sponsorships-tier-renderer yt-button-renderer.style-primary[is-paper-button], /*join button in join window*/
	/*as of april 2021*/
	ytd-button-renderer.style-suggestive[is-paper-button] tp-yt-paper-button.ytd-button-renderer,
	tp-yt-paper-button.ytd-subscribe-button-renderer
	{
		background-color: var(--main-color) !important;
		border-color: var(--main-color) !important;
		box-shadow: var(--shadow) !important;
	}
	if join-color /*overwriting the above*/
	{
		ytd-button-renderer.style-suggestive[is-paper-button] paper-button.ytd-button-renderer,
		ytd-sponsorships-tier-renderer yt-button-renderer.style-primary[is-paper-button], /*join button in join window*/
		ytd-button-renderer.style-suggestive[is-paper-button] tp-yt-paper-button.ytd-button-renderer /*as of april 2021*/
		{
			background-color: var(--second-background) !important;
			border-color: var(--second-background) !important;
		}
	}
	if subscribe-color /*overwriting the above*/
	{
		ytd-button-renderer.style-destructive[is-paper-button],
		paper-button.ytd-subscribe-button-renderer,.ytp-sb-subscribe,
		a.ytp-sb-subscribe, ytd-subscribe-button-renderer:not([button-style]) paper-button:not([subscribed]),
		#button[class="style-scope ytd-button-renderer style-compact-gray"],
		ytd-button-renderer.style-compact-gray[is-paper-button] paper-button.ytd-button-renderer,
		tp-yt-paper-button.ytd-subscribe-button-renderer /*as of april 2021*/
		{
			background-color: var(--second-background) !important;
			border-color: var(--second-background) !important;
		}
	}
	ytd-button-renderer.style-destructive[is-paper-button]:hover,
	paper-button.ytd-subscribe-button-renderer:hover,
	paper-button.ytd-subscribe-button-renderer[subscribed]:hover,
	.ytp-sb-subscribe, a.ytp-sb-subscribe:hover,.ytp-sb-unsubscribe:hover,
	ytd-subscribe-button-renderer:not([button-style]) paper-button:not([subscribed]):hover,
	#button[class="style-scope ytd-button-renderer style-compact-gray"]:hover,
	ytd-button-renderer.style-compact-gray[is-paper-button] paper-button.ytd-button-renderer:hover,
	ytd-button-renderer.style-suggestive[is-paper-button] paper-button.ytd-button-renderer:hover, /*join button*/
	ytd-sponsorships-tier-renderer yt-button-renderer.style-primary[is-paper-button]:hover, /*join button in join window*/
	/*as of april 2021*/
	ytd-button-renderer.style-suggestive[is-paper-button] tp-yt-paper-button.ytd-button-renderer:hover,
	tp-yt-paper-button.ytd-subscribe-button-renderer:hover
	{
		filter: brightness(110%) !important;
	}
	paper-button.ytd-subscribe-button-renderer[subscribed], .ytp-sb-unsubscribe,
	tp-yt-paper-button.ytd-subscribe-button-renderer[subscribed] /*as of april 2021*/
	{
		background-color: var(--second-background) !important;
		color: var(--main-text) !important;
		opacity: 0.9 !important;
		box-shadow: var(--shadow) !important;
	}
	ytd-button-renderer.style-primary[is-paper-button]
	{
		background-color: transparent !important;
	}

	/*Sponsor button*/
	ytd-modal-with-title-and-button-renderer
	{
		background: var(--second-background) !important;
	}
	#content.ytd-modal-with-title-and-button-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.buttons.ytd-modal-with-title-and-button-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*sponsor popup*/
	#sponsor-button.ytd-membership-offer-renderer ytd-button-renderer.ytd-membership-offer-renderer
	{
		background-color: var(--main-color) !important;
	}
	#sponsor-button.ytd-membership-offer-renderer ytd-button-renderer.ytd-membership-offer-renderer:hover
	{
		filter: brightness(110%) !important;
	}
	#header.ytd-membership-offer-renderer
	{
		background: var(--main-background) !important;
	}
	ytd-perks-section-renderer, ytd-membership-offer-renderer[dialog][dialog][dialog],
	paper-dialog-scrollable.can-scroll:not(.scrolled-to-bottom):not(:last-child)::after,
	paper-dialog-scrollable.is-scrolled:not(:first-child)::before
	{
		background: var(--second-background) !important;
	}
	.extra-content.ytd-offer-perk-extra
	{
		border-color: var(--hover-background) !important;
		background: var(--hover-background) !important;
		color: var(--dimmer-text) !important;
	}
	.footer.ytd-membership-offer-renderer
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	ytd-membership-offer-renderer *
	{
		border-color: var(--hover-background) !important;
	}
	.price.ytd-membership-offer-renderer
	{
		color: var(--main-color) !important;
	}
	.style-title.ytd-offer-text-item, .style-subtitle.ytd-offer-text-item,
	.payment-clause.ytd-membership-offer-renderer
	{
		color: var(--main-text) !important;
	}
	.perk-item-title.ytd-perk-item-renderer, .perk-item-public-description.ytd-perk-item-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Edit button in channel page*/
	#edit-buttons.ytd-c4-tabbed-header-renderer ytd-button-renderer.ytd-c4-tabbed-header-renderer
	{
		background-color: transparent !important;
	}

	/*Toggle button to play next*/
	paper-toggle-button[checked]:not([disabled]) .toggle-bar.paper-toggle-button
	{
		background-color: var(--main-color) !important;
		opacity: 0.9 !important;
	}
	paper-toggle-button[checked]:not([disabled]) .toggle-button.paper-toggle-button
	{
		--paper-toggle-button-checked-button-color: rgb(255,255,255) !important;
	}
	/*Hover for toggle button*/
	.toggle-button.paper-toggle-button:hover,paper-toggle-button[checked]:not([disabled]) .toggle-button.paper-toggle-button:hover
	{
		background-color: var(--main-color) !important;
	}
	yt-bubble-hint-renderer
	{
		background: var(--hover-background) !important;
	}
	yt-bubble-hint-renderer::after
	{
		border-top-color: var(--second-background) !important;
	}
	#text.yt-bubble-hint-renderer
	{
		background: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	#details-text.yt-bubble-hint-renderer
	{
		background: var(--hover-background) !important;
		color: var(--dimmer-text) !important;
	}
	.buttons.yt-bubble-hint-renderer
	{
		border-color: var(--hover-background) !important;
	}

	/*Filter active*/
	paper-button.ytd-toggle-button-renderer
	{
		color: rgba(255, 255, 255, 0.5) !important;
	}

	/*Badges*/
	.badge-style-type-simple.ytd-badge-supported-renderer,.badge-style-type-disabled.ytd-badge-supported-renderer, yt-icon.ytd-badge-supported-renderer
	{
		background: transparent !important;
		color: var(--main-color) !important;
		padding-left: 0px !important;
		opacity: .7 !important;
	}
	.badge-style-type-simple-strikethrough.ytd-badge-supported-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*Trending badge*/
	.badge-style-type-featured.ytd-badge-supported-renderer
	{
		background: var(--main-color) !important;
	}
	/*Author verified badge in comments*/
	ytd-author-comment-badge-renderer:not(.creator) #icon.ytd-author-comment-badge-renderer
	{
		fill: var(--main-color) !important;
	}
	/*Live now badge*/
	.badge-style-type-live-now.ytd-badge-supported-renderer
	{
		color: var(--main-color) !important;
		background: transparent !important;
		border-color: var(--main-color) !important;
	}
	/*Premium*/
	.badge-style-type-red.ytd-badge-supported-renderer
	{
		color: #DA4453 !important;
		background: transparent !important;
		border-color: var(--main-color) !important;
	}
	/*Series name*/
	.badge-style-type-collection.ytd-badge-supported-renderer
	{
		color: var(--main-color) !important;
	}

	.yt-simple-endpoint.style-scope.yt-formatted-string
	{
		color: var(--dimmer-text);
	}

	/*Dropdown*/
	.dropdown-content.style-scope.ytd-popup-container > *,
	tp-yt-paper-listbox, ytd-menu-popup-renderer
	{
		background: var(--second-background) !important;
		color: var(--main-text) !important;
	}
	ytd-menu-service-item-renderer:hover, a.ytd-menu-navigation-item-renderer:hover,
	tp-yt-paper-listbox.yt-dropdown-menu .iron-selected.yt-dropdown-menu,
	tp-yt-paper-listbox.yt-dropdown-menu tp-yt-paper-item.yt-dropdown-menu:hover,
	ytd-menu-service-item-renderer[is-selected]
	{
		background: var(--hover-background) !important;
	}
	yt-formatted-string.ytd-menu-service-item-renderer, yt-formatted-string.ytd-menu-navigation-item-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-menu-service-item-renderer:hover yt-formatted-string.ytd-menu-service-item-renderer,
	a.ytd-menu-navigation-item-renderer:hover yt-formatted-string.ytd-menu-navigation-item-renderer,
	tp-yt-paper-listbox a.yt-simple-endpoint.yt-dropdown-menu:hover .item.yt-dropdown-menu
	{
		color: var(--main-color) !important;
	}
	#owner-name.ytd-video-owner-renderer a
	{
		color: var(--main-color) !important;
		opacity: .9;
	}
	/*share*/
	#header.ytd-add-to-playlist-renderer
	{
		color: var(--main-text) !important;
	}
	#label.ytd-playlist-add-to-option-renderer, paper-item.ytd-compact-link-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#header.ytd-add-to-playlist-renderer, #playlists.ytd-add-to-playlist-renderer
	{
		border-color: var(--hover-background) !important;
	}
	paper-item.ytd-compact-link-renderer:hover #label.ytd-compact-link-renderer,
	paper-item.ytd-compact-link-renderer:hover yt-icon.ytd-compact-link-renderer
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	ytd-playlist-add-to-option-renderer paper-checkbox:hover #label.ytd-playlist-add-to-option-renderer,
	ytd-playlist-add-to-option-renderer paper-checkbox[checked] #label.ytd-playlist-add-to-option-renderer,
	yt-icon.ytd-playlist-add-to-option-renderer
	{
		color: var(--main-color) !important;
	}

	/*Avatars and thumbnails opacity */
	img.yt-img-shadow
	{
		opacity: 0.9 !important;
	}
	img.yt-img-shadow:hover
	{
		opacity: 1 !important;
	}
	/*Very specific hover for thumbnails*/
	#dismissable.ytd-compact-video-renderer:hover img.yt-img-shadow, #items.yt-horizontal-list-renderer > .yt-horizontal-list-renderer:hover img.yt-img-shadow, #items.ytd-grid-renderer > ytd-grid-video-renderer.ytd-grid-renderer:hover img.yt-img-shadow, ytd-video-renderer.ytd-item-section-renderer:hover img.yt-img-shadow, .style-scope.ytd-channel-featured-content-renderer:hover img.yt-img-shadow, #grid-container.ytd-expanded-shelf-contents-renderer > .ytd-expanded-shelf-contents-renderer:hover img.yt-img-shadow, ytd-playlist-video-renderer:hover img.yt-img-shadow, iron-list:not([grid]) #items.iron-list > *:hover img.yt-img-shadow
	{
		opacity: 1 !important;
	}

	/*Video section*/
	/*Video title hover in html5 video*/
	.html5-video-player a:hover
	{
		color: var(--main-text) !important;
		text-shadow: none !important;
	}

	/* Code takken from https://userstyles.org/styles/95280 */
	/* scrubber button */
	.html5-scrubber-button:hover, .ytp-chrome-controls .ytp-button[aria-pressed]::after, .ytp-scrubber-button:hover, .html5-video-player:not(.ytp-color-party) .ytp-swatch-background-color, .ytp-swatch-background-color-secondary
	{
		background: var(--main-color) !important;
	}
	/* progress bar */
	.html5-video-player:not(.ytp-color-party) .html5-play-progress,
	.html5-video-player:not(.ytp-color-party) .ytp-play-progress
	{
		background: var(--main-color) !important;
	}
	.ytp-volume-slider-track, .ytp-volume-slider-handle:before
	{
		background: var(--main-color) !important;
		z-index: -117;
	}
	.ytp-settings-button.ytp-hd-quality-badge::after, .ytp-settings-button.ytp-4k-quality-badge::after, .ytp-settings-button.ytp-5k-quality-badge::after, .ytp-settings-button.ytp-8k-quality-badge::after, .ytp-settings-button.ytp-3d-badge::after
	{
		background-color: var(--main-color) !important;
	}
	.ytp-swatch-color
	{
		color: var(--main-color) !important;
	}
	.ytp-menuitem[aria-checked="true"] .ytp-menuitem-toggle-checkbox
	{
		background-color: var(--main-color) !important;
	}
	.ytp-chrome-controls .ytp-button.ytp-youtube-button:hover:not([aria-disabled="true"]):not([disabled]) .ytp-svg-fill-logo-tube-lozenge
	{
		fill: var(--main-color) !important;
	}
	.ytp-cued-thumbnail-overlay:hover .ytp-large-play-button-bg, .ytp-large-play-button.ytp-touch-device .ytp-large-play-button-bg
	{
		fill: var(--main-color) !important;
	}
	.ytp-large-play-button.ytp-button.ytp-red2:hover, .ytp-cued-thumbnail-overlay:hover .ytp-large-play-button.ytp-button.ytp-red2
	{
		/*background-image: url(https://github.com/RaitaroH/YouTube-DeepDark/raw/master/YT_Images/large_play_button_hover_ringo-vfl7vEehF.png) !important;*/
		background-image: url(https://s.ytimg.com/yts/img/large_play_button_ringo-vfljWXIdx.png) !important;
		filter: invert(100%) brightness(300%);
	}
	.resume-playback-progress-bar
	{
		background: var(--main-color) !important;
	}

	/*Added because of this: https://forum.userstyles.org/discussion/53368/solved-fix-this-annoying-youtube-tab-select-bug-thats-been-there-forever#latest*/
	.ytp-keyboard-focus .ytp-progress-bar:focus
	{
		box-shadow: none !important;
	}

	/*Video menu - might have issues with lighter colors*/
	.ytp-popup
	{
		background: var(--second-background) !important;
		opacity: .9 !important;
	}
	.ytp-menuitem:hover:not([aria-disabled="true"])
	{
		background-color: var(--hover-background) !important;
	}
	/*Text*/
	.iv-branding .iv-branding-context-name, .ytp-menuitem-label, .ytp-menuitem-label-count, .ytp-menuitem-content, .ytp-menu-label-secondary, .ytp-panel-header
	{
		color: var(--main-text) !important;
		text-shadow: none !important;
	}

	/*Keyboard focus*/
	.ytp-probably-keyboard-focus .ytp-menuitem:focus .ytp-menuitem-content, .ytp-probably-keyboard-focus .ytp-menuitem:focus .ytp-menuitem-label
	{
		box-shadow: inset -2px -2px 0 var(--main-color),inset 0 2px 0 var(--main-color) !important;
	}
	.ytp-probably-keyboard-focus .ytp-button:focus
	{
		box-shadow: inset 0 0 0 2px var(--main-color) !important;
	}
	.ytp-probably-keyboard-focus .ytp-progress-bar:focus
	{
		box-shadow: 0 0 0 2px var(--main-color) !important;
	}

	/*Miniplayer*/
	#info-bar.ytd-miniplayer .metadata.ytd-miniplayer,
	#info-bar.ytd-miniplayer
	{
		background-color: var(--main-background) !important;
	}
	#info-bar.ytd-miniplayer .channel.ytd-miniplayer
	{
		color: var(--main-color) !important;
	}
	.ytd-miniplayer .ytp-button:not([aria-disabled="true"]):not([disabled]):not([aria-hidden="true"]):hover svg path
	{
		fill: var(--main-color) !important;
	}
	/*added to queue*/
	ytd-miniplayer-toast[opened]
	{
		background-color: var(--second-background) !important;
	}
	#label.ytd-miniplayer-toast
	{
		color: var(--main-color) !important;
	}

	/*Watch later svg*/
	.style-scope.ytd-thumbnail-overlay-toggle-button-renderer:hover
	{
		fill: var(--main-color) !important;
	}
	ytd-thumbnail-overlay-toggle-button-renderer:focus yt-icon.ytd-thumbnail-overlay-toggle-button-renderer
	{
		outline-color: var(--main-color) !important;
	}

	/*This channel is watched by others*/
	ytd-thumbnail-overlay-endorsement-renderer
	{
		background-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}

	/*Popup for when you hover over the channel avatar in the video*/
	.iv-branding .branding-context-container-inner
	{
		background-color: var(--main-background) !important;
	}

	/*Changing icon for unavailable video*/
	#img.ytd-player-error-message-renderer
	{
		display: block !important;
		-moz-box-sizing: border-box !important;
		box-sizing: border-box !important;
		background: url(https://github.com/RaitaroH/YouTube-DeepDark/raw/master/YT_Images/404.png) no-repeat !important;
		width: 140px !important;
		height: 100px !important;
		padding-left: 140px !important;
		position: relative !important;
	}
	/*Changing icon for unavailable page (404)*/
	#error-page-hh-illustration
	{
		display: block !important;
		-moz-box-sizing: border-box !important;
		box-sizing: border-box !important;
		background: url(https://github.com/RaitaroH/YouTube-DeepDark/raw/master/YT_Images/404.png) no-repeat !important;
		width: 140px !important;
		height: 100px !important;
		padding-left: 140px !important;
		right: -175px !important;
		position: relative !important;
	}
	/*Some spacing for the logo*/
	#yt-masthead #logo-container
	{
		margin-right: 20px !important;
	}

	/*New logo*/
	#logo-icon-container.ytd-topbar-logo-renderer svg g path[fill*="#FF0000"],
	ytd-topbar-logo-renderer.style-scope a svg > g > g:nth-child(1) > path:nth-child(1)
	{
		fill: var(--main-color) !important;
	}
	ytd-topbar-logo-renderer.style-scope a svg > g > g:nth-child(1) > path:nth-child(2)
	{
		fill: var(--main-text) !important;
	}
	ytd-topbar-logo-renderer.style-scope a svg > g > g:nth-child(2) > g,
	#country-code.ytd-topbar-logo-renderer
	{
		color: var(--main-text) !important;
	}
	/*Logo hover*/
	#logo-icon:hover
	{
		--yt-swatch-logo-override: var(--main-color) !important;
	}
	/*Rewind logo*/
	#animated-yoodle
	{
		filter: invert(90%) grayscale(1);
	}

	/*Playlist page*/
	/*sidebar*/
	ytd-playlist-sidebar-renderer
	{
		background-color: var(--hover-background) !important;
	}
	#stats.ytd-playlist-sidebar-primary-info-renderer,
	#description.ytd-playlist-sidebar-primary-info-renderer .bold.yt-formatted-string,
	#owner-sub-count.ytd-video-owner-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#items.ytd-playlist-sidebar-renderer > .ytd-playlist-sidebar-renderer:not(:last-child)
	{
		border-color: var(--hover-background) !important;
	}
	#primary.ytd-two-column-browse-results-renderer
	{
		background-color: var(--main-background) !important;
	}
	ytd-button-renderer[is-paper-button] yt-icon.ytd-button-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#content.ytd-playlist-video-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*buttons*/
	ytd-playlist-sidebar-renderer ytd-toggle-button-renderer.style-suggestive[is-paper-button],
	ytd-playlist-sidebar-renderer paper-button.ytd-toggle-button-renderer
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	a.yt-simple-endpoint.ytd-button-renderer:hover *,
	ytd-playlist-sidebar-renderer ytd-button-renderer #button.ytd-button-renderer:hover,
	ytd-playlist-sidebar-renderer ytd-button-renderer #button.ytd-button-renderer:hover > yt-formatted-string.ytd-button-renderer
	{
		color: var(--main-color) !important;
	}
	/*playlist page*/
	ytd-browse[page-subtype="playlist"] ytd-two-column-browse-results-renderer.ytd-browse
	{
		background-color: var(--main-background) !important;
	}
	.index-message.ytd-playlist-panel-renderer,
	.light-text.ytd-playlist-segment-renderer,
	#contributor.ytd-playlist-video-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#title-container.ytd-playlist-segment-renderer
	{
		border-color: var(--hover-background) !important;
	}
	#title-container.ytd-playlist-segment-renderer:hover #title.ytd-playlist-segment-renderer
	{
		color: var(--main-color) !important;
	}

	/*Playlist changes*/
	ytd-playlist-panel-video-renderer:hover
	{
		background-color: var(--hover-background) !important;
	}
	ytd-playlist-panel-video-renderer[selected] #index.ytd-playlist-panel-video-renderer,#byline.ytd-playlist-panel-video-renderer,.ytp-video-menu-item[aria-checked="true"] .ytp-video-menu-item-now-playing,.ytp-video-menu-item-author
	{
		color: var(--main-color) !important;
	}
	ytd-playlist-video-renderer:hover,
	ytd-playlist-video-renderer:hover:not(.dragging)
	{
		background-color: var(--second-background) !important;
	}

	.header.ytd-playlist-panel-renderer,.playlist-items.ytd-playlist-panel-renderer,
	#header.ytd-engagement-panel-title-header-renderer,
	#content.ytd-engagement-panel-section-list-renderer,
	ytd-transcript-footer-renderer, ytd-transcript-segment-list-renderer
	{
		background-color: var(--second-background) !important;
	}
	.cue.ytd-transcript-body-renderer,
	.cue-group-start-offset.ytd-transcript-body-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.cue-group.active.ytd-transcript-body-renderer
	{
		border-left-color: var(--main-color) !important;
		background-color: var(--hover-background) !important;
	}
	.cue-group.active.ytd-transcript-body-renderer .cue-group-start-offset.ytd-transcript-body-renderer,
	.cue.ytd-transcript-body-renderer.active
	{
		color: var(--main-text) !important;
	}
	.cue-group.ytd-transcript-body-renderer:hover .cue-group-start-offset.ytd-transcript-body-renderer,
	.cue-group.ytd-transcript-body-renderer:hover .cue.ytd-transcript-body-renderer
	{
		color: var(--main-color) !important;
	}
	.cue.ytd-transcript-body-renderer:hover, ytd-transcript-body-renderer:not([refresh]) .cue.active.ytd-transcript-body-renderer
	{
		background-color: transparent !important;
		color: var(--main-color) !important
	}
	.segment-timestamp.ytd-transcript-segment-renderer
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important
	}
	/*search transcript*/
	ytd-transcript-search-panel-renderer,
	ytd-transcript-search-box-renderer
	{
		background-color: var(--second-background) !important;
	}
	.input-container.ytd-transcript-search-box-renderer
	{
		background-color: var(--hover-background) !important;
	}
	/*magnifing glass icon*/
	.icon.ytd-transcript-search-box-renderer
	{
		--iron-icon-fill-color: var(--dimmer-text) !important;
		--iron-icon-stroke-color: var(--dimmer-text) !important;
	}
	#transcript-search-box-input.ytd-transcript-search-box-renderer
	{
		color: var(--main-text) !important;
		caret-color: var(--main-color) !important;
	}

	.ytp-video-menu-item[aria-checked="true"] .ytp-video-menu-item-thumbnail
	{
		border-color: var(--main-color) !important;
	}

	#index.ytd-playlist-video-renderer, #index.ytd-playlist-panel-video-renderer,
	.badge-style-type-medium-grey.ytd-badge-supported-renderer /*unlisted*/
	{
		color: var(--dimmer-text) !important;
	}

	#container.ytd-playlist-panel-renderer
	{
		border-color: var(--second-background) !important;
	}

	/*Playlist creation*/
	#create-playlist-form .input-content.paper-input-container label
	{
		color: var(--main-text) !important;
	}
	#create-playlist-form input.style-scope.paper-input::placeholder
	{
		color: var(--dimmer-text) !important;
	}
	#create-playlist-form .underline.is-highlighted.paper-input-container .focused-line.paper-input-container
	{
		border-bottom-color: var(--main-text) !important;
	}
	#create-playlist-form #label.ytd-privacy-dropdown-item-renderer
	{
		color: var(--main-text) !important;
	}
	#create-playlist-form ytd-privacy-dropdown-item-renderer.iron-selected
	{
		background-color: var(--hover-background) !important;
	}

	/*Chapters*/
	/*title*/
	h4.ytd-macro-markers-list-item-renderer
	{
		color: var(--main-text) !important;
	}
	/*timestamp*/
	#time.ytd-macro-markers-list-item-renderer
	{
		color: var(--main-color) !important;
		background-color: transparent !important;
		padding: 0px !important;
	}
	/*show current chapter*/
	#sync-button.ytd-macro-markers-list-renderer
	{
		background-color: var(--main-background) !important;
		color: var(--main-text) !important;
	}
	#sync-button.ytd-macro-markers-list-renderer:hover
	{
		color: var(--main-color) !important;
	}
	/*active indicators*/
	ytd-macro-markers-list-item-renderer[active] #thumbnail.ytd-macro-markers-list-item-renderer
	{
		outline-color: var(--main-color) !important;
	}
	#active-indicator.ytd-macro-markers-list-item-renderer
	{
		background-color: var(--main-color) !important;
	}
	/*hover for item*/
	ytd-macro-markers-list-item-renderer:hover, ytd-macro-markers-list-item-renderer[active]
	{
		background-color: var(--hover-background) !important;
	}
	ytd-macro-markers-list-item-renderer:hover
	{
		box-shadow: 0px 2px 8px rgba(0, 0, 0, 0.4);
	}
	ytd-macro-markers-list-item-renderer:hover h4.ytd-macro-markers-list-item-renderer
	{
		color: var(--main-color) !important;
	}
	/*chapter images in description*/
	ytd-macro-markers-list-item-renderer[active][layout="MACRO_MARKERS_LIST_ITEM_RENDERER_LAYOUT_VERTICAL"]
	{
		border-color: var(--main-color) !important;
	}
	ytd-horizontal-card-list-renderer.ytd-structured-description-content-renderer:not(:first-child),
	ytd-metadata-row-container-renderer.ytd-structured-description-content-renderer:not(:first-child),
	ytd-structured-description-content-renderer[inline-structured-description] ytd-horizontal-card-list-renderer.ytd-structured-description-content-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*chapter times in search description*/
	.metadata-snippet-container-one-line.ytd-video-renderer #time.ytd-video-renderer
	{
		color: var(--main-color) !important;
		background: var(--second-background) !important;
	}

	/*Search bar*/
	ytd-searchbox[mode="legacy"] #container.ytd-searchbox, ytd-searchbox[mode="material-centered"] #container.ytd-searchbox,
	ytd-searchbox[mode="legacy"] #container.ytd-searchbox, ytd-searchbox[mode="legacy-centered"] #container.ytd-searchbox,
	#container.ytd-searchbox,
	#masthead-search-terms /*account settings page*/
	{
		background: var(--main-background) !important;
		border-color: var(--main-background) !important;
		box-shadow: none !important;
	}
	ytd-searchbox[mode="legacy"] #container.ytd-searchbox:hover, ytd-searchbox[mode=legacy][has-focus] #container.ytd-searchbox, ytd-searchbox[mode="material-left"] #container.ytd-searchbox, ytd-searchbox.style-scope[has-focus=""] #container.ytd-searchbox, ytd-searchbox[mode="material-centered"]:hover #container.ytd-searchbox,
	#masthead-search-terms.masthead-search-terms-border /*error page*/
	{
		border: 1px solid var(--main-color) !important;
		box-shadow: none !important;
	}
	ytd-searchbox[mode="legacy"] #container.ytd-searchbox input.ytd-searchbox,
	#container.ytd-searchbox > input, ytd-searchbox input,
	#masthead-search-terms.masthead-search-terms-border input /*error page*/
	{
		color: var(--main-text) !important;
	}
	/*Search icon*/
	#search-icon-legacy.ytd-searchbox,
	#masthead-search .search-btn-component, #masthead-search .search-btn-component .start /*account*/
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	#masthead-search .search-btn-component .yt-uix-button-content /*account*/
	{
		filter: invert(1);
	}
	#search-icon-legacy.ytd-searchbox yt-icon.ytd-searchbox
	{
		color: var(--main-text) !important;
	}
	#search-icon-legacy.ytd-searchbox:hover yt-icon.ytd-searchbox, #search-icon.ytd-searchbox:hover
	{
		color: var(--main-color) !important;
	}
	/*Main backgrounds*/
	.sbsb_a,.sbdd_b
	{
		background: var(--second-background) !important;
		border: none !important;
	}
	/*Text color*/
	.gsfs
	{
		color: var(--dimmer-text) !important;
	}
	/*Hover and keyboard select background*/
	.sbsb_c.gsfs:hover,.sbsb_d
	{
		background-color: var(--hover-background) !important;
	}
	.sbfl_b
	{
		background-color: var(--second-background) !important;
	}
	.sbfl_b:hover
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	.sbpqs_a
	{
		color: var(--main-color) !important;
	}
	/*Keyboard select text color and hover text color*/
	.sbsb_c:hover .sbqs_c,.sbsb_c.gsfs.sbsb_d .sbqs_c
	{
		color: var(--main-color) !important;
	}
	/*Keyboard icon in the search bar*/
	#gs_ok50
	{
		filter: invert(100%);
	}

	/*Microphone search*/
	ytd-masthead #voice-search-button.ytd-masthead
	{
		background-color: var(--hover-background) !important;
	}
	ytd-voice-search-dialog-renderer[dialog]
	{
		background-color: var(--second-background) !important;
	}
	#header-text.ytd-voice-search-dialog-renderer,
	#microphone-label.ytd-voice-search-dialog-renderer,
	#microphone.ytd-voice-search-dialog-renderer[state="try-again"] #microphone-circle.ytd-voice-search-dialog-renderer yt-icon.ytd-voice-search-dialog-renderer
	{
		color: var(--main-text) !important;
	}

	/*Search results correction*/
	.style-scope.yt-search-query-correction
	{
		color: var(--main-text) !important;
	}
	.style-scope.yt-search-query-correction .italic.yt-formatted-string, .style-scope.yt-search-query-correction:hover
	{
		color: var(--main-color) !important;
	}
	/*Similar results*/
	#title.ytd-exploratory-results-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*search results filter border*/
	#filter-menu.ytd-search-sub-menu-renderer
	{
		border-color: var(--hover-background) !important;
	}

	#watch-card-header.ytd-generic-watch-card, #img-endpoint.ytd-watch-card-collage-renderer #overlay-button.ytd-watch-card-collage-renderer
	{
		background: var(--main-color) !important;
		color: var(--main-text) !important;
	}
	paper-tab,
	paper-tab.iron-selected.ytd-generic-watch-card
	{
		color: var(--main-color) !important;
	}
	paper-item:hover
	{
		background-color: var(--second-background) !important;
	}
	#img-endpoint.ytd-watch-card-collage-renderer #overlay-button.ytd-watch-card-collage-renderer
	{
		opacity: .9;
	}
	#img-endpoint.ytd-watch-card-collage-renderer #overlay-button.ytd-watch-card-collage-renderer:hover
	{
		opacity: 1 !important;
	}

	/*album*/
	#watch-card-subtitle.ytd-watch-card-rich-header-renderer
	{
		color: var(--main-text) !important;
	}
	.duration.ytd-watch-card-compact-video-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Buttom border for different fields*/
	.unfocused-line.paper-input-container
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	.focused-line.paper-input-container
	{
		background-color: var(--main-color) !important;
		border-color: var(--main-color) !important;
	}

	/*Search page*/
	#result-count.ytd-search-sub-menu-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-search-sub-menu-renderer, ytd-exploratory-results-renderer.ytd-item-section-renderer, ytd-shelf-renderer.ytd-item-section-renderer
	{
		border-color: var(--hover-background) !important;
	}
	/*no results*/
	.promo-title.ytd-background-promo-renderer, .promo-body-text.ytd-background-promo-renderer
	{
		color: var(--main-text) !important;
	}
	/*show more*/
	#more.ytd-vertical-list-renderer yt-formatted-string.ytd-vertical-list-renderer, #all.ytd-vertical-list-renderer yt-formatted-string.ytd-vertical-list-renderer
	{
		color: var(--main-text) !important;
	}
	#more.ytd-vertical-list-renderer yt-formatted-string.ytd-vertical-list-renderer:hover,
	#all.ytd-vertical-list-renderer yt-formatted-string.ytd-vertical-list-renderer:hover
	{
		color: var(--main-color) !important;
	}
	ytd-search-filter-renderer yt-formatted-string.ytd-search-filter-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-search-filter-renderer.selected yt-formatted-string.ytd-search-filter-renderer, ytd-search-filter-renderer.selected #dismiss-x.ytd-search-filter-renderer, ytd-search-filter-renderer yt-formatted-string.ytd-search-filter-renderer:hover
	{
		color: var(--main-color) !important;
	}

	/*Search music suggestions*/
	ytd-watch-card-rich-header-renderer
	{
		background: var(--hover-background) !important;
	}
	#overlay-button
	{
		background: var(--main-color) !important;
	}
	#overlay-button:hover
	{
		filter: brightness(110%) !important;
	}
	#watch-card-title, #view-all-endpoint:hover
	{
		color: var(--main-color) !important;
	}
	ytd-watch-card-compact-video-renderer[is-condensed], #view-all-endpoint
	{
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}

	/*Search results related to item searched*/
	a.ytd-search-refinement-card-renderer
	{
		background-color: var(--second-background) !important;
		border-color: var(--hover-background) !important;
		border-radius: 8px !important;
	}
	a.ytd-search-refinement-card-renderer:hover #card-title.ytd-search-refinement-card-renderer div.ytd-search-refinement-card-renderer
	{
		color: var(--main-color) !important;
	}
	#card-title.ytd-search-refinement-card-renderer div.ytd-search-refinement-card-renderer
	{
		color: var(--main-text) !important;
	}
	/*Next button*/
	.center-aligned.ytd-horizontal-card-list-renderer
	{
		background-color: var(--second-background) !important;
		color: var(--main-text) !important;
	}
	.center-aligned.ytd-horizontal-card-list-renderer:hover
	{
		color: var(--main-color) !important;
	}

	/*filter*/
	a.yt-simple-endpoint.ytd-toggle-button-renderer:hover *
	{
		color: var(--main-color) !important;
		/* fill: var(--main-color) !important; */
	}
	#filter-group-name.ytd-search-filter-group-renderer
	{
		color: var(--main-text) !important;
		border-color: var(--hover-background) !important;
	}

	#description-text.ytd-video-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Iridium support, former YouTube+*/
	#iridium_settings .iri-settings-button.danger,.active_sidebar
	{
		background-color: var(--main-color) !important;
		border-color: var(--main-color) !important;
	}
	.feature-link
	{
		color: var(--main-color) !important;
	}
	.iri-dark-mode-settings .sidebar_section:hover:not(.active_sidebar)
	{
		background-color: var(--hover-background) !important;
	}
	.sidebar_section
	{
		color: var(--dimmer-text) !important;
	}
	.iri-dark-mode-settings #iridium_settings {
		background-color: var(--second-background) !important;
	}
	.iri-dark-mode-settings #iridium_settings_sidebar, .iri-dark-mode-settings #settings_section, .iri-dark-mode-settings #iridium-text-editor
	{
		background-color: var(--main-background) !important;
	}
	.iri-video-count
	{
		color: var(--dimmer-text) !important;
		opacity: .8;
	}
	.iri-video-count:hover
	{
		color: var(--main-color) !important;
		opacity: 1 !important;
	}
	.iri-add-to-blacklist:hover svg
	{
		fill: var(--main-color) !important;
	}
	#iri-quick-controls button svg
	{
		fill: var(--dimmer-text) !important;
	}
	#iri-quick-controls button[enabled] svg
	{
		fill: var(--main-color) !important;
		opacity: .9;
	}
	#iri-quick-controls button:hover svg, #iri-quick-controls button[enabled]:hover svg
	{
		fill: var(--main-color) !important;
		opacity: 1 !important;
	}
	.iri-quick-controls-tooltip, .iri-tooltip
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	#iri-show-comments:hover
	{
		color: var(--main-color) !important;
	}

	/*SponsorBlock*/
	#sponsorblockPopup, #sponsorBlockPopupBody, #sponsorBlockPopupContainer,
	#sponsorBlockPopupContainer .sbControlsMenu-item
	{
		background-color: var(--second-background) !important;
	}
	#sponsorBlockPopupContainer
	{
		padding-top: 12px !important;
		margin-bottom: 20px !important;
	}
	#sponsorBlockPopupContainer .smallLink
	{
		color: var(--main-text) !important;
		font-size: 13px !important;
	}
	#sponsorBlockPopupContainer .smallLink:hover
	{
		color: var(--main-color) !important;
	}
	#sponsorBlockPopupContainer .switchBg.green
	{
		background: var(--main-color) !important;
	}
	#sponsorBlockPopupContainer .switchBg.white
	{
		background-color: var(--paper-toggle-button-unchecked-bar-color, #000000) !important;
		opacity: 0.4 !important;
	}
	#sponsorBlockPopupContainer .sponsorBlockPageBody .sbMediumButton
	{
		background-color: var(--main-color) !important;
	}
	#sponsorBlockPopupContainer .sponsorBlockPageBody .sbMediumButton:hover
	{
		filter: brightness(110%);
	}
	/*logo change*/
	#sponsorBlockPopupLogo, .sponsorSkipLogo
	{
		display: block !important;
		-moz-box-sizing: border-box !important;
		box-sizing: border-box !important;
		background: url(https://raw.githubusercontent.com/RaitaroH/YouTube-DeepDark/master/YT_Images/IconSponsorBlocker256px.png) top left no-repeat !important;
		background-size: 100% !important;
		position: relative !important;
	}
	#sponsorBlockPopupLogo
	{
		width: 40px !important;
		height: 40px !important;
		padding-left: 40px !important;
	}
	/*for overlays*/
	.sponsorSkipLogo
	{
		width: 18px !important;
		height: 18px !important;
		padding-left: 18px !important;
	}

	/*Comments*/
	yt-formatted-string.ytd-comments-header-renderer,
	#contenteditable-root.yt-formatted-string[aria-label].yt-formatted-string:empty::before,
	#contenteditable-textarea.ytd-commentbox
	{
		color: var(--dimmer-text) !important;
	}
	/*sort by*/
	#icon-label.yt-dropdown-menu, #label-icon.yt-dropdown-menu
	{
		color: var(--main-text) !important;
		fill: var(--main-text) !important;
	}
	yt-sort-filter-sub-menu-renderer.ytd-comments-header-renderer:hover #icon-label.yt-dropdown-menu,
	yt-sort-filter-sub-menu-renderer.ytd-comments-header-renderer:hover #label-icon.yt-dropdown-menu
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	/*sort by dropdown*/
	paper-listbox.yt-dropdown-menu
	{
		background: var(--second-background) !important;
	}
	.item.yt-dropdown-menu
	{
		color: var(--main-text) !important;
	}
	paper-listbox.yt-dropdown-menu paper-item.yt-dropdown-menu:hover,
	paper-listbox.yt-dropdown-menu paper-item.yt-dropdown-menu:hover .item.yt-dropdown-menu
	{
		background: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	paper-listbox.yt-dropdown-menu .yt-dropdown-menu.iron-selected
	{
		background-color: var(--second-background) !important;
	}
	paper-listbox.yt-dropdown-menu .yt-dropdown-menu.iron-selected .item.yt-dropdown-menu
	{
		color: var(--main-color) !important;
	}
	/*text box*/
	#simplebox-placeholder.ytd-comment-simplebox-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#placeholder-area.ytd-comment-simplebox-renderer
	{
		border-color: var(--hover-background) !important;
	}
	#input-container.ytd-commentbox, ytd-commentbox
	{
		--paper-input-container-underline-color: var(--hover-background) !important;
		--paper-input-container-underline-focus-color: var(--main-color) !important;
	}
	.focused-line.tp-yt-paper-input-container
	{
		border-color: var(--main-color) !important;
	}
	.unfocused-line.tp-yt-paper-input-container
	{
		border-color: var(--dimmer-text) !important;
	}
	/*comments themselves*/
	#author-text.yt-simple-endpoint.ytd-comment-renderer
	{
		color: var(--main-text) !important;
	}
	#author-text.yt-simple-endpoint.ytd-comment-renderer:hover
	{
		color: var(--main-color) !important;
	}
	ytd-author-comment-badge-renderer
	{
		background-color: var(--hover-background) !important;
	}
	#content-text.ytd-comment-renderer,
	ytd-expander[should-use-number-of-lines][collapsed] > #content.ytd-expander
	{
		color: var(--dimmer-text) !important;
	}
	/*read more*/
	.more-button-exp.ytd-comment-renderer, .less-button-exp.ytd-comment-renderer
	{
		color: var(--main-text) !important;
	}
	.more-button-exp.ytd-comment-renderer:hover, .less-button-exp.ytd-comment-renderer:hover
	{
		color: var(--main-color) !important;
	}
	/*view replies*/
	paper-button.ytd-comment-replies-renderer, yt-next-continuation.ytd-comment-replies-renderer, yt-icon.ytd-comment-replies-renderer
	{
		color: var(--main-text) !important;
	}
	.more-button.style-scope.ytd-comment-replies-renderer:hover paper-button.ytd-comment-replies-renderer,
	.more-button.style-scope.ytd-comment-replies-renderer:hover yt-next-continuation.ytd-comment-replies-renderer,
	.more-button.style-scope.ytd-comment-replies-renderer:hover yt-icon.ytd-comment-replies-renderer
	{
		color: var(--main-color) !important;
	}
	/*likes*/
	#vote-count-middle.ytd-comment-action-buttons-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-button-renderer yt-formatted-string.ytd-button-renderer:hover
	{
		color: var(--main-color) !important;
	}
	/*Show more videos*/
	yt-next-continuation.ytd-watch-next-secondary-results-renderer
	{
		--paper-button_-_background-color: transparent !important;
		--paper-button_-_color: var(--dimmer-text) !important;
	}
	.style-scope.yt-next-continuation
	{
		border-color: transparent !important;
	}
	.style-scope.yt-next-continuation:hover
	{
		background-color: transparent !important;
		color: var(--main-color) !important;
	}
	yt-formatted-string.ytd-expanded-shelf-contents-renderer
	{
		color: var(--dimmer-text) !important;
	}
	yt-formatted-string.ytd-expanded-shelf-contents-renderer:hover
	{
		color: var(--main-color) !important;
	}
	/*View more comments*/
	paper-button.yt-next-continuation
	{
		color: var(--dimmer-text) !important;
	}
	/*Links in description and published date for comments*/
	#content.ytd-expander a
	{
		color: var(--main-color) !important;
		opacity: 0.9;
	}
	#published-time-text.ytd-comment-renderer, #published-time-text.ytd-comment-renderer a
	{
		--yt-endpoint-color: var(--dimmer-text) !important;
		color: var(--dimmer-text) !important;
		opacity: .8;
	}
	#content.ytd-expander a:hover, #published-time-text.ytd-comment-renderer a:hover, #content.ytd-expander #name.ytd-author-comment-badge-renderer:hover
	{
		color: var(--main-color) !important;
		opacity: 1 !important;
	}
	#content.ytd-expander #name.ytd-author-comment-badge-renderer
	{
		color: var(--main-text) !important;
	}

	/*Heart icon in comments*/
	#hearted-border.ytd-creator-heart-renderer,#hearted.ytd-creator-heart-renderer
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	yt-icon-button#creator-heart-button svg {
		fill: var(--main-color) !important;
	}

	/*Pinned by*/
	#label.ytd-pinned-comment-badge-renderer
	{
		color: var(--main-color) !important;
		opacity: 0.5;
	}
	yt-icon.ytd-pinned-comment-badge-renderer
	{
		fill: var(--main-color) !important;
		opacity: 0.5;
	}

	/*Fundraiser message*/
	#wrapper.ytd-donation-unavailable-renderer
	{
		background-color: var(--hover-background) !important;
	}

	/*Chat*/
	/*header*/
	yt-live-chat-header-renderer, #header.yt-live-chat-participant-list-renderer, yt-live-chat-message-renderer, yt-live-chat-ticker-renderer
	{
		background: var(--hover-background) !important;
	}
	yt-live-chat-banner-manager[has-active-banner]
	{
		background: linear-gradient(var(--hover-background) 0%, var(--second-background) 100%) !important;
	}
	/*live replay*/
	#card.yt-live-chat-viewer-engagement-message-renderer, yt-live-chat-text-message-renderer[is-highlighted]
	{
		background: var(--hover-background) !important;
	}
	#chat, #participants, yt-live-chat-renderer
	{
		background: var(--second-background) !important;
	}
	/*show mode was enabled*/
	#container.yt-live-chat-restricted-participation-renderer
	{
		background: var(--second-background) !important;
	}
	#contents.yt-live-chat-mode-change-message-renderer
	{
		background: var(--hover-background) !important;
	}
	#contents.yt-live-chat-mode-change-message-renderer, #subtext.yt-live-chat-mode-change-message-renderer
	{
		color: var(--dimmer-text) !important;
	}
	yt-live-chat-toast-renderer[is-showing-message] /*info for show mode*/
	{
		background: var(--hover-background) !important;
	}
	/*dropmenu*/
	#menu.yt-live-chat-text-message-renderer
	{
		background: transparent !important;
	}
	paper-listbox
	{
		background: var(--second-background) !important;
	}
	yt-icon.ytd-menu-navigation-item-renderer, yt-icon.ytd-menu-service-item-renderer, #header.yt-live-chat-participant-list-renderer,
	#author-name.yt-live-chat-author-chip, .style-scope.yt-live-chat-ninja-message-renderer
	{
		color: var(--main-text) !important;
	}
	#deleted-state, #show-original, yt-live-chat-text-message-renderer[is-deleted] #message.yt-live-chat-text-message-renderer,
	#timestamp
	{
		color: var(--dimmer-text) !important;
	}
	/*paid messages*/
	#content.yt-live-chat-paid-message-renderer #message
	{
		color: black !important;
	}
	#message.yt-live-chat-text-message-renderer a.yt-live-chat-text-message-renderer
	{
		color: var(--main-color) !important;
		text-decoration: none !important;
	}
	yt-live-chat-author-chip[is-highlighted] #author-name
	{
		background: var(--main-color) !important;
	}
	/*paid arrows*/
	yt-icon.yt-live-chat-ticker-renderer
	{
		background: var(--main-background) !important;
		color: var(--main-text) !important;
	}
	yt-icon.yt-live-chat-ticker-renderer:hover
	{
		color: var(--main-color) !important;
	}
	#right-arrow-container.yt-live-chat-ticker-renderer,
	#left-arrow-container.yt-live-chat-ticker-renderer
	{
		background: transparent !important;
	}
	/*channel messages*/
	yt-live-chat-text-message-renderer[author-is-owner]
	{
		background: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	/*pinned*/
	yt-live-chat-banner-manager[has-visible-banner]
	{
		background: var(--second-background) !important;
	}
	#contents.yt-live-chat-banner-renderer > .yt-live-chat-banner-renderer
	{
		background: transparent !important;
	}
	/*Confirmantion popup*/
	paper-toast
	{
		background-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	/*button*/
	yt-icon-button.yt-live-chat-item-list-renderer, yt-live-chat-ninja-message-renderer.yt-live-chat-renderer paper-button.yt-button-renderer,
	yt-live-chat-message-renderer.yt-live-chat-message-input-renderer yt-button-renderer.style-dark[is-paper-button]
	{
		background: var(--main-background) !important;
		color: var(--main-text) !important;
	}
	/*input*/
	yt-live-chat-message-input-renderer
	{
		background-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	#focused.yt-live-chat-text-input-field-renderer
	{
		background: var(--main-color) !important;
	}
	#count
	{
		color: var(--dimmer-text) !important;
	}
	/*hide chat*/
	#show-hide-button.ytd-live-chat-frame > ytd-toggle-button-renderer.ytd-live-chat-frame
	{
		background: var(--hover-background) !important;
	}
	/*emoji*/
	yt-formatted-string.yt-emoji-picker-category-renderer
	{
		background: var(--hover-background) !important;
	}
	#search-panel.yt-emoji-picker-renderer
	{
		background: var(--main-background) !important;
		color: var(--main-text) !important;
	}
	#search-empty
	{
		color: var(--dimmer-text) !important;
	}
	/*donations superchats cards*/
	#card.yt-live-chat-donation-announcement-renderer
	{
		background-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	#menu.yt-live-chat-donation-announcement-renderer
	{
		background: transparent !important;
	}
	/*for actually donating*/
	#subtext.yt-live-chat-product-button-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#container.yt-live-chat-product-button-renderer .yt-icon
	{
		fill: var(--dimmer-text) !important;
	}

	/*Fund raiser*/
	#header-section.ytd-donation-shelf-renderer,
	#collapse-controls-section.ytd-donation-shelf-renderer
	{
		background-color: var(--hover-background) !important;
	}
	#header-text.ytd-donation-shelf-renderer,
	#collapse-controls-section.ytd-donation-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	#collapse-controls-section.ytd-donation-shelf-renderer:hover
	{
		color: var(--main-color) !important;
	}
	#header-section.ytd-donation-shelf-renderer .style-scope.ytd-donation-shelf-renderer.no-transition
	{
		filter: invert(.8);
	}
	#donate-section.ytd-donation-shelf-renderer,
	#creator-messages-section.ytd-donation-shelf-renderer, #nonprofit-section.ytd-donation-shelf-renderer,
	#nonprofit-title.ytd-donation-shelf-renderer
	{
		background-color: var(--second-background) !important;
		border-color: var(--hover-background) !important;
	}
	#campaign-title.ytd-donation-shelf-renderer,
	.creator-message.ytd-donation-shelf-renderer, #campaign-subtitle.ytd-donation-shelf-renderer, .creator-message-name.ytd-donation-shelf-renderer,
	#nonprofit-title.ytd-donation-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	.creator-message.ytd-donation-shelf-renderer, #campaign-subtitle.ytd-donation-shelf-renderer,
	#nonprofit-subtitle.ytd-donation-shelf-renderer,
	#nonprofit-description.ytd-donation-shelf-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#amount-raised.ytd-donation-shelf-renderer,
	#nonprofit-title.ytd-donation-shelf-renderer yt-icon.ytd-donation-shelf-renderer
	{
		color: var(--main-color) !important;
	}
	#nonprofit-link.ytd-donation-shelf-renderer .inline-icon.ytd-donation-shelf-renderer
	{
		fill: var(--main-color) !important;
	}
	/*progress*/
	#progress-bar-start.ytd-donation-shelf-renderer, #progress-bar-end.ytd-donation-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	#matching-label.ytd-donation-shelf-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#progress-bar.ytd-donation-shelf-renderer
	{
		background-color: var(--dimmer-text) !important;
	}
	#progress-bar-fill.ytd-donation-shelf-renderer
	{
		background-color: var(--main-color) !important;
	}
	/*donate button*/
	#donate-section.ytd-donation-shelf-renderer ytd-button-renderer.style-primary[is-paper-button],
	.b3-button.jfk-button, .b3-button.jfk-button.jfk-button-action
	{
		background-color: var(--main-color) !important;
	}
	/*donate window*/
	#top-box.ytd-donation-amount-picker-renderer
	{
		background-color: var(--second-background) !important;
	}
	#campaign-title.ytd-donation-amount-picker-renderer,
	#nonprofit-title.ytd-donation-amount-picker-renderer
	{
		color: var(--main-color) !important;
	}
	#campaign-subtitle.ytd-donation-amount-picker-renderer,
	#nonprofit-subtitle.ytd-donation-amount-picker-renderer
	{
		color: var(--main-text) !important;
	}
	/*amount buttons*/
	#suggested-amount-buttons-row.ytd-donation-amount-picker-renderer ytd-button-renderer.ytd-donation-amount-picker-renderer[is-paper-button] paper-button.ytd-button-renderer
	{
		background-color: var(--second-background) !important;
	}
	#suggested-amount-buttons-row.ytd-donation-amount-picker-renderer ytd-button-renderer.ytd-donation-amount-picker-renderer[is-paper-button] paper-button.ytd-button-renderer
	{
		background-color: var(--second-background) !important;
		border-color: var(--second-background) !important;
	}
	#suggested-amount-buttons-row.ytd-donation-amount-picker-renderer ytd-button-renderer.ytd-donation-amount-picker-renderer[is-paper-button][selected] paper-button.ytd-button-renderer,
	.ytd-donation-amount-picker-renderer ytd-button-renderer.style-primary[is-paper-button]
	{
		background-color: var(--main-color) !important;
	}
	/*curency for other amount*/
	span.prefix.style-scope.paper-input-container > div.ytd-donation-amount-picker-renderer
	{
		color: var(--main-text) !important;
	}

	/*Payment window*/
	.popup-mode .b3-page-header
	{
		background-color: var(--main-background) !important;
	}
	.b3-line-items-mundane-items-container, .b3-line-items-mundane-items-container
	{
		background-color: var(--hover-background) !important;
	}
	.b3-separator
	{
		display: none !important;
	}
	.b3-line-item-value
	{
		color: var(--main-color) !important;
	}
	.b3-line-item-name, .b3-line-item-infomessage, .b3-line-item-subvalue
	{
		color: var(--main-text) !important;
	}
	.b3-single-option-form-selector-option-content .b3-existing-instrument-option-label-without-image,
	.b3-dropdown-form-selector .b3-existing-instrument-option-label-without-image,
	.b3-single-option-form-selector-option-content .b3-additional-instrument-option-label, .b3-dropdown-form-selector .b3-additional-instrument-option-label,
	.b3-input.focused .b3-input-label, .b3-input.focused .b3-input-label-text,
	.b3-input input[type="tel"], .b3-input input[type="text"], .b3-input input[type="password"], .b3-input input[type="email"],
	.b3-input.populated .b3-input-label, .b3-input.invalid .b3-input-label, .b3-input.autofilled .b3-input-label,
	.b3-input-field > .b3-input-label, .b3-input-field > .b3-input-label.accessible,
	.b3-collapsing-form-placeholder-text
	{
		color: var(--main-text) !important;
	}
	.countryselector .goog-flat-menu-button-caption, .countryselector .goog-flat-menu-button-caption .goog-menuitem-content
	{
		color: var(--dimmer-text) !important;
	}
	/*icons*/
	.b3-single-option-form-selector-icon,
	.b3-collapsing-form-icon
	{
		fill: var(--main-text) !important;
	}
	.b3-collapsing-form.focused .b3-collapsing-form-icon
	{
		fill: var(--main-color) !important;
	}
	.b3-tooltip-icon
	{
		filter: invert(1) !important;
	}
	/*border*/
	.b3-input-status-indicator
	{
		background-color: var(--main-color) !important;
	}
	.b3-input-accent
	{
		border-color: var(--hover-background) !important;
	}
	/*tooltip*/
	.b3-inline-tooltip-popup-wrapper, .help-Helpwidgets-TooltipWidget-content-html
	{
		background-color: var(--hover-background) !important;
		color: var(--dimmer-text) !important;
	}
	.b3-inline-tooltip-popup-wrapper a, .help-Helpwidgets-TooltipWidget-content-html a
	{
		color: var(--main-color) !important;
	}
	/*country choice*/
	.goog-menu, .goog-menuitem:hover
	{
		background-color: var(--hover-background) !important;
	}
	.goog-menuitem, .goog-tristatemenuitem, .goog-filterobsmenuitem
	{
		color: var(--main-text) !important;
	}
	.goog-menuitem-highlight .goog-menuitem-content
	{
		color: var(--main-color) !important;
	}
	.goog-menuitem .countryselector-flag
	{
		border-radius: 4px !important; /*hiding ugly white corners*/
	}
	/*footer*/
	.b3-legal-message-content, .b3-info-message-list.b3-buyflow-extra-messages .b3-info-message-component.b3-info-message-unknown,
	.b3-info-message-component.b3-info-message-unknown.b3-buyflow-extra-messages .b3-info-message-html
	{
		color: var(--dimmer-text) !important;
	}
	.b3-legal-message-content a, .b3-info-message-component.b3-info-message-unknown.b3-buyflow-extra-messages .b3-info-message-html a
	{
		color: var(--main-color) !important;
	}

	/*Notification*/
	/*load spinner - also for comments*/
	.spinner-layer.layer-1.tp-yt-paper-spinner, .spinner-layer.layer-2.tp-yt-paper-spinner,
	.spinner-layer.layer-3.tp-yt-paper-spinner, .spinner-layer.layer-4.tp-yt-paper-spinner
	{
		color: var(--dimmer-text) !important;
	}
	#notification-count.ytd-notification-topbar-button-renderer,
	ytd-notification-renderer.unread #new.ytd-notification-renderer,
	.yt-lockup-notification .unread-dot /*account settings*/
	{
		background: var(--main-color) !important;
		border-color: var(--main-color) !important;
	}
	.text.ytd-notification-renderer,
	.message.ytd-notification-renderer
	#yt-masthead-notifications-title, .yt-lockup-notification .yt-lockup-title a /*account settings*/
	h2.yt-multi-page-menu-section-renderer /*comments and notifications headers*/
	{
		color: var(--main-text) !important;
	}
	.metadata.ytd-notification-renderer,
	.exp-responsive .yt-lockup-tile .yt-lockup-byline /*account settings*/
	{
		color: var(--dimmer-text) !important;
	}
	ytd-notification-renderer:hover .message.ytd-notification-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-watch:not([flexy-fit-to-video_]) #chat.ytd-watch, ytd-watch:not([flexy-fit-to-video_]) #transcript.ytd-watch
	{
		padding-left: 0 !important;
	}
	ytd-simple-menu-header-renderer
	{
		background-color: var(--hover-background) !important;
	}
	h2.ytd-simple-menu-header-renderer
	{
		color: var(--main-text) !important;
	}
	#sections.ytd-multi-page-menu-renderer > ytd-background-promo-renderer.ytd-multi-page-menu-renderer,
	ytd-multi-page-menu-renderer,
	#yt-masthead-notifications-content .item-section > li > .yt-lockup-tile, #yt-masthead-notifications-content .yt-ui-ellipsis, /*account settings*/
	#yt-masthead-notifications-content /*bottom thing - account settings*/
	{
		background: var(--second-background) !important;
		border-color: var(--second-background) !important;
	}
	.browse-items-load-more-button
	{
		background-color: var(--main-background) !important;
		border-color: var(--main-background) !important;
		color: var(--main-text) !important;
	}
	.browse-items-load-more-button:hover
	{
		color: var(--main-color) !important;
	}
	.promo-message.ytd-background-promo-renderer, #message:not([class*="yt-music"])
	{
		color: var(--dimmer-text) !important;
	}
	/*triangle*/
	.yt-uix-clickcard-card-reverse .yt-uix-card-body-arrow-vertical, .yt-uix-hovercard-card-reverse .yt-uix-card-body-arrow-vertical /*account settings*/
	{
		border-bottom-color: var(--hover-background) !important;
	}
	/*menu*/
	.yt-ui-menu-content /*account settings*/
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	.yt-ui-menu-item /*account settings*/
	{
		background-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	.yt-ui-menu-item:hover /*account settings*/
	{
		color: var(--main-color) !important;
	}
	/*gear icon*/
	.yt-uix-button-icon-icon-account-settings /*account settings*/
	{
		filter: brightness(250%) invert(1);
	}

	/*Cards*/
	.iv-card-content,.ytp-ce-expanding-overlay-background,.ytp-cards-teaser .ytp-cards-teaser-text, .ytp-cards-teaser .ytp-cards-teaser-box
	{
		background-color: var(--main-background) !important;
	}
	.ytp-cards-teaser .ytp-cards-teaser-box,.iv-card-image
	{
		border: 0px !important;
	}
	.iv-card-content > :first-child,.html5-video-player a,.iv-card h2,.ytp-cards-teaser .ytp-cards-teaser-text
	{
		color: var(--main-text) !important;
	}
	.iv-card:hover .iv-card-primary-link,.ytp-ce-website-title
	{
		color: var(--main-color) !important;
	}
	.ytp-ce-element:hover
	{
		border-color: var(--main-color) !important;
	}
	.ytp-ce-channel-title.ytp-ce-link
	{
		color: var(--main-color) !important;
		opacity: 0.9 !important;
	}
	.ytp-ce-channel-title.ytp-ce-link:hover,.ytp-cards-teaser .ytp-cards-teaser-text:hover
	{
		color: var(--main-color) !important;
		opacity: 1 !important;
	}
	.ytp-ce-channel-metadata.yt-ui-ellipsis.yt-ui-ellipsis-3
	{
		background: transparent;
		color: var(--dimmer-text) !important;
	}
	/*Cards border color*/
	.iv-card-message
	{
		border-bottom: 1px solid var(--main-color) !important;
	}
	.ytp-ce-channel-this .ytp-ce-channel-metadata
	{
		border-color: var(--hover-background) !important;
	}

	/*Poll*/
	.iv-card-poll label, .iv-card-poll.iv-card-poll-voted label.iv-card-poll-choice-checked, .iv-card-poll.iv-card-poll-voted label
	{
		color: var(--main-text) !important;
	}
	#vote-info.ytd-backstage-poll-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.iv-card-poll .iv-card-poll-result .iv-card-poll-result-bar
	{
		background-color: var(--main-color) !important;
	}
	ytd-backstage-post-thread-renderer
	{
		border-color: var(--hover-background) !important;
	}
	ytd-backstage-poll-renderer[show-poll-choice-border] .choice-info.ytd-backstage-poll-renderer
	{
		border-color: transparent !important;
	}

	/*Account menu header*/
	ytd-active-account-header-renderer
	{
		background: var(--second-background) !important;
	}
	ytd-active-account-header-renderer:hover
	{
		background-color: var(--hover-background) !important;
	}
	#account-name.ytd-active-account-header-renderer, #channel-title.ytd-account-item-renderer
	{
		color: var(--main-text) !important;
	}
	#email.ytd-active-account-header-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*subentries*/
	#label.ytd-toggle-theme-compact-link-renderer,
	tp-yt-paper-item.ytd-compact-link-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-toggle-theme-compact-link-renderer:hover #label.ytd-toggle-theme-compact-link-renderer,
	ytd-toggle-theme-compact-link-renderer:hover yt-icon,
	paper-item.ytd-compact-link-renderer:hover #subtitle,
	paper-item.ytd-compact-link-renderer:hover .deemphasize.yt-formatted-string,
	tp-yt-paper-item.ytd-compact-link-renderer:hover *,
	tp-yt-paper-item.ytd-compact-link-renderer:hover #subtitle.ytd-compact-link-renderer
	{
		color: var(--main-color) !important;
	}
	#footer.ytd-multi-page-menu-renderer > .ytd-multi-page-menu-renderer
	{
		border-color: var(--hover-background) !important;
	}
	.description.ytd-toggle-item-renderer, #caption.ytd-toggle-item-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*language*/
	#language.ytd-account-settings, #country.ytd-account-settings, #restricted.ytd-account-settings, .container.ytd-account-settings
	{
		background-color: var(--second-background) !important;
	}
	paper-item.ytd-account-settings
	{
		color: var(--dimmer-text) !important;
	}
	paper-item.ytd-account-settings:hover
	{
		color: var(--main-color) !important;
	}
	/*swich account*/
	yt-formatted-string.ytd-account-item-renderer[secondary]
	{
		color: var(--dimmer-text) !important;
	}
	#selected.ytd-account-item-renderer
	{
		color: var(--main-color) !important;
	}
	/*theme*/
	ytd-compact-link-renderer[compact-link-style="compact-link-style-type-disclaimer"] #label.ytd-compact-link-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Live background color*/
	ytd-thumbnail-overlay-time-status-renderer[overlay-style="LIVE"]
	{
		background-color: var(--main-color) !important;
	}

	.guide-entry-badge.ytd-guide-entry-renderer
	{
		color: var(--main-color) !important;
		fill: var(--main-color) !important;
	}
	.ytp-live-badge[disabled]:before
	{
		background: var(--main-color) !important;
	}

	/*Recolored sidepane icons, menu icons and filter button*/
	.guide-icon.ytd-guide-entry-renderer, paper-button.ytd-toggle-button-renderer, yt-icon.ytd-compact-link-renderer, yt-icon.ytd-toggle-theme-compact-link-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Sidepane titles*/
	#guide-section-title a
	{
		color: var(--dimmer-text) !important;
	}
	#guide-section-title a:hover
	{
		color: var(--main-color) !important;
	}


	/*Autoplay text*/
	#upnext.ytd-compact-autoplay-renderer, #autoplay.ytd-compact-autoplay-renderer
	{
		color: var(--dimmer-text) !important;
		opacity: .8;
	}
	ytd-compact-autoplay-renderer
	{
		border-color: var(--hover-background) !important;
	}

	/*Video was removed by user - not interested*/
	#text.ytd-notification-multi-action-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Links in video description*/
	.description.ytd-video-secondary-info-renderer a
	{
		color: var(--main-color) !important;
		opacity: .9;
	}

	/*Game cards*/
	ytd-rich-metadata-renderer
	{
		background-color: var(--second-background) !important;
	}
	#call-to-action.ytd-rich-metadata-renderer
	{
		color: var(--main-text) !important;
	}
	#title.ytd-rich-metadata-renderer, #call-to-action.ytd-rich-metadata-renderer:hover
	{
		color: var(--main-color) !important;
	}

	/*Movie cards*/
	#header.ytd-movie-offer-module-renderer
	{
		background-color: var(--second-background) !important;
	}
	ytd-button-renderer.ytd-movie-offer-module-renderer.style-primary[is-paper-button] {
		background-color: var(--main-color) !important;
	}
	#wide-clickable-area.ytd-movie-offer-module-renderer {
		background-color: var(--hover-background) !important;
	}
	#info.ytd-movie-offer-module-renderer {
		color: var(--main-text) !important;
	}
	h3.ytd-compact-movie-renderer {
		color: var(--main-text) !important;
	}

	/*Tour/ticket cards*/
	ytd-ticket-shelf-renderer
	{
		background-color: var(--second-background) !important;
	}
	#primary-event.ytd-ticket-shelf-renderer #meta.ytd-ticket-shelf-renderer #tickets-button.ytd-ticket-shelf-renderer
	{
		background: var(--main-color) !important;
		color: var(--main-text) !important;
	}
	#primary-event.ytd-ticket-shelf-renderer #meta-info.ytd-ticket-shelf-renderer #nearest.ytd-ticket-shelf-renderer,
	#primary-event.ytd-ticket-shelf-renderer #meta-info.ytd-ticket-shelf-renderer #subtitle1.ytd-ticket-shelf-renderer,
	#primary-event.ytd-ticket-shelf-renderer #meta-info.ytd-ticket-shelf-renderer #subtitle2.ytd-ticket-shelf-renderer,
	.where-column-td.ytd-ticket-shelf-renderer .where-column.ytd-ticket-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	.when-date-column.ytd-ticket-shelf-renderer, .link.ytd-ticket-shelf-renderer, .when-weekday-column.ytd-ticket-shelf-renderer
	{
		color: var(--main-color) !important;
	}
	/*separator*/
	#seperator.ytd-ticket-shelf-renderer, ytd-ticket-shelf-renderer
	{
		border-color: var(--hover-background) !important;
	}


	/*Author name*/
	#owner-name.ytd-video-owner-renderer
	{
		opacity: .9;
	}
	#owner-name.ytd-video-owner-renderer:hover
	{
		opacity: 1 !important;
	}

	/*Set a memento*/
	ytd-toggle-button-renderer.style-compact-gray[is-paper-button]
	{
		background-color: var(--second-background) !important;
		color: var(--dimmer-text) !important;
	}

	/*Series name*/
	.super-title.ytd-video-primary-info-renderer a, #additional-metadata-line.ytd-video-meta-block
	{
		color: var(--dimmer-text) !important;
		opacity: .8;
	}

	#selectionBar.paper-tabs
	{
		border-color: var(--main-color) !important;
	}

	/*"Best" of YouTube icons in sidepane*/
	/*.style-scope.ytd-guide-entry-renderer.no-transition
	{
		filter: grayscale(100%);
	}*/

	/* Promo page */
	body.yt-new-promo-page-use-launched-copy .yt-new-promo-page-header
	{
		background: var(--main-background) !important;
	}
	.yt-new-promo-page-section-text, .yt-new-promo-page-header
	{
		color: var(--dimmer-text);
	}
	.yt-new-promo-page-button
	{
		background-color: var(--main-color) !important;
		color: var(--main-text) !important;
		opacity: .9;
	}
	.yt-new-promo-page-button:hover
	{
		opacity: 1;
	}
	/* Crude logo fix */
	.yt-new-promo-page-logo
	{
		filter: grayscale(100%) invert(100%);
	}
	/* Fix for active like/dislike buttons */
	ytd-toggle-button-renderer.style-grey-text[is-icon-button]
	{
		color: var(--yt-button-color);
	}
	ytd-toggle-button-renderer #button.ytd-toggle-button-renderer
	{
		color: inherit;
	}
	/*like/dislike buttons in nested replies*/
	/*.style-scope.ytd-toggle-button-renderer svg
	{
		fill: var(--dimmer-text) !important;
	}
	.style-scope.ytd-toggle-button-renderer yt-icon-button.style-default-active svg
	{
		fill: var(--main-color) !important;
	}*/
	ytd-toggle-button-renderer.ytd-comment-action-buttons-renderer #button.ytd-toggle-button-renderer
	{
		color: var(--yt-button-color);
	}
	ytd-toggle-button-renderer.ytd-comment-action-buttons-renderer .style-default-active
	{
		color: var(--main-color) !important;
	}

	/* Fix for placeholders/skeletons */
	/*ytd-masthead.shell
	{
		background-color: var(--main-background);
	}
	ytd-masthead.shell [class*='skeleton'], [id*='skeleton'] [class*='skeleton'], [id*='skeleton'], .shelf-videos, .skeleton-bg-color
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}*/
	/*homepage skeleton*/
	#home-container-skeleton, html[dark] #home-container-skeleton
	{
		background-color: var(--main-background) !important;
	}
	/*sidebar skeleton*/
	#guide-skeleton, html[dark] #guide-skeleton
	{
		background-color: var(--second-background) !important;
	}
	/*homepage videos skeleton*/
	#home-page-skeleton .skeleton-bg-color,
	html[dark] #home-page-skeleton .skeleton-bg-color
	{
		background-color: var(--hover-background) !important;
	}
	.masthead-skeleton-icon, html[dark] .masthead-skeleton-icon,
	/*ytd-masthead.shell [class*='skeleton'], html[dark] ytd-masthead.shell,
	.shelf-videos, html[dark] .shelf-videos,*/
	.skeleton-bg-color, html[dark] .skeleton-bg-color
	{
		background-color: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
	}
	.skeleton-light-border-bottom,
	html[dark] .skeleton-light-border-bottom
	{
		border-bottom: 1px solid var(--hover-background) !important;
	}

	ytd-alert-with-button-renderer[type="INFO"],
	#content-wrapper.yt-alert-with-actions-renderer /*TOS*/
	{
		background-color: var(--hover-background) !important;
	}
	#content-wrapper.yt-alert-with-actions-renderer yt-button-renderer[is-paper-button] yt-icon.yt-button-renderer
	{
		color: var(--main-color) !important;
	}
	ytd-alert-with-button-renderer[type="INFO"] #text.ytd-alert-with-button-renderer
	{
		color: var(--main-text) !important;
	}
	#alert-message.ytd-consent-bump-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Paid membership*/
	yt-subscription-product-header-renderer.ytd-item-section-renderer
	{
		color: var(--main-text) !important;
	}

	/*Reporting*/
	.introduction-header
	{
		color: var(--main-text) !important;
	}
	.introduction-body, .introduction-bullet-items
	{
		color: var(--dimmer-text) !important;
	}
	yt-report-form-modal-renderer[dialog][dialog][dialog]
	{
		background: var(--main-background) !important;
	}
	yt-options-renderer[increased-tooltip-target] yt-icon.yt-options-renderer
	{
		color: var(--main-text) !important;
	}

	/*Help*/
	.ghp-header-searchBox, .ghp-autocomplete-label
	{
		color: var(--dimmer-text) !important;
	}
	/*
	.ghp-header-searchIcon.ghpv-loaded, .ghp-iconTextComponent-icon, .ghp-autocomplete-icon
	{
		filter: invert(100%) grayscale(100%) brightness(150%);
	}
	.ghp-autocompleteGlass
	{
		background: rgba(0,0,0,3) !important;
	}
	.ghp-card-title
	{
		color: var(--main-text) !important;
	}
	.ghp-card, .ghp-content, .ghp-iconTextComponent, .ghp-contentFrame, .hcfe
	{
		background-color: var(--second-background) !important;
		border-color: var(--hover-background) !important;
	}
	.ghp-iconTextComponent:hover .ghp-iconTextComponent-label,
	.ghp-iconTextComponent:hover .ghp-separator
	{
		color: var(--main-color) !important;
		border-color: var(--hover-background) !important;
	}
	.ghp-separator
	{
		border-color: var(--hover-background) !important;
	}
	.ghp-iconTextComponent-label, .hcfe
	{
		color: var(--dimmer-text) !important;
	}
	*/

	/*Trending page*/
	ytd-destination-button-renderer
	{
		background-color: var(--hover-background) !important;
	}
	#destination-label.ytd-destination-button-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-destination-button-renderer:hover #destination-label.ytd-destination-button-renderer
	{
		color: var(--main-color) !important;
	}
	/*more - shown on low width*/
	ytd-destination-shelf-renderer[is-show-more-visible] #show-more-button.ytd-destination-shelf-renderer,
	#show-more-button.ytd-destination-shelf-renderer
	{
		background: var(--hover-background) !important;
	}
	#show-more-button-icon.ytd-destination-shelf-renderer
	{
		color: var(--main-text) !important;
	}
	ytd-destination-shelf-renderer[is-show-more-visible] #show-more-button.ytd-destination-shelf-renderer:hover #show-more-button-icon.ytd-destination-shelf-renderer
	{
		color: var(--main-color) !important;
	}

	/*Learning*/
	ytd-carousel-header-renderer
	{
		background: var(--main-background) !important;
	}

	/*Music*/
	.flex-container.ytd-compact-station-renderer
	{
		background-color: var(--second-background) !important;
	}
	h3.ytd-compact-station-renderer
	{
		color: var(--main-text) !important;
	}
	.flex-container.ytd-compact-station-renderer:hover h3.ytd-compact-station-renderer
	{
		color: var(--main-color) !important;
	}
	#video-count-text.ytd-compact-station-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Gaming*/
	#live-viewers-count.ytd-game-details-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*History*/
	yt-formatted-string.ytd-sub-feed-option-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#title.ytd-sub-feed-selector-renderer, ytd-sub-feed-option-renderer.ytd-sub-feed-selector-renderer
	{
		border-color: var(--hover-background) !important;
	}
	ytd-two-column-browse-results-renderer #secondary.ytd-two-column-browse-results-renderer
	{
		background-color: var(--second-background) !important;
	}
	ytd-two-column-browse-results-renderer #primary ytd-text-header-renderer
	{
		color: var(--main-text) !important;
	}
	/*dialog confirm*/
	yt-confirm-dialog-renderer[dialog][dialog][dialog]
	{
		background-color: var(--second-background) !important;
	}
	#scroller.yt-confirm-dialog-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#cancel-button.yt-confirm-dialog-renderer
	{
		color: var(--main-text) !important;
	}
	.buttons.yt-confirm-dialog-renderer
	{
		border-color: var(--hover-background) !important;
	}

	/*Premium*/
	/*video*/
	#main-title.ytd-unlimited-offer-module-renderer
	{
		color: var(--main-text) !important;
	}
	#sub-title.ytd-unlimited-offer-module-renderer
	{
		color: var(--dimmer-text) !important;
	}
	/*popup*/
	.ytd-mealbar-promo-renderer-message-title.ytd-mealbar-promo-renderer
	{
		color: var(--main-text) !important;
	}
	.ytd-mealbar-promo-renderer-message-text.ytd-mealbar-promo-renderer
	{
		color: var(--dimmer-text) !important;
	}
	.button-container.ytd-mealbar-promo-renderer
	{
		border-color: var(--hover-background) !important;
	}

	ytd-grid-video-renderer[is-dismissed] #dismissed
	{
		border-color: var(--hover-background) !important;
	}
	ytd-grid-video-renderer[is-dismissed] #dismissed .ytd-notification-multi-action-renderer
	{
		color: var(--dimmer-text) !important;
	}
	ytd-dismissal-follow-up-renderer[dialog][dialog][dialog]
	{
		background: var(--main-background) !important;
	}
	#content.ytd-dismissal-follow-up-renderer #checkboxLabel.paper-checkbox,
	#content.ytd-dismissal-follow-up-renderer #label.ytd-dismissal-reason-video-renderer
	{
		color: var(--dimmer-text) !important;
	}
	#buttons.ytd-dismissal-follow-up-renderer
	{
		border-top-color: var(--hover-background) !important;
	}

	/*New TOS*/
	yt-alert-with-actions-renderer
	{
		background-color: var(--hover-background) !important;
	}
	#text.yt-alert-with-actions-renderer, #alert-message.yt-alert-with-actions-renderer
	{
		color: var(--main-text) !important;
	}
	yt-button-renderer yt-formatted-string.yt-button-renderer,
	#icon.yt-alert-with-actions-renderer
	{
		color: var(--main-color) !important;
	}
	/*actual page for TOS*/
	#yts-article #article-container.ytg-box #summary
	{
		background-color: var(--hover-background) !important;
	}
	.separator, .with-divider, .header, #yts-article #header, #yts-nav
	{
		border-color: var(--hover-background) !important;
	}
	#yts-nav .indented .sub-level a, #yts-nav .top-level a, #yts-article #header
	{
		color: var(--main-text) !important;
	}

	/*Premium page (https://www.youtube.com/premium)*/
	yt-button-renderer#manage-subscription-button yt-formatted-string.yt-button-renderer
	{
		color: inherit !important;
	}
	.yt-unlimited-page-header-renderer a.yt-simple-endpoint.yt-formatted-string
	{
		color: var(--main-color) !important;
	}
	#header.yt-music-pass-small-feature-info-renderer,
	.question.yt-generic-faq-question-renderer,
	.answer-arrow.yt-generic-faq-question-renderer
	{
		color: var(--main-text) !important;
	}
	#description.yt-music-pass-small-feature-info-renderer,
	.container.yt-faq-section-renderer,
	.answer.yt-generic-faq-question-renderer,
	.text.ytd-simple-text-section-renderer
	{
		color: var(--dimmer-text) !important;
	}
	yt-generic-faq-question-renderer .yt-simple-endpoint.style-scope.yt-formatted-string,
	yt-generic-faq-question-renderer a.yt-simple-endpoint.yt-formatted-string:only-of-type,
	.text.ytd-simple-text-section-renderer a.yt-simple-endpoint.yt-formatted-string:only-of-type
	{
		color: var(--main-color) !important;
	}

	/*Paid memberships*/
	paper-card.yt-subscription-product-upsell-offer-renderer
	{
		background-color: var(--second-background) !important;
	}
	#title.yt-subscription-product-upsell-offer-renderer,
	#description.yt-subscription-product-upsell-offer-renderer,
	#additional-info.yt-subscription-product-upsell-offer-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Gaming page (https://www.youtube.com/gaming) and gaming channels*/
	#channel-details.ytd-carousel-header-renderer,
	#channel-header-container.ytd-topic-channel-details-renderer
	{
		background-color: var(--main-background) !important;
	}
	#bg.ytd-interactive-tabbed-header-renderer
	{
		fill: var(--main-background) !important;
	}
	#tabs-inner-container.ytd-interactive-tabbed-header-renderer
	{
		background-color: transparent !important;
	}

	/*Acount page specific*/
	/*Sidebar*/
	#creator-page.account-page, ytd-settings-sidebar-renderer
	{
		background-color: var(--second-background) !important;
	}
	.exp-kevlar-settings .account-page #creator-sidebar h3
	{
		color: var(--main-text) !important;
	}
	.exp-kevlar-settings .account-page #creator-sidebar .creator-sidebar-item a
	{
		color: var(--dimmer-text) !important;
	}
	.exp-kevlar-settings .account-page #creator-sidebar .creator-sidebar-item.selected > a, .exp-kevlar-settings .account-page #creator-sidebar .creator-sidebar-item.selected > a:hover,
	.exp-kevlar-settings .account-page #creator-sidebar .creator-sidebar-item:hover a
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	ytd-compact-link-renderer[compact-link-style="compact-link-style-type-settings-sidebar"][active],
	ytd-compact-link-renderer[compact-link-style="compact-link-style-type-settings-sidebar"][active]:hover
	{
		background-color: var(--hover-background) !important;
	}
	/*Burger sidebar*/
	#appbar-guide-menu, .guide-flyout
	{
		background-color: var(--second-background) !important;
	}
	#guide-container .guide-item
	{
		color: var(--main-text) !important;
	}
	#guide-container .guide-item:hover
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	/*headers*/
	.exp-invert-logo li.guide-section h3, .exp-invert-logo li.guide-section h3 a
	{
		color: var(--main-color) !important;
	}
	.guide-section-separator /*divider*/
	{
		border-color: var(--hover-background) !important;
	}
	/*Contents - account*/
	.account-page-header,
	ytd-section-list-renderer[page-subtype="account-settings"] a.yt-simple-endpoint.yt-formatted-string
	{
		color: var(--main-color) !important;
	}
	#account-page-header-title, h2.account-section-header
	{
		color: var(--main-text) !important;
	}
	/*title of the page*/
	#name.ytd-page-introduction-renderer,
	#name.ytd-channel-options-renderer,
	ytd-settings-options-renderer .yt-formatted-string:not(a).bold
	{
		color: var(--main-text) !important;
	}
	.exp-kevlar-settings #account-page-header-subtitle, .account-info-item .account-info-label,
	.account-section .account-email, .account-content, .account-section-subtext
	{
		color: var(--dimmer-text) !important;
	}
	/*other text*/
	#text.ytd-page-introduction-renderer, /*email*/
	#text.ytd-settings-options-renderer, /*descriptions, metadata, below text*/
	#label.ytd-settings-checkbox-renderer, #label.ytd-settings-radio-option-renderer, /*playback*/
	#text.ytd-connected-app-renderer /*connected accounts*/
	{
		color: var(--dimmer-text) !important;
	}
	.yt-horizontal-rule /*divider*/
	{
		border-color: var(--hover-background) !important;
	}
	.account-info .account-photo .yt-thumb /*avatar*/
	{
		border-radius: 100%;
	}
	.account-content a, .account-header a /*various links*/
	{
		color: var(--main-color) !important;
	}
	.yt-thumb
	{
		background-color: var(--hover-background) !important;
	}
	/*Notifications*/
	.setting-reminder, h3.account-section-header
	{
		color: var(--main-text) !important;
	}
	.yt-uix-form-input-checkbox-container input:checked + .yt-uix-form-input-checkbox-element
	{
		border-color: #000;
		filter: invert(1);
	}
	.desktop-notifications .browser
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
		border-color: var(--hover-background) !important;
	}
	.desktop-notifications .browser .yt-uix-button.turn-on, .desktop-notifications .browser .yt-uix-button.turn-off, .resume-setting-button, .undo-setting-button-section, .resume-all-settings-button /*turn off*/
	{
		background: var(--main-background) !important;
		border-color: var(--main-background) !important;
		color: var(--main-color) !important;
	}
	.yt-uix-form-input-select /*dropdowns*/
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	/*checkboxes*/
	tp-yt-paper-toggle-button[checked]:not([disabled]) .toggle-bar.tp-yt-paper-toggle-button
	{
		background-color: var(--main-color) !important;
		opacity: 1 !important;
	}
	tp-yt-paper-toggle-button[checked]:not([disabled]) .toggle-button.tp-yt-paper-toggle-button
	{
		background-color: var(--main-text) !important;
	}
	/*language*/
	ytd-dropdown-renderer[has-background] tp-yt-paper-dropdown-menu-light.ytd-dropdown-renderer
	{
		background-color: var(--hover-background) !important;
	}
	label.label-is-floating.tp-yt-paper-dropdown-menu-light,
	#label.ytd-dropdown-item-renderer
	{
		color: var(--main-text) !important;
	}
	#input.tp-yt-paper-dropdown-menu-light
	{
		color: var(--dimmer-text) !important;
	}
	/*Playback*/
	.yt-help-icon
	{
		filter: invert(1);
	}
	.yt-uix-clickcard-card-content, .yt-uix-hovercard-card-content
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	.yt-uix-clickcard-card-border, .yt-uix-hovercard-card-border
	{
		border-color: var(--hover-background) !important;
	}
	.yt-uix-clickcard-card-flip .yt-uix-card-body-arrow-horizontal, .yt-uix-hovercard-card-flip .yt-uix-card-body-arrow-horizontal
	{
		border-right-color: var(--hover-background) !important;
	}
	.exp-kevlar-settings .account-page .yt-uix-button /*save buttons*/
	{
		background: var(--main-color) !important;
		border-color: var(--main-color) !important;
		color: var(--main-text) !important;
		opacity: .9;
	}
	.exp-kevlar-settings .account-page .yt-uix-button:hover
	{
		opacity: 1 !important;
	}
	/*Social*/
	.social-connector
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	/*TV*/
	.howto-circle
	{
		background-color: var(--hover-background) !important;
		color: var(--main-color) !important;
	}
	.howto-text
	{
		color: var(--dimmer-text) !important;
	}
	.remote-icon
	{
		filter: invert(1) brightness(200%);
	}
	h3.pairing-section-header
	{
		color: var(--main-text)
	}
	.yt-uix-form-input-select, .yt-uix-form-input-text, .yt-uix-form-input-textarea
	{
		border-color: var(--hover-background) !important;
	}
	#account-page-header-avatar.howto-promo-image
	{
		filter: invert(1) grayscale(1);
	}
	/*TV code*/
	.yt-uix-form-input-select, .yt-uix-form-input-text, .yt-uix-form-input-textarea
	{
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	/*Footer*/
	body #footer-container {
		background: var(--hover-background) !important;
		border-color: var(--hover-background) !important;
		color: var(--main-text) !important;
	}
	#footer-main /*divider*/
	{
		border-color: var(--hover-background) !important;
	}
	/*links*/
	#footer-links-primary a
	{
		color: var(--main-text) !important;
	}
	#footer-links-secondary a
	{
		color: var(--dimmer-text) !important;
	}
	#footer-links-primary a:hover, #footer-links-secondary a:hover
	{
		color: var(--main-color) !important;
	}
	/*buttons*/
	#footer .yt-uix-button-group .yt-uix-button,
	#footer .pickers li, #footer .footer-history, #footer #google-help
	{
		background: var(--second-background) !important;
		border-color: var(--second-background) !important;
		color: var(--main-text) !important;
		box-shadow: none !important;
	}
	.yt-uix-button-default.yt-uix-button-toggled:hover
	{
		box-shadow: none !important;
	}
	#footer .yt-uix-button-icon-footer-language, #footer .yt-uix-button-icon-footer-history, #footer .yt-uix-button-icon-questionmark
	{
		filter: invert(1);
	}
	.yt-uix-button-arrow
	{
		border-top-color: var(--main-text) !important;
	}
	#yt-picker-country-footer, #yt-picker-language-footer, #yt-picker-safetymode-footer
	{
		background: var(--second-background) !important;
		border-color: var(--second-background) !important;
		color: var(--main-text) !important;
	}
	.yt-picker-header, #safety-form p.safety-submit /*divider*/
	{
		border-color: var(--hover-background) !important;
	}
	.yt-picker-header h3.yt, .yt-picker-content strong
	{
		color: var(--main-text) !important;
	}
	#yt-picker-country-footer .yt-default .yt-notes, p.yt-notes,
	#safety-mode-description li
	{
		color: var(--dimmer-text) !important;
	}
	#yt-picker-country-footer .yt-picker-content a, .yt-picker-content button
	{
		color: var(--main-color) !important;
	}
	#yt-picker-safetymode-footer button /*save*/
	{
		background: var(--main-color) !important;
		border-color: var(--main-color) !important;
		color: var(--main-text) !important;
		opacity: .9;
	}

	/*Notification buttom corner - for settings, watch later etc*/
	tp-yt-paper-toast
	{
		background: var(--hover-background) !important;
		color: var(--main-text) !important;
		box-shadow: var(--shadow) !important;
	}

	/*Topic auto-generated by youtube*/
	#auto-generated.ytd-interactive-tabbed-header-renderer,
	#metadata.ytd-interactive-tabbed-header-renderer
	{
		color: var(--dimmer-text) !important;
	}

	/*Keyboard shortcuts Shift-/ */
	ytd-hotkey-dialog-renderer[dialog][dialog][dialog]
	{
		background-color: var(--main-background) !important;
	}
	ytd-hotkey-dialog-section-option-renderer
	{
		border-color: var(--hover-background) !important;
	}
}
