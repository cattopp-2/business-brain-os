### 2026-06-10
Strip any Divi shortcodes from the content before publishing. This includes anything like [et_pb_section], [et_pb_row], [et_pb_column], [et_pb_text], and their closing equivalents. Plain HTML only goes into post_data.json.

When handling [image: label] markers: always build the HTML from the Google Doc source (not from the existing WP post content). The WP post won't have the markers if they were added to the doc after the initial publish. Parse the doc, replace markers with <img> tags using already-uploaded media URLs, then update the post.
