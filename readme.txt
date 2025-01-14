=== Block Catalog ===
Contributors:      10up, dsawardekar, dkotter, jeffpaul
Tags:              gutenberg, developer, blocks, custom blocks
Tested up to:      6.6
Stable tag:        1.6.1
License:           GPL-2.0-or-later
License URI:       https://spdx.org/licenses/GPL-2.0-or-later.html

Easily keep track of which Gutenberg Blocks are used across your site.

== Description ==

* Find which blocks are used across your site.
* Fully Integrated with the WordPress Admin.
* Use filters to see Posts that use a specific block.
* Find Posts that use Reusable Blocks.
* Use the WP CLI to quickly find blocks from the command line.
* Use custom WordPress filters to extend the Block Catalog.

[Fork on GitHub](https://github.com/10up/block-catalog)

== Screenshots ==

1. The Block Catalog indexing page. You need to index your content first.
2. The Blocks found by the plugin on your site.
3. The Blocks for each post can be seen on the post listing page.
4. You can filter the post listing to a specific Block using this dropdown.

== Getting Started ==

1. On activation, the plugin will prompt you to index your content. You need to do this first before you will be able to see the various blocks used on your site. You can also go to *WP-Admin > Tools > Block Catalog* to do this yourself. Alternately, you can run the WP CLI command `wp block-catalog index` to index your content from the command line.

2. Once indexed, you will be able to see the different blocks used on your site in the Block Catalog Taxonomy.

3. Navigating to any Block Editor post type will also show you the list of blocks present in a post.

4. You can also filter the listing to only show Posts that have a specific block.

== Frequently Asked Questions ==

= 1) Why does the Plugin require indexing? =

Block Catalog uses a taxonomy to store the data about blocks used across a site. The plugin can build this index via the Tools > Block Catalog screen or via the WP CLI `wp block-catalog index`. After the initial index, the data is automatically kept in sync after any content updates.

= 2) Why does the name displayed in the plugin use the blockName attribute instead of the title? =

If your blocks are registered on the Backend with the old [register_block_type](https://developer.wordpress.org/reference/functions/register_block_type/) API, you may be missing the `title` attribute. The newer [register_block_type_from_metadata](https://developer.wordpress.org/reference/functions/register_block_type_from_metadata/) uses the same `block.json` on the FE and BE which includes the Block title.

When the plugin detects such a missing `title`, it uses the `blockName` suffix instead. eg:- xyz/custom-block will display as Custom Block.

To address this you need to update your custom block registration. If this is outside your control, you can also use the `block_catalog_block_title` filter hook to [override the title as seen here](https://gist.github.com/dsawardekar/676d0d4c5d7f688351e199fdc54484d6).

== Changelog ==

= 1.6.1 - 2024-07-09 =
* **Changed:** Update [Support Level](https://github.com/10up/block-catalog/blob/develop/README.md#support-level) from `Beta` to `Stable` (props [@jeffpaul](https://github.com/jeffpaul), [@dkotter](https://github.com/dkotter) via [#56](https://github.com/10up/block-catalog/pull/56)).
* **Changed:** Bump WordPress "tested up to" version 6.6 (props [@sudip-md](https://github.com/sudip-md), [@jeffpaul](https://github.com/jeffpaul) via [#60](https://github.com/10up/block-catalog/pull/60)).
* **Changed:** Bump WordPress minimum supported version to 6.4 (props [@sudip-md](https://github.com/sudip-md), [@jeffpaul](https://github.com/jeffpaul) via [#60](https://github.com/10up/block-catalog/pull/60)).
* **Security:** Bump `braces` from 3.0.2 to 3.0.3 (props [@dependabot](https://github.com/apps/dependabot), [@faisal-alvi](https://github.com/faisal-alvi) via [#58](https://github.com/10up/block-catalog/pull/58)).
* **Security:** Bump `ws` from 7.5.9 to 7.5.10 (props [@dependabot](https://github.com/apps/dependabot), [@faisal-alvi](https://github.com/faisal-alvi) via [#58](https://github.com/10up/block-catalog/pull/58)).

= 1.6.0 - 2024-05-13 =
* **Added:** WP-CLI command, `export`, to generate a CSV of the block catalog (props [@dsawardekar](https://github.com/dsawardekar), [@psorensen](https://github.com/psorensen), [@Sidsector9](https://github.com/Sidsector9) via [#52](https://github.com/10up/block-catalog/pull/52)).
* **Added:** Classic Editor block detection (props [@dsawardekar](https://github.com/dsawardekar), [@Sidsector9](https://github.com/Sidsector9) via [#53](https://github.com/10up/block-catalog/pull/53)).
* **Changed:** Bump WordPress "tested up to" version 6.5 (props [@sudip-md](https://github.com/sudip-md), [@jeffpaul](https://github.com/jeffpaul) via [#51](https://github.com/10up/block-catalog/pull/51)).
* **Changed:** Bump WordPress minimum from 5.7 to 6.3 (props [@sudip-md](https://github.com/sudip-md), [@jeffpaul](https://github.com/jeffpaul) via [#51](https://github.com/10up/block-catalog/pull/51)).
* **Changed:** Replaced [lee-dohm/no-response](https://github.com/lee-dohm/no-response) with [actions/stale](https://github.com/actions/stale) to help with closing no-response/stale issues (props [@jeffpaul](https://github.com/jeffpaul) via [#48](https://github.com/10up/block-catalog/pull/48)).
* **Security:** Bump `express` from 4.18.2 to 4.19.2 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#50](https://github.com/10up/block-catalog/pull/50)).
* **Security:** Bump `follow-redirects` from 1.15.5 to 1.15.6 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#50](https://github.com/10up/block-catalog/pull/50)).
* **Security:** Bump `postcss` from 7.0.39 to 8.4.33 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#50](https://github.com/10up/block-catalog/pull/50)).
* **Security:** Bump `10up-toolkit` from 5.2.3 to 6.0.1 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#50](https://github.com/10up/block-catalog/pull/50)).
* **Security:** Bump `webpack-dev-middleware` from 5.3.3 to 5.3.4 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#50](https://github.com/10up/block-catalog/pull/50)).

= 1.5.4 - 2024-02-29 =
* **Added:** Support for the WordPress.org plugin preview (props [@dkotter](https://github.com/dkotter), [@jeffpaul](https://github.com/jeffpaul) via [#38](https://github.com/10up/block-catalog/pull/38)).
* **Changed:** Significantly improved performance of block catalog reset on larger WordPress installations (props [@dsawardekar](https://github.com/dsawardekar), [@Sidsector9](https://github.com/Sidsector9) via [#41](https://github.com/10up/block-catalog/pull/41)).
* **Changed:** Clean up NPM dependencies and update the minimum node version to 20 (props [@Sidsector9](https://github.com/Sidsector9), [@dsawardekar](https://github.com/dsawardekar) via [#43](https://github.com/10up/block-catalog/pull/43)).
* **Security:** Bump `tj-actions/changed-files` from 39 to 41 (props [@dependabot](https://github.com/apps/dependabot), [@peterwilsoncc](https://github.com/peterwilsoncc) via [#39](https://github.com/10up/block-catalog/pull/39)).
* **Security:** Bump `follow-redirects` from 1.15.2 to 1.15.4 (props [@dependabot](https://github.com/apps/dependabot), [@Sidsector9](https://github.com/Sidsector9) via [#40](https://github.com/10up/block-catalog/pull/40)).

= 1.5.3 - 2023-11-23 =
* **Fixed:** PHP 8.2 deprecation warnings (props [@dsawardekar](https://github.com/dsawardekar), [@ravinderk](https://github.com/ravinderk) via [#34](https://github.com/10up/block-catalog/pull/34)).
* **Added:** PHPUnit 9.x support (props [@dsawardekar](https://github.com/dsawardekar), [@ravinderk](https://github.com/ravinderk) via [#34](https://github.com/10up/block-catalog/pull/34)).
* **Security:** Bump `sharp` from 0.32.3 to 0.32.6 (props [@dependabot](https://github.com/apps/dependabot), [@faisal-alvi](https://github.com/faisal-alvi) via [#32](https://github.com/10up/block-catalog/pull/32)).

= 1.5.2 - 2023-11-16 =
* **Changed:** Bump WordPress "tested up to" version to 6.4 (props [@qasumitbagthariya](https://github.com/qasumitbagthariya), [@jeffpaul](https://github.com/jeffpaul) via [#28](https://github.com/10up/block-catalog/pull/28), [#29](https://github.com/10up/block-catalog/pull/29)).

= 1.5.1 - 2023-10-24 =
**Note that this release changes the name of the base plugin file. As such, you'll probably need to reactivate the plugin after updating.**

* **Added:** Add our standard GitHub Action automations (props [@jeffpaul](https://github.com/jeffpaul), [@dsawardekar](https://github.com/dsawardekar), [@dkotter](https://github.com/dkotter) via [#10](https://github.com/10up/block-catalog/pull/10), [#20](https://github.com/10up/block-catalog/pull/20), [#22](https://github.com/10up/block-catalog/pull/22), [#23](https://github.com/10up/block-catalog/pull/23), [#24](https://github.com/10up/block-catalog/pull/24), [#25](https://github.com/10up/block-catalog/pull/25)).
* **Changed:** Update our plugin image assets (props [Brooke Campbell](https://www.linkedin.com/in/brookecampbelldesign/), [@jeffpaul](https://github.com/jeffpaul), [@dsawardekar](https://github.com/dsawardekar), [@faisal-alvi](https://github.com/faisal-alvi) via [#11](https://github.com/10up/block-catalog/pull/11), [#17](https://github.com/10up/block-catalog/pull/17)).
* **Changed:** Updated the main plugin file name (props [@dkotter](https://github.com/dkotter), [@peterwilsoncc](https://github.com/peterwilsoncc), [@dsawardekar](https://github.com/dsawardekar) via [#18](https://github.com/10up/block-catalog/pull/18)).
* **Security:** Bump `@babel/traverse` from 7.22.8 to 7.23.2 (props [@dependabot](https://github.com/apps/dependabot), [@dkotter](https://github.com/dkotter) via [#21](https://github.com/10up/block-catalog/pull/21)).

= 1.5.0 - 2023-08-11 =
* **Added:** `Beta` Support Level (props [@jeffpaul](https://github.com/jeffpaul), [@dsawardekar](https://github.com/dsawardekar) via [#3](https://github.com/10up/block-catalog/pull/3)).
* **Added:** Adds support for multisite via WP CLI (props [@dsawardekar](https://github.com/dsawardekar), [@Sidsector9](https://github.com/Sidsector9) via [#9](https://github.com/10up/block-catalog/pull/9)).
* **Fixed:** Missing name in the `block_catalog_taxonomy_options` hook (props [@dsawardekar](https://github.com/dsawardekar), [@fabiankaegy](https://github.com/fabiankaegy) via [#6](https://github.com/10up/block-catalog/pull/6)).

[View historical changelog details here](https://github.com/10up/block-catalog/blob/develop/CHANGELOG.md).

== Upgrade Notice ==

= 1.6.1 =
Updates the [Support Level](https://github.com/10up/block-catalog/blob/develop/README.md#support-level) from `Beta` to `Stable`.

= 1.5.1 =
* Note that this release changes the name of the base plugin file. As such, you'll probably need to reactivate the plugin after updating

