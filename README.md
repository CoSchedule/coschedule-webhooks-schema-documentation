# Events
| Event          | Collection           | Trigger                             |
| -------------- | -------------------- | ----------------------------------- |
| comments.create | [Comments](#comments) | Occurs whenever a comment is created. |
| comments.update | [Comments](#comments) | Occurs whenever a comment is updated. |
| comments.delete | [Comments](#comments) | Occurs whenever a comment is deleted. |
| content.create | [Content](#content) | Occurs whenever content is created. |
| content.update | [Content](#content) | Occurs whenever content is updated. |
| content.delete | [Content](#content) | Occurs whenever content is deleted. |
| events.create | [Events](#events) | Occurs whenever an event is created. |
| events.update | [Events](#events) | Occurs whenever an event is updated. |
| events.delete | [Events](#events) | Occurs whenever an event is deleted. |
| messages.create | [Messages](#messages) | Occurs whenever a message is created. |
| messages.update | [Messages](#messages) | Occurs whenever a message is updated. |
| messages.delete | [Messages](#messages) | Occurs whenever a message is deleted. |
| notes.create | [Notes](#notes) | Occurs whenever a note is created. |
| notes.update | [Notes](#notes) | Occurs whenever a note is updated. |
| notes.delete | [Notes](#notes) | Occurs whenever a note is deleted. |
| projects.create | [Projects](#projects) | Occurs whenever a Marketing Project is created. |
| projects.update | [Projects](#projects) | Occurs whenever a Marketing Project is updated. |
| projects.delete | [Projects](#projects) | Occurs whenever a Marketing Project is deleted. |
| tasks.create | [Tasks](#tasks) | Occurs whenever a task is created. |
| tasks.update | [Tasks](#tasks) | Occurs whenever a task is updated. |
| tasks.delete | [Tasks](#tasks) | Occurs whenever a task is deleted. |
| wordpress_posts.create | [WordPress Posts](#wordpress-posts) | Occurs whenever a WordPress post is created. |
| wordpress_posts.update | [WordPress Posts](#wordpress-posts) | Occurs whenever a WordPress post is updated. |
| wordpress_posts.delete | [WordPress Posts](#wordpress-posts) | Occurs whenever a WordPress post is deleted. |

# Collection Schema

## Content
| Property              | Type        | Description                                                                                                                                                                                 |
| --------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| id                    | `integer`   | Unique identifier for the content object.                                                                                                                                                   |
| public_uuid           | `string`    | The public UUID of the content in RFC4122 v4 format.                                                                                                                                        |
| private_uuid          | `string`    | The private UUID of the content in RFC4122 v4 format.                                                                                                                                       |
| created               | `timestamp` | Time at which the content was created. Measured in seconds since the Unix epoch.                                                                                                            |
| updated               | `timestamp` | Time at which the content was last updated. Measured in seconds since the Unix epoch.                                                                                                       |
| calendar_id           | `integer`   | The ID of the content's parent calendar.                                                                                                                                                    |
| team_member_id        | `integer`   | The ID of the team member assigned as the owner of the content.                                                                                                                             |
| title                 | `string`    | Title of the content.                                                                                                                                                                       |
| schedule              | `timestamp` | Time at which the content has been scheduled for delivery. Measured in seconds since the Unix epoch.                                                                                        |
| status                | `string`    | Defines the status of the content. Can be: `draft`, `pending`, `future`, or `publish`.                                                                                                      |
| permalink             | `string`    | The Permalink Social Helper will be whatever URL is added to the Permalink field.                                                                                                           |
| permalink_images      | `array`     | An array of image URL's scraped from the Open Graph tags of the permalink.                                                                                                                  |
| permalink_title       | `string`    | The Open Graph Title scraped from the permalink.                                                                                                                                            |
| excerpt               | `string`    | A user-defined custom excerpt used in place of `excerpt_memo`.                                                                                                                              |
| excerpt_memo          | `string`    | The Open Graph Description scraped from the permalink.                                                                                                                                      |
| preferred_image       | `string`    | Defines the image url currently computed to fill the 'Best Image' placeholder.                                                                                                              |
| description           | `string`    | The description of the Content.                                                                                                                                                             |
| editor_type           | `string`    | Defines the Content Editor type. Can be: `null` (No Editor, default), `wysiwyg` (string Editor), `enote` (Evernote), `gdoc` (Google Docs), `file` (File Import) or `wordpress` (WordPress). |
| content_types_link_id | `integer`   | Defines the id of the `content_type_link` representing the content type.                                                                                                                    |
| project_id            | `integer`   | Defines the parent project id if the content is part of a Marketing Project.                                                                                                                |
| in_draft_bin          | `boolean`   | Defines if the content appears in the Draft Bin instead of on the calendar.                                                                                                                 |
| label_id              | `integer`   | The ID of the Color Label set on the content.                                                                                                                                               |
| tags                  | `array`     | An array of ids defining the tags attached to the content  (e.g. `[521419, 749243, 816307]`).                                                                                               |

## Comments
| Property       | Type        | Description                                                                           |
| -------------- | ----------- | ------------------------------------------------------------------------------------- |
| id             | `integer`   | Unique identifier for the comment object.                                             |
| team_member_id | `integer`   | The ID of the team member assigned as the owner of the comment.                       |
| parent_type    | `string`    | The type of the comment's parent object. Can be: `content`, or `task`.                |
| parent_id      | `integer`   | The ID of the comment's parent object.                                                |
| calendar_id    | `integer`   | The ID of the comment's parent calendar.                                              |
| comment        | `string`    | The discussion text of the comment.                                                   |
| thread_id      | `integer`   | The ID of the discussion thread the comment belongs to. (can be null)                 |
| created_at     | `timestamp` | Time at which the comment was created. Measured in seconds since the Unix epoch.      |
| updated_at     | `timestamp` | Time at which the comment was last updated. Measured in seconds since the Unix epoch. |

## Events
| Property    | Type        | Description                                                                              |
| ----------- | ----------- | ---------------------------------------------------------------------------------------- |
| id          | `integer`   | Unique identifier for the events object.                                                 |
| calendar_id | `integer`   | The ID of the event's parent calendar.                                                   |
| status      | `string`    | Defines the status of the event. Can be: `inactive`. (currently unused)                  |
| schedule    | `timestamp` | Time at which the event is scheduled to occur. Measured in seconds since the Unix epoch. |
| name        | `string`    | The name of the event.                                                                   |
| description | `string`    | The description of the event. (currently unused)                                         |
| all_day     | `boolean`   | Defines if the event is blocked out for the entire day. (currently unused)               |
| project_id  | `integer`   | Defines the parent project id if the event is part of a Marketing Project.               |
| label_id    | `integer`   | The ID of the Color Label set on the event.                                              |

## Messages
- Coming soon.

## Notes
| Property       | Type        | Description                                                                                                    |
| -------------- | ----------- | -------------------------------------------------------------------------------------------------------------- |
| id             | `integer`   | Unique identifier for the notes object.                                                                        |
| calendar_id    | `integer`   | The ID of the note's parent calendar.                                                                          |
| team_member_id | `integer`   | The ID of the team member assigned as the owner of the note.                                                   |
| text           | `string`    | The text content of the note.                                                                                  |
| shared         | `boolean`   | Defines the visibility of the note (public or private).                                                        |
| date_value     | `string`    | The date at which the note has been scheduled to appear on the calendar. Format: `MM/DD/YYYY`                  |
| schedule       | `timestamp` | Time at which the note has been scheduled to appear on the calendar. Measured in seconds since the Unix epoch. |
| created        | `timestamp` | Time at which the note was created. Measured in seconds since the Unix epoch.                                  |
| project_id     | `integer`   | Defines the parent project id if the note is part of a Marketing Project.                                      |
| label_id       | `integer`   | The ID of the Color Label set on the note.                                                                     |

## Marketing Projects
| Property       | Type        | Description                                                                                          |
| -------------- | ----------- | ---------------------------------------------------------------------------------------------------- |
| id             | `integer`   | Unique identifier for the projects object.                                                           |
| title          | `string`    | Title of the project.                                                                                |
| description    | `string`    | Defines the description string of the projecet.                                                      |
| schedule       | `timestamp` | Time at which the project has been scheduled for delivery. Measured in seconds since the Unix epoch. |
| end_date       | `timestamp` | Time at which the project will end. Measured in seconds since the Unix epoch.                        |
| team_member_id | `integer`   | The ID of the team member assigned as the owner of the project.                                      |
| created_at     | `timestamp` | Time at which the project was created. Measured in seconds since the Unix epoch.                     |
| updated_at     | `timestamp` | Time at which the project was last updated. Measured in seconds since the Unix epoch.                |
| calendar_id    | `integer`   | The ID of the project's parent calendar.                                                             |
| label_id       | `integer`   | The ID of the Color Label set on the project.                                                        |
| tags           | `array`     | An array of ids defining the tags attached to the project  (e.g. `[521419, 749243, 816307]`).        |

## Tasks
- Coming soon.

## WordPress Posts
| Property                | Type        | Description                                                                                                                                                        |
| ----------------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                      | `integer`   | Unique identifier for the wordpress_posts object.                                                                                                                  |
| calendar_id             | `integer`   | The ID of the post's parent calendar.                                                                                                                              |
| status                  | `string`    | Defines the status of the wordpress post. Can be: `draft`, `pending`, `future`, or `publish`.                                                                      |
| schedule                | `timestamp` | Time at which the post has been scheduled for delivery. Measured in seconds since the Unix epoch.                                                                  |
| post_date               | `string`    | The WordPress `post_date` value of the post. Signifies the date the post is scheduled, was published, or the draft was last updated. Format: `YYYY-MM-DD HH:mm:ss` |
| post_date_gmt           | `string`    | The WordPress `post_date_gmt` value of the post, in GMT/UTC. Format: `YYYY-MM-DD HH:mm:ss`                                                                         |
| post_modified_timestamp | `timestamp` | Time at which the post has been modified. Measured in seconds since the Unix epoch.                                                                                |
| post_id                 | `integer`   | The WordPress `post_id` value of the post                                                                                                                          |
| post_type               | `string`    | The WordPress `post_type` value of the post. Can be: `post`, `page`, or `attachment` (or potentially custom post type values)                                      |
| title                   | `string`    | The WordPress `post_title` value of the post                                                                                                                       |
| permalink               | `string`    | The link to the original WordPress post.                                                                                                                           |
| author                  | `integer`   | The WordPress `author_id` value of the post.                                                                                                                       |
| categories              | `string`    | A comma separated string of the category IDs attached to the WordPress post.                                                                                       |
| post_excerpt            | `string`    | The WordPress `post_excerpt` value of the post.                                                                                                                    |
| attachments             | `string`    | An array of image URL's attached to the post from WordPress.                                                                                                       |
| team_member_id          | `integer`   | The ID of the team member assigned as the owner of the post.                                                                                                       |
| excerpt                 | `string`    | A user-defined custom excerpt used in place of `excerpt_memo`.                                                                                                     |
| preferred_image         | `string`    | Defines the image url currently computed to fill the 'Best Image' placeholder.                                                                                     |
| description             | `string`    | Defines the text of the description field for the post.                                                                                                            |
| content_types_link_id   | `integer`   | Defines the id of the `content_type_link` representing the post type.                                                                                              |
| project_id              | `integer`   | Defines the parent project ID if the post is part of a Marketing Project.                                                                                          |
| in_draft_bin            | `boolean`   | Defines if the post appears in the Draft Bin instead of on the calendar.                                                                                           |
| label_id                | `integer`   | The ID of the Color Label set on the post.                                                                                                                         |
| tags                    | `array`     | An array of ids defining the tags attached to the post (e.g. `[521419, 749243, 816307]`).                                                                          |
