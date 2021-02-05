See how solr server configuration should be done on a server
https://github.com/ymcatwincities/openy_activity_finder/wiki


**Upgrade path:**

- login as admin
- Go to `admin/modules` and enable the Open Y search API module.
- Go to Search API configuration page `admin/config/search/search-api`
- Verify the Database search is enabled by default. But admin can enable and the Solr search and switch the index between servers.
- Index content
-  Go to the homepage and run a search by any keyword
- Verify search results are displayed correctly in all Open Y themes.

**Open Y installation:**

* Make sure the `Select search service` step is displayed during Open Y installation.
* Verify user can choose different search options during installation:
* **None**
  * Nothing happens if user chooses this option, search modules are displayed after installation.
* **Open Y Google Custom Search**
  * Google Custom Search configuration form is displayed if the user chooses this option.
  * The Open Y Google Search module is enabled after installation and ready to use.
* **Open Y Search API**
  * Search API backend options are displayed in this case with the following options:
    * _Database_
      * The Open Y Search API module is enabled after installation. The database search API server is enabled. The search is ready to use after content indexation.
    * _Solr_
      * Additional installation step with Solr configuration form is displayed in this case and user can specify all params for Solr connection. The Open Y Search API module is enabled after installation, Solr search API server is enabled. The search is ready to use after content indexation (if correct Solr settings were used).
