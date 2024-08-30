# Create Content Model

_Define custom post types & fields in the Block Editor._

WordPress.com’s experimental Create Content Model plugin transforms the way custom post types and custom fields are created and managed in WordPress by making use of the latest core features to bring content modeling into the Block Editor.  ​​Additionally, the created data model and data entry UI can be exported as a standalone, maintenance-free plugin.

[[video]]

## About

Our team at WordPress.com is excited to share our recent prototyping  efforts on game changing approaches to custom content creation. 

This Create Content Model plugin builds upon our custom post types project at the [CloudFest Hackathon in 2024](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-variations/). We’ve leveraged core functionality, like [block bindings](https://make.wordpress.org/core/2024/03/06/new-feature-the-block-bindings-api/) and [block variations](https://developer.wordpress.org/block-editor/reference-guides/block-api/block-variations/), to create a new paradigm for creating and managing custom post types and custom fields in WordPress. 

Unlike existing custom post type and custom field plugins, our plugin  takes a native approach by putting the creation and management of these elements directly in the WordPress Block Editor.

Using the Block Bindings API, custom fields (`post_meta`) are bound to a block’s attributes. Block Variations are created from each bound block for use in front-end template layouts. The result is an extremely intuitive workflow for both the setup of custom post types and fields and their usage in front-end templating. 

```
<!-- wp:paragraph {
	"metadata":{
		"bindings":{
			"content":{
				"source":"core/post-meta",
				"args":{
					"key":"movie-rating"
				}
			}
		}
	}
} -->
<p></p>
<!-- /wp:paragraph -->
```

A key feature of the Create Content Model plugin is the [export](https://github.com/Automattic/create-content-model/blob/78d4a208e0c2c74cebd2a7b434e086731c762b41/includes/exporter/class-content-model-exporter.php) of a locked custom data model and a data entry UI. Developers can generate and reuse the same content model on multiple sites without ongoing plugin maintenance or costs. They can hand off fully functional sites with locked custom post types and fields, ready for clients to populate the content. 


```
private function generate_json_for_model( $model ) {
   return array(
      'type'     => 'postType',
      'postType' => $model->slug,
      'slug'     => $model->slug,
      'label'    => $model->title,
      'template' => $model->template,
      'fields'   => $this->format_fields_for_export( $model->get_meta_fields() ),
   );
}
```

This Create Content Model plugin provides a preview of functionality that can be further developed into a practical solution for users and developers navigating the evolving landscape of WordPress content management.

<!--

## Try it out & give us feedback
See it in action in the WordPress Playground[link to playground site]. And then share your feedback in a [GitHub issue](https://github.com/Automattic/create-content-model/issues).

Or download the plugin [here](download link)
-->




## Development

* `npm install` to install the dependencies
* `npm run dev-server` to start the local WordPress server
* open new terminal window
* `npm start` to start the JavaScript bundler watcher

### Bundling

Run `npm run plugin-zip` to create a zip file of the plugin. This will automatically bundle the JavaScript files. We will update this with versioning when that is in place.

## Documentation
Find detailed instructions on creating your content model using this plugin in the [Get Started](/GETSTARTED.md) guide.


## Contribute & Contact 

Want to help us move this concept forward?

Feel free to open an issue in the repo to discuss your proposed improvement. Pull requests are welcome for bug fixes and enhancements.

We built this as a prototype and may invest into it further based on level of interest.  Our near term vision is outline in this [roadmap issue](https://github.com/Automattic/create-content-model/issues/77).


## Licensing
[GNU General Public License](/LICENSE.md)

## Credits & Acknowledgements 
We’d like to thank the team at WordPress.com who made this project possible:  Brian Coords, Luis Felipe Zaguini, Candy Tsai,  Autumn Fjeld, Daniel Bachhuber.

## Stay in the Loop with WordPress.com
Follow us:

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/automattic/)
  
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/automattic)


[![image](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/wordpressdotcom)

<!-- Later we can add deveopers newsletter -->

And while you’re at it, check out our [WordPress hosting solution for developers](https://wordpress.com/hosting) and [our agency program](https://wordpress.com/for-agencies/).
