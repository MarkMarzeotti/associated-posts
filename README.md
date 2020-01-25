# Associated Posts

Exploring the idea of associating two posts of different post types by adding a column to the `wp_posts` table rather than by using Post Meta. The idea being faster retrieval of multiple posts along with post data without having massive joins with the post meta table.

The idea roughly follows the idea of the post_parent column in the `wp_posts` table but would be intended to cross post types.

## Use Case

If you had a number of post types that should be related to one another. Say you were cataloging houses for sale. You might have a post type for Houses, a post type for Real Estate Agents, and a post type for Real Estate Companies. You would want to easily list information on the Company and Agent on the House single view, list Houses and Agents on the Company single view, and list Company and Houses on the Agent single view.

You would start at the bottom with one to one associations. Houses are assigned to an Agent and Agents are assigned to a Company. No matter what you would have to search the `wp_posts` table for the three posts, Company, Agent, and Houses. Maybe its easier than doing a join with the `wp_postmeta` table between each of them?