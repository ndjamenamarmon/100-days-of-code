# 100 Days Of Code - Log

### Day 1: November 2, Friday

**Today's Progress**: I set up the git repository and boilerplate code for my React project, ChaiCMS. I upgraded the packages in package.json that were outdated from the Udemy React course. This caused issues with webpack that I went through and fixed.

**Thoughts:** I thought diving by myself into webpack once everything broke after the upgrades was going to be really scary since I am new to webpack config, but it wasn't too bad. Some googling and documentation reading got me going in the right direction. It was great seeing the dev server fire up successfully after getting everything set up.

**Link(s) to work:** [ChaiCMS](https://github.com/ndjamenamarmon/chaicms)


### Day 2: November 3, Saturday

**Today's Progress**: I created the Sidebar component for ChaiCMS, hard-coding the links for the moment to point to the dashboard page. I added initial styles for the layout. I then created the Settings page and settings form, adding functionality to edit and display the site title and site description, integrating with the Firebaase database.

**Thoughts:** I feel like I made fast progress building out the components I worked on today, helped by the boilerplate project from the React Udemy course I just completed. So far, I am feeling pretty comfortable modifying the boilerplate code to build what I need. Tomorrow I plan on creating the tests for the Sidebar and Settings components, actions, and reducers.

**Link(s) to work:** [PR #2](https://github.com/ndjamenamarmon/chaicms/pull/2)


### Day 3: November 4, Sunday

**Today's Progress**: I built out Content Types, Fields, and the start of Entries for ChaiCMS, including updating the Sidebar to populate content types dynamically. I built a basic integration of fields with content types.

Just before bed, I looked into the new React Hooks API and switched two class components (the SettingsForm and ContentTypeForm) over to functional components using Hooks. I for the second form, I created a custom hook, useSlugify.

**Thoughts:** I know I was planning on building out all the tests for the Sidebar and Settings components, actions, and reducers today, but I found myself much more interested in building rather than testing. I will need to build out the tests at some point, but it is interesting observing myself and my tendencies. I love working with the more visual aspects of coding and being able to see what I am creating. Tests seem more like a "have to do" task rather than a "want to do."

So far, I'm liking Hooks. They seem cleaner and more straightforward than the Class component method of handling state. Moving away from using this for state and props is nice, as is being able to use custom hooks that can be re-used in different components.

**Link(s) to work:**
- [Added basic Content Types functionality](https://github.com/ndjamenamarmon/chaicms/commit/afc570f367e1186f85ef2ad17962f1b7bc0e1d08)
- [Moved Content Types to folder](https://github.com/ndjamenamarmon/chaicms/commit/eb54e61b0d6763541e7591cdfba597b4ed27400f)
- [Added Fields functionality and basic integration with content types](https://github.com/ndjamenamarmon/chaicms/commit/0026a96b160c260af939abd2eb7ad4d6da7be4d5)
- [Added files for Entries](https://github.com/ndjamenamarmon/chaicms/commit/5633a4af3a19e8aed90f298be238cded9886aeda)
- [Changed SettingsForm to function component with hooks](https://github.com/ndjamenamarmon/chaicms/commit/b9e8a71dfdea13cc68c4baf2f6876c13428c3fb0)
- [Changed ContentTypeForm to functional component with Hooks, created custom useSlugify hook](https://github.com/ndjamenamarmon/chaicms/commit/7c1fa8d44f2f045bb60d86ab551898b0b346c30b)


### Day 4: November 5, Monday

**Today's Progress**: Today I continued building out the Entries functionality for ChaiCMS, focusing on the EntryForm. I changed the EntryForm component from a class component to a function component, and implemented Hooks to handle state.

**Thoughts:** Working with the Entries functionality is an interesting challenge since they are meant to have dynamic fields. Unlike Content Types or Fields, I don't know what the fields are going to be, so I have to build with that in mind. Up to now I have been outputting form fields and object properties that I know the object must have, but with Entries the object properties could be anything. 

I am loving working with Hooks. Changing from the Class component to the Function component was a relief and I had to think about this.props.whatever and this.state.whatever less, and just code!

**Link(s) to work:** [Changed EntryForm to functional components with Hooks, started building it out; fixed some bugs](https://github.com/ndjamenamarmon/chaicms/commit/31431f057ce08c42fb43162dd6787e7002d4d5f1)


### Day 5: November 6, Tuesday

**Today's Progress**: Today I continued building out the Entries functionality for ChaiCMS, working on handling the EntryForm submission of data to the database. I also worked on implementing the list of entries per content type. 

**Thoughts:** Submitting entry data was an interesting little challenge since the fields and consequently key-value pairs in each entry object could vary and would need to be dynamic depending on the fields available for the content type. I had an issue where React didn't like me updating the entry state whose initial value was an empty object ```{}``` but when edited had key value pairs. It was expecting the empty state to already have those keys with some default data: ```{ key: "" }```.

I tried using a useEffect() hook to populate the state immediately after render and before the text input was used by the user, but that didn't work either. I then passed the calculated state (with all keys that would be used based on the fields available in the content type) from the parent component as a prop and passed that into useState() as the default state, and that worked well. 

**Link(s) to work:**
- [Add entry functionality and saving to db](https://github.com/ndjamenamarmon/chaicms/commit/9c4aeb817895bafdb4469fda8a33390d218885aa)
- [Wired up Entries List on Entries page](https://github.com/ndjamenamarmon/chaicms/commit/0178c875dfc7d155b21ff20e158af9cecd4684f4)


### Day 6: November 7, Wednesday

**Today's Progress**: Today I worked on the Edit Entry functionality for ChaiCMS. I then changed the route where the edit entry page would live to ```/entry/:slug/edit/:id``` and fixed the affected components. Finally, I wiped the database to start from a clean slate for further building, and fixed some issues that came from the empty database. 

**Thoughts:** Today's work was pretty straightforward. I learned more about passing multiple objects as props using the spread operator. I also had to figure out how to debug an issue with an action where it appeared that the updates being passed to it weren't getting through. It ended up being fairly simple once I figured it out.

**Link(s) to work:**
- [Added edit entry functionality](https://github.com/ndjamenamarmon/chaicms/commit/0f3abd7390a8185f244d68fa98d505b9a0e6a7d3)
- [Reconfigured the edit entries page to live at /entry/:slug/edit/:id to match with other pages, fixed sidebar to show current content type](https://github.com/ndjamenamarmon/chaicms/commit/abd42977d60627b9b0a1103d7128768bb5c42473)
- [Fixed issues caused when database was wiped](https://github.com/ndjamenamarmon/chaicms/commit/a70e624ee04d4332307f48e191b0450899fa895c)


### Day 7: November 8, Thursday

**Today's Progress**: Today I worked on the add page for content types to redirect to the edit page after a new content type is created. I also added the createdAt and lastUpdated properties to content type database entries. Finally, I changed content types and fields to use apiKey instead of slug in camelCase instead of slug-format.

**Thoughts:** I wanted the add content type page to redirect to the content type's edit page after it was edited so the user could continue to work on it if they chose instead of redirecting to the list of content types. I ran into an issue where dispatching the startAddContentType action did not return any of the data that firebase return with the generated ID that I would need to redirect to the edit page for that content type. I tried adding a promise ```.then(()=>{})``` to the action, but that didn't work. After a bit of Googling, it seemed that action dispatches were supposed to be "fire and forget," and not return something back after the action was fired.

So then I added createdAt to the content type properties and updated the selector to accept sorts by createdAt. In this way I was able to sort the content types in the state (that was updated in the action) by createdAt and grab the ID of the newest one and use that for the redirect to the edit page. I still did need to add the promise to the action dispatch on the add page so I got the latest state after it resolved.

**Link(s) to work:**
- [Added createdAt and lastUpdated to content types, modified content type selector to include different sorts, redirect to content type edit page after add](https://github.com/ndjamenamarmon/chaicms/commit/977a1206a0d45e83a7a61ea1756f2d604c0992dd)
- [Changed slug field to API Key in content types and fields with camelCase format](https://github.com/ndjamenamarmon/chaicms/commit/9af9905bb797e36b8a13e6b2df1cc76e1f91a05a)


### Day 8: November 9, Friday

**Today's Progress**: Today for ChaiCMS I moved the styles into a theme folder and added the option to use a node environment variable to change the theme. I also added createdAt and lastUpdated properties to fields. Finally I continued to build out the field add/edit form to include help text, is required checkbox, and is unique checkbox along with some aesthetic/accessibility changes with labels and required field notes.

**Thoughts:** Trying to figure out how to make webpack compile a theme dynamically from a variable in a path was a difficult challege. I tried to use template strings in an import statement, but that didn't work. Eventually I settled on a require using a node environment variable. However, I wanted to be able to import/require the styles after getting the theme variable from the firebase database, but couldn't figure out how to do that.

The other updates I did today were straightforward and fun to do. It's nice to see what I have planned for this project slowly come to life on the screen.

**Link(s) to work:**
- [Moved styles into default theme, added theme environment variable](https://github.com/ndjamenamarmon/chaicms/commit/60985bd553bd363d7326616703014e4ee4ab86fa)
- [Add createdAt and lastUpdated to fields, move createdAt and lastUpdated calculations to onSubmit for freshest time](https://github.com/ndjamenamarmon/chaicms/commit/50277bd7139d48c1402e464e77269f9cb109486b)
- [Added helpText, isRequired, and isUnique properties to fields, added labels and required text in field form](https://github.com/ndjamenamarmon/chaicms/commit/0395eb1a884c72f63387e9d51fcc194e7762e54d)


### Day 9: November 10, Saturday

**Today's Progress**: Today for ChaiCMS I updated the display, styling, and sorting (to alphabetical) for the field list. I also updated the content type form to include a modal for selecting fields to add to the content type, and added the title field property to designate which field should act as the title of the entry. Finally, I fixed bugs in the Entry pages caused by the earlier change in content types and forms to go from using a slug to an apiKey.

**Thoughts:** Today's updates were pretty straightforward. I was feeling tired after the week so was glad to have some easy pickings with this side project to still get some practice in but not tackle anything too challenging.

I worked with the react-modal plugin to implement the modal for selecting the fields. I'm not sure that I will be keeping this implementation. If I do I will definitely want to change the UI and spruce it up a bit, I'm not crazy about how it's looking right now.

**Link(s) to work:**
- [Updated field list: display and styling, alphabetical sort](https://github.com/ndjamenamarmon/chaicms/commit/3e58da76eeed8f400382026bb0e206231e49254a)
- [Added field selection modal and title field property to content type form](https://github.com/ndjamenamarmon/chaicms/commit/9bd4796d57ad136c606a306c4b598106ccc7dd7b)
- [Fixed bugs in entries pages caused by recent changes slug -> apiKey in content types and fields](https://github.com/ndjamenamarmon/chaicms/commit/f983655c0a0f96fccbb04c189240577a9fbab140)


### Day 10: November 11, Sunday

**Today's Progress**: Today for ChaiCMS I implemented a Markdown WYSIWYG editor for markdown entry fields using the react-draft-wysiwyg plugin built on DraftJS.

**Thoughts:** I was feeling a bit burned out by coding this weekend, so I wanted to just get my hour done and be done for the day. Getting the markdown editor working with my entry form was a bit of a challenge though, so I ended up getting a bit sucked into it. First I had an issue importing the package, getting an error that the draft-js node module did not exist. I was about to put in an issue ticket when I noticed others had had the same issue, and that the fix was to install the draft-js peer dependency. The react-draft-wysiwyg could have made that clearer in the installation instructions!

After that I tried adding the editor to my entry form component but ran into issues because it didn't allow the props I needed to let my on change handler know which field was tied to which editor and which part of the state. I finally moved it into its own component with its own state, letting its own on change handlers send the data back to my parent component to deal with the entry state.

I also needed to install a couple of other plugins to convert markdown stored in the database to a draft-js object for the editor to handle, and to convert that object back into markdown for saving into the database. This whole process took a lot of time and Googling and Stackoverflow ... it could definitely have been better documented. I'm thinking I should write a blog post about it.

**Link(s) to work:**
- [Added markdown wysiwyg editor for markdown entry fields](https://github.com/ndjamenamarmon/chaicms/commit/023ae6f2350c091defa07e93b4280139ac532caf)


### Day 11: November 12, Monday

**Today's Progress**: Today for ChaiCMS I added functionality for slug field types in the entry form that would be populated by "slugifying" the title field of the entry. I also added Required notes and help text to the entry form. Finally, I added the Date only field type, using react-dates to display a datepicker.

**Thoughts:** Today's updates were pretty straightforward, and I'm happy with the progress I am making on the entry form. I'm feeling pretty comfortable working with React in this project by now.

Like the markdown editor I had issues getting the datepicker to work until I moved it into its own component with its own state. I still need to build out the Date and Time fields, as I only have Date for now.

**Link(s) to work:**
- [Added slug field functionality](https://github.com/ndjamenamarmon/chaicms/commit/ce780c08904c46cf23dcf5ae221a36dfcbf45941)
- [Added Required and Help Text to Entry Form](https://github.com/ndjamenamarmon/chaicms/commit/7cb0a36d273e9de57194889d6df3a715f6e1c7ff)
- [Added Date only field display to entries/fields with react-dates Datepicker](https://github.com/ndjamenamarmon/chaicms/commit/1ad956677966a1c7cda47a4c68ac14b42bda6061)


### Day 12: November 13, Tuesday

**Today's Progress**: Today for ChaiCMS I tried adding an image in the markdown editor, and though it worked well initially and saved the image markdown to the database, on re-load it would not display it. I looked into the plugin I am using to convert the markdown to the draft js format, and did a lot of Googling, but didn't have any luck figuring it out today. After about 20-30 minutes I stopped to work on something else as I wanted to get some updates committed.

I worked on enforcing the uniqueness of api keys for content types and fields, and making api keys readonly after creation.

**Thoughts:** It was a bit frustrating not having the time to figure out what was going on with the markdown editor (and why isn't instructions for how to get it to work right documented anywhere?!).

Enforcing the uniqueness of api keys is currently based on the state at the time the add/edit form is visited. I'm thinking it should be changed to pulling from the database, at least when validating during submission (so as not to slow down the user experience). 

**Link(s) to work:**
- [Enforce uniqueness of content type api keys](https://github.com/ndjamenamarmon/chaicms/commit/9202c418211e9eb3ced7018ff0edd84667973d02)
- [Enforce uniqueness of field api keys, make api keys of content types and fields readonly when editing](https://github.com/ndjamenamarmon/chaicms/commit/cdd344af86ddaa1cb53308335492c524f79551e7)
