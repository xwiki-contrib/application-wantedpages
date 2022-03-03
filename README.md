# About

This is an extension for [XWiki](https://www.xwiki.org), inspired by MediaWiki's [Special:WantedPages](https://www.mediawiki.org/wiki/Special:WantedPages). It contains a small application that includes a page with a dynamic list of non-URL links on your wiki that point to nonexistent documents.

The list includes three main components:
  - The name (\<spaces\>.\<displayTitle\>) of the nonexistent page to which link(s) exist. You can click on the name to be taken to the "create" screen for that page.
  - The number of documents that contain a live link to that nonexistent page. (Note that this counts *documents*, not links.) You can click on the count to reveal...
  - An alphabetical sublist of those document(s)' fullnames. Each list item is a live link to the named page.

The list is sorted in descending order based on the number of linking documents, then in ascending alphabetical order. It also respects the "displayHiddenDocuments" user preference, so if that is set to `false`, the list will not include or count documents marked as hidden.
  
As the extension installs an application, it is configured to show up in your Applications panel.
  
# Localization/Translation

While it is in US English by default, the extension is fully(?) configured for localization. The default translation strings are located in WantedPages.WantedPagesTranslations.
  
Wanted Pages is not currently an XWiki Contrib project and, as such, is not yet on XWiki's Weblate instance. Hopefully, this will change in the coming weeks!

# Current Limitations

- The list is currently just that: a list. You cannot, for instance, modify the sort method without modifying the `order by` clause in WantedPagesCode---in other words, without modifying the code itself.
  - I or another contributor(s) may eventually convert the list to a Livetable object, if this would be feasible.
- It is not necessarily optimized for very large wikis. The data is processed synchronously and is not cached.
- **At the present, I cannot guarantee that it will function as intended on a wiki farm setup.** The database queries that fetch the relevant data do not currently discern among sub-wikis, so if you install this extension on any wiki other than the main one, you may find that the list includes links and documents from other wikis on your farm.
  - This would probably be a relatively simple fix to implement, though my test environment only has one wiki, so others might need to test the eventual fix.
- As mentioned above, the extension is not yet on the Extension Manager, so you will have to import the XAR manually in order to "install."

# Authors

[Eden Biskin](https://github.com/SightSpirit/), yours truly, is the only author at present.

I must also, of course, acknowledge the hard work of the XWiki community for building such a powerful information platform.
  
# License
  
[GPLv3](https://www.gnu.org/licenses/gpl-3.0.html), baby.
