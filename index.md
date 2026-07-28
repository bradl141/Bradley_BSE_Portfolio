# Smart Mirror
My project is the Magic Mirror, a program that can display a lot of different widgets on a monitor.
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Bradley Wang | Palo Alto High | Computer Science | Incoming Sophmore

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
# Modification: Making A Case
- Components
  - Printed Case: The case that my monitor slots into, which also holds my Raspberry Pi
  - Reflective Film: Creates the mirror effect on my monitor while allowing light to still show through
- Technical Progress
  - Modeled the case in Onshape
- Challenges
  - Learning Onshape
  - I had to modify my design to be printable
  - Sizing was wrong, so I had to print multiple times
  - The case messed with the film

# Final Milestone: Applying Reflective Film
<iframe width="560" height="315" src="https://www.youtube.com/embed/HZsq55PDu-g?si=y7aQgUZVEVGfIsNo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What I've accomplished:
	- Applied the film to the monitor
  	- Adjusted UI to stand out more against the film
- Biggest challenges and triumphs at BSE:
	- 
- Key Topics I Learned:
	- How to solder
    - How to CAD
    - How to 3d Print
    - Using Github
- What I hope to learn in the future:
	- b
    - b
    -    



# Second Milestone: Updating Ui
<iframe width="560" height="315" src="https://www.youtube.com/embed/EVJP-fTA7WQ?si=BsX_caQ2THmkbwqm" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
- Components
  - Printed Case: The case that my monitor slots into, which also holds my Raspberry Pi
  - Reflective Film: Creates the mirror effect on my monitor while allowing light to still show through
- Technical Progress
  - Modeled the case in Onshape
- Challenges
  - Learning Onshape
  - I had to modify my design to be printable
  - Applying the film correctly
- Future Plans
  - Add more modules
  - Make it a mirror
  - Make a cased

# First Milestone: Setting up the Mirror
<iframe width="560" height="315" src="https://www.youtube.com/embed/Fc8ASIRg2Ys?si=wR9Xdvz4Gwit2ehI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
- Components
  - Monitor: The display for the Magic Mirror
  - Raspberry Pi: A mini computer that acts as the system the Magic Mirror runs on
- Technical Progress
  - Set up the Raspberry Pi
  - Installed Magic Mirror
- Challenges
  - I had to learn how Linux worked
  - I ran into some Linux bugs
- Future Plans
  - Add more modules
  - Make it a mirror
  - Make a case

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```JavaScript
- This is my file that sets all the modules, the apps on my Magic Mirror
- This allows me to configure different settings for each of them.
let config = {
	address: "localhost",	// Address to listen on
	port: 8080,
	basePath: "/",	// The URL path where MagicMirror² is hosted.
	ipWhitelist: ["127.0.0.1", "::ffff:127.0.0.1", "::1"],	// Set [] to allow all IP addresses

	useHttps: false,			// Support HTTPS or not, default "false" will use HTTP
	httpsPrivateKey: "",	// HTTPS private key path, only require when useHttps is true
	httpsCertificate: "",	// HTTPS Certificate path, only require when useHttps is true

	language: "en",
	locale: "en-US",   

	logLevel: ["INFO", "LOG", "WARN", "ERROR"], // Add "DEBUG" for even more logging
	timeFormat: 12,
	units: "metric",

	modules: [
		{
			module: "alert",
		},
		{
			module: "updatenotification",
			position: "top_bar"
		},
		{
			module: "clock",
			position: "top_right"
		},
		{
			module: "calendar",
			header: "US Holidays",
			position: "top_left",
			config: {
				calendars: [
					{
						fetchInterval: 7 * 24 * 60 * 60 * 1000,
						symbol: "calendar-check",
						url: "https://ics.calendarlabs.com/76/mm3137/US_Holidays.ics"
					}
				]
			}
		},
		{
			//module: "compliments",
			//position: "lower_third"
		//},
		{
			module: "weather",
			position: "top_left",
			config: {
				weatherProvider: "openmeteo",
				type: "current",
				lat: 37.407378,
				lon: -122.088866
			}
		},
		{
			module: "weather",
			position: "top_left",
			header: "Weather Forecast",
			config: {
				weatherProvider: "openmeteo",
				type: "forecast",
				lat: 37.407378,
				lon: -122.088866
			}
		},
		{
			module: "MMM-MyTeams-LeagueTable",
			position: "bottom_right",
			header: "League Standings", 
			config: {
				updateInterval: 30 * 60 * 1000, 
				retryDelay: 15000, 
				maxRetries: 3, 
				animationSpeed: 2000, 
				fadeSpeed: 4000, 
				colored: true, 

				selectedLeagues: [
					"WORLD_CUP_2026" 
				],

				autoGenerateButtons: true, 
				showLeagueButtons: true, 
				autoFocusRelevantSubTab: true, 

				showWC2026: true, 
				onlyShowWorldCup2026: true, 
				showWC2026Groups: ["A","B","C","D","E","F","G","H","I","J","K","L"], 
				showWC2026Knockouts: ["Rd32", "Rd16", "QF", "SF", "TP", "Final"], 
				defaultWCSubTab: "C", 
				displayAllTabs: true, 
				useMockData: false, 

				showPosition: true, 
				showTeamLogos: true, 
				showPlayedGames: true, 
				showWon: true, 
				showDrawn: true, 
				showLost: true, 
				showGoalsFor: true, 
				showGoalsAgainst: true, 
				showGoalDifference: true, 
				showPoints: true, 
				showForm: true, 
				formMaxGames: 6, 
				enhancedIndicatorShapes: true, 
				firstPlaceColor: "rgb(142, 142, 142)", 
				highlightedColor: "rgba(255, 255, 255, 0.1)", 
				
				tableDensity: "normal", 
				fixtureDateFilter: null, 
				enableVirtualScrolling: true, 
				virtualScrollThreshold: 10, 

				autoCycle: true, 
				cycleInterval: 15 * 1000, 
				wcSubtabCycleInterval: 20 * 1000, 
				autoCycleWcSubtabs: true, 

				darkMode: true, 
				fontColorOverride: "#FFFFFF", 
				opacityOverride: null, 
				
				
				clearCacheButton: true,     
				clearCacheOnStart: false, 
				maxTableHeight: 520 
			}
		},
		{
			module: "newsfeed",
			position: "bottom_left",
			config: {
				feeds: [
					{
						title: "New York Times",
						url: "https://rss.nytimes.com/services/xml/rss/nyt/HomePage.xml"
					}
				],
				showSourceTitle: true,
				showPublishDate: true,
				broadcastNewsFeeds: true,
				broadcastNewsUpdates: true
			}
		}
	]
};
if (typeof module !== "undefined") { module.exports = config; }
```

# Bill of Materials

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| WGK Portable Monitor | Display for the mirror | $39.99 | <a href="https://www.amazon.com/WGK-Portable-Monitor-15-6-inch-Kickstand/dp/B0DCYBR34X?th=1"> Link </a> |
| CanaKit Raspberry Pi 4 Starter Kit | What the mirror runs on | $169.95 | <a href="https://www.canakit.com/raspberry-pi-4-starter-kit.html?srsltid=AfmBOoqQb4gPflC-FdNE6q8kvRr3PZ0iNNf-mfZ3B4ASjp9StDkw8tvG"> Link </a> |
| One Way Privacy Film | Reflective Film | $5.99 | <a href="https://www.amazon.com/dp/B0998PYXSH?ref_=ppx_hzsearch_conn_dt_b_fed_asin_title_1&th=1"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1: MagicMirror Guide]([https://learn.sparkfun.com/tutorials/how-to-make-a-magic-mirror-with-raspberry-pi/all])
- [Example 2: MagicMirror Example]([https://noahnewman44.github.io/BSE_Template_Portfolio/])
