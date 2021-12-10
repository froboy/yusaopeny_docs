Open Y leverages [Apache Solr](https://solr.apache.org/) for a few features:

- [Activity Finder](https://github.com/ymcatwincities/openy_activity_finder/wiki) requires Solr
- Site search can _optionally_ use Solr as per [this Pull Request](https://github.com/ymcatwincities/openy/pull/1967)

## Quick Start / Upgrade path

- Log in as admin.
- Go to `admin/modules` and enable the Open Y Search API module.

![image](https://user-images.githubusercontent.com/563412/142628630-b412aa4b-8f2b-42f6-ba06-c5bb6a78469c.png)

- Approve the next step for enabling Database Search.

![image](https://user-images.githubusercontent.com/563412/142628735-6aa409bd-5ff5-4305-a0f0-7f6bc96d0740.png)

- Go to the Search API configuration page `admin/config/search/search-api`.
- Verify that the "OpenY Database Search" server is enabled.
- Visit "Search content" index.

![image](https://user-images.githubusercontent.com/563412/142629065-e13c8bb4-cad8-436f-93c6-30fa6ac6fdf7.png)

tip: Admins can enable and the Solr search and switch the index between servers.

- Index content by clicking "Index now".

![image](https://user-images.githubusercontent.com/563412/142629227-8607eeca-4022-47c4-b5fd-6e38ccfb7bab.png)

- Go to the homepage and search for any keyword.

![image](https://user-images.githubusercontent.com/563412/142629467-e275b536-2505-4ddf-8d78-7c6f4ae0e716.png)

- Verify search results are displayed correctly.

## Starting from the Open Y installer

- Find the `Select search service` step displayed during the Open Y installation.
- Choose from one of these options during installation:
  - **None**
    - Nothing happens if the user chooses this option, search modules are displayed after installation.
  - **Open Y Google Custom Search**
    - Google Custom Search configuration form is displayed if the user chooses this option.
    - The Open Y Google Search module is enabled after installation and ready to use.
  - **Open Y Search API**
    - Search API backend options are displayed in this case with the following options:
      - _Database_
        - The Open Y Search API module is enabled after installation. The database search API server is enabled. The search is ready to use after content indexation.
      - _Solr_
        - Additional installation step with Solr configuration form is displayed in this case and user can specify all params for Solr connection. The Open Y Search API module is enabled after installation, Solr search API server is enabled. The search is ready to use after content indexing (if the correct Solr settings were used).

## Switch from database search backend to Solr backend

Watch a [video tutorial](https://youtu.be/-Sq3uZb5K_U) on how to switch an existing site from the database backend to a Solr server. This requires a Solr server to be configured in your environment.

- Edit the "Solr search" server from the Search API configuration `admin/config/search/search-api`.
- Add the configuration information for your Solr server. Refer to Drupal's [Search API Solr project](https://www.drupal.org/project/search_api_solr) for troubleshooting connection information.
- Save the server and observe that Search API has successfully connected to your server.
- Edit the "Search content" index and change the "Server" field to the newly configured "Solr Search" index.
- Visit the "Search content" index and click "Index now" to re-index the content.
