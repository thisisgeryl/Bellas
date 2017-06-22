## Synopsis

This is a photo gallery that periodically gathers pictures from various sources. 
Currently, it only gathers pictures from Reddit, but I might add other aggregation sites.

## Motivation

I made this project as a basis of other projects. The code structure is shared from my other closed sourced projects. 
It helped me practice with Celery, Django, Heroku, and S3.

## How to Use

### Gallery Index

The json list of galleries can be accessed at https://bellapi-heroku.herokuapp.com/v0/gallery/index. 
The galleries have the following fields.

Field             | Description
------------------|-------------
name              | The name of the gallery
slug              | The gallery id. Used for the url of the gallery. 
description       | The gallery description
preview_image_url | A link to a single thumb image from a gallery for previewing the gallery.

### Gallery

If you want to get more information on a specific gallery,
just append the galleries *slug* at https://bellapi-heroku.herokuapp.com/v0/gallery/id

**Example**: https://bellapi-heroku.herokuapp.com/v0/gallery/id/123

The json has the following fields.

Field       | Description
------------|-------------
description | The gallery description (Same as the gallery items at gallery index) 
images      | A list of image items from this gallery

Each image item also has its own fields.

Field     | Description
----------|-------------
name      | The name of image (Duh).
image_url | The url to the full size image
thumb_url | The url to the thumbnail of the image. **Warning**: Currently links to the full-size image due to a bug.

