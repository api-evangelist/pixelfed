<!-- fetched 2026-10-15 from https://docs.pixelfed.org/spec/ActivityPub.html by sweep-shape-compat.py; text extracted from the provider's own page -->

ActivityPub | Pixelfed Docs Skip to content Docs 
 Search K 
 Main Navigation pixelfed.org Support 
 Appearance
 Menu Return to top 
 Sidebar Navigation 
 Introduction
 Code of Conduct
 Community
 Documentation
 Running Pixelfed
 Prerequisites
 Installation
 Configuration
 Administration
 Push Notifications
 CLI Cheatsheet
 Troubleshooting
 Spec Compliance
 ActivityPub
 On this page
 Table of Contents for current page 
 ActivityPub ​ 
 A decentralized social networking protocol based upon the ActivityStreams 2.0 data format and JSON-LD. Pixelfed uses ActivityPub to send and receive activities from other Pixelfed servers and other fediverse software like Mastodon.
 Context ​ 
 Click to expand status context example json "@context" : [ "https://w3id.org/security/v1" , "https://www.w3.org/ns/activitystreams" , { "Hashtag" : "as:Hashtag" , "sensitive" : "as:sensitive" , "schema" : "http://schema.org/" , "pixelfed" : "http://pixelfed.org/ns#" , "commentsEnabled" : { "@id" : "pixelfed:commentsEnabled" , "@type" : "schema:Boolean" }, "capabilities" : { "@id" : "pixelfed:capabilities" , "@container" : "@set" }, "announce" : { "@id" : "pixelfed:canAnnounce" , "@type" : "@id" }, "like" : { "@id" : "pixelfed:canLike" , "@type" : "@id" }, "reply" : { "@id" : "pixelfed:canReply" , "@type" : "@id" }, "toot" : "http://joinmastodon.org/ns#" , "Emoji" : "toot:Emoji" , "blurhash" : "toot:blurhash" } ] 
 Actors ​ 
 Click to expand actor example json { "id" : "https://example.org/users/dansup" , "type" : "Person" , "following" : "https://example.org/users/dansup/following" , "followers" : "https://example.org/users/dansup/followers" , "inbox" : "https://example.org/users/dansup/inbox" , "outbox" : "https://example.org/users/dansup/outbox" , "preferredUsername" : "dansup" , "name" : "dansup" , "summary" : "Example summary" , "url" : "https://example.org/dansup" , "manuallyApprovesFollowers" : false , "indexable" : true , "publicKey" : { "id" : "https://example.org/users/dansup#main-key" , "owner" : "https://example.org/users/dansup" , "publicKeyPem" : "-----BEGIN PUBLIC KEY--..." }, "icon" : { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://example.org/avatars/avatar.jpg" }, "endpoints" : { "sharedInbox" : "https://example.org/f/inbox" }, "alsoKnownAs" : [ "https://example.net/users/dansup" ] } 
 Click to expand actor attributes Field | Type | Description | 
 id | String | ID of the user | 
 type | String | The object type, always set to Person | 
 following | String | The following collection | 
 followers | String | The followers collection | 
 inbox | String | The inbox collection | 
 outbox | String | The outbox collection | 
 preferredUsername | String | The account username | 
 name | String | The account display name | 
 summary | String | The account bio, may contain HTML | 
 url | String | The account url | 
 manuallyApprovesFollowers | Boolean | If the account is private, this value is set to true | 
 indexable | Boolean | If the account allows crawling, this value is set to true | 
 publicKey | Object | The public key data used for federation | 
 icon | Object | The account avatar object | 
 endpoints | Object | The sharedInbox will be set if configured | 
 alsoKnownAs | Array | A list of account aliases if applicable | 
 Activities ​ 
 Supported ActivityPub Activities
 Click to expand Activities Accept ​ 
 object.type if Follow is transformed into a FollowRequest or Follow model.
 Add ​ 
 If type is Story then object object is transformed into Story model.
 Announce ​ 
 object object is transformed into a reblog_of_id Status model.
 Create ​ 
 Note and Question objects are transformed into statuses database models.
 Delete ​ 
 Person , Tombstone and Story objects with cached models are deleted.
 Flag ​ 
 Used for federated Reports.
 Like ​ 
 object object is transformed into a StatusLike model.
 Reject ​ 
 Used to reject or deny FollowRequest .
 Story:Reaction ​ 
 Transformed into StoryReaction model.
 Story:Reply ​ 
 Transformed into StoryReaction model.
 Update ​ 
 Used for ...
 Undo ​ 
 Used for ...
 View ​ 
 Transformed into StoryView model.
 Collections ​ 
 Following ​ 
 The user following collection is comprised of accounts that this account follows. You may use the totalItems to get the following count for this account, it may return 0 if the account has opted to hide their following.
 Click to expand following example json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/pixelfed/following" , "type" : "OrderedCollection" , "totalItems" : 2 } 
 Followers ​ 
 The user followers collection is comprised of accounts that follow this account. You may use the totalItems to get the followers count for this account, it may return 0 if the account has opted to hide their followers.
 Click to expand followers example json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/pixelfed/followers" , "type" : "OrderedCollection" , "totalItems" : 18189 } 
 Outbox ​ 
 The user outbox collection is comprised of statuses authored by this account. You may use the totalItems to get the status count for this account, it may return 0 if the account is private.
 Click to expand outbox example json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/pixelfed/outbox" , "type" : "OrderedCollection" , "totalItems" : 22 } 
 Objects ​ 
 Accept ​ 
 Accept.Follow ​ 
 Approve/accept follow requests
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "type" : "Accept" , "id" : "https://pixelfed.test/users/john#accepts/follows/2985" , "actor" : "https://pixelfed.test/users/john" , "object" : { "type" : "Follow" , "id" : "https://other.test/35860bf0-9930-4131-b5b4-31d2f31df873" , "actor" : "https://other.test/users/jane" , "object" : "https://pixelfed.test/users/john" } } 
 Announce ​ 
 Announce (also known as boosting or re-tooting) a status to your followers
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/p/mike/631334127931904009/activity" , "type" : "Announce" , "actor" : "https://pixelfed.test/users/mike" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/mike" , "https://pixelfed.test/users/mike/followers" ], "published" : "2023-11-18T03:36:25+0000" , "object" : "https://pixelfed.test/p/dansup/630671772572999686" } 
 Add ​ 
 Add.Story ​ 
 This object is used for federating new Stories, and uses Bearcaps. We currently deliver this activity to known Pixelfed instances only.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/stories/dansup/123456/activity" , "type" : "Add" , "actor" : "https://pixelfed.test/users/dansup" , "to" : [ "https://pixelfed.test/users/dansup/followers" ], "object" : { "id" : "https://pixelfed.test/stories/dansup/123456" , "type" : "Story" , "object" : "bear:?t=XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX&u=https://pixelfed.test/stories/dansup/123456" } } 
 Create ​ 
 Create.Note ​ 
 Share a new status to your followers.
 Click to expand json { "@context" : [ "https://w3id.org/security/v1" , "https://www.w3.org/ns/activitystreams" , { "Hashtag" : "as:Hashtag" , "sensitive" : "as:sensitive" , "schema" : "http://schema.org/" , "pixelfed" : "http://pixelfed.org/ns#" , "commentsEnabled" : { "@id" : "pixelfed:commentsEnabled" , "@type" : "schema:Boolean" }, "capabilities" : { "@id" : "pixelfed:capabilities" , "@container" : "@set" }, "announce" : { "@id" : "pixelfed:canAnnounce" , "@type" : "@id" }, "like" : { "@id" : "pixelfed:canLike" , "@type" : "@id" }, "reply" : { "@id" : "pixelfed:canReply" , "@type" : "@id" }, "toot" : "http://joinmastodon.org/ns#" , "Emoji" : "toot:Emoji" , "blurhash" : "toot:blurhash" } ], "id" : "https://pixelfed.test/p/admin/1/activity" , "type" : "Create" , "actor" : "https://pixelfed.test/users/admin" , "published" : "2018-05-31T21:57:27+00:00" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/admin/followers" ], "object" : { "id" : "https://pixelfed.test/p/admin/1" , "type" : "Note" , "summary" : null , "content" : "Hello Fediverse! <a href='https://pixelfed.test/discover/tags/pixelfed' class='mention hashtag status-link' rel='noopener'>#pixelfed</a> <a href='https://pixelfed.test/discover/tags/dogsOfPixelFed' class='mention hashtag status-link' rel='noopener'>#dogsOfPixelFed</a>" , "inReplyTo" : null , "published" : "2018-05-31T21:57:27+00:00" , "url" : "https://pixelfed.test/p/admin/1" , "attributedTo" : "https://pixelfed.test/users/admin" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/admin/followers" ], "sensitive" : false , "attachment" : [ { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://pixelfed.test/storage/m/image.jpeg" , "name" : null } ], "tag" : [ { "type" : "Hashtag" , "href" : "https://pixelfed.test/discover/tags/pixelfed" , "name" : "#pixelfed" }, { "type" : "Hashtag" , "href" : "https://pixelfed.test/discover/tags/dogsofpixelfed" , "name" : "#dogsOfPixelFed" } ], "commentsEnabled" : true , "capabilities" : { "announce" : "https://www.w3.org/ns/activitystreams#Public" , "like" : "https://www.w3.org/ns/activitystreams#Public" , "reply" : "https://www.w3.org/ns/activitystreams#Public" }, "location" : null } } 
 Delete ​ 
 Delete.Note ​ 
 Delete a status by the object id.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/p/admin/1#delete" , "type" : "Delete" , "actor" : "https://pixelfed.test/users/admin" , "object" : { "id" : "https://pixelfed.test/p/admin/1" , "type" : "Tombstone" } } 
 Delete.Story ​ 
 Delete a story by the object id.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/stories/dansup/123456#delete" , "type" : "Delete" , "actor" : "https://pixelfed.test/users/dansup" , "object" : { "id" : "https://pixelfed.test/stories/dansup/123456" , "type" : "Story" } } 
 Follow ​ 
 Follow a specific account as described by the object attribute.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "type" : "Follow" , "actor" : "https://pixelfed.test/users/pixelfed" , "object" : "https://pixelfed.test/users/admin" } 
 Like ​ 
 Like a specific status as described by the object attribute.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/admin#likes/1" , "type" : "Like" , "actor" : "https://pixelfed.test/users/admin" , "object" : "https://pixelfed.test/p/admin/1" } 
 Reject ​ 
 Reject.Follow ​ 
 Reject/deny a follow request by the actor .
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "type" : "Reject" , "id" : "https://pixelfed.test/users/example#rejects/follows/4284" , "actor" : "https://pixelfed.test/users/example" , "object" : { "type" : "Follow" , "id" : "https://other.test/follows/9k2hoq7pj105mcdm" , "actor" : "https://other.test/users/john" , "object" : "https://pixelfed.test/users/example" } } 
 Undo ​ 
 Undo.Announce ​ 
 Undo the announce/boost activity as described by the object.object attribute.
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/p/dansup/12345/undo" , "actor" : "https://pixelfed.test/users/dansup" , "type" : "Undo" , "object" : { "id" : "https://pixelfed.test/p/dansup/12345/activity" , "type" : "Announce" , "actor" : "https://pixelfed.test/users/dansup" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/dansup" , "https://pixelfed.test/users/dansup/followers" ], "published" : "2018-09-10T00:03:25+0000" , "object" : "https://pixelfed.test/p/dansup/11767" } } 
 Undo.Follow ​ 
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/pixelfed#follow/1/undo" , "type" : "Undo" , "actor" : "https://pixelfed.test/users/pixelfed" , "object" : { "id" : "https://pixelfed.test/users/pixelfed#follows/1" , "actor" : "https://pixelfed.test/users/pixelfed" , "object" : "https://pixelfed.test/users/admin" , "type" : "Follow" } } 
 Undo.Like ​ 
 Click to expand json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/users/admin#likes/1/undo" , "type" : "Undo" , "actor" : "https://pixelfed.test/users/admin" , "object" : { "id" : "https://pixelfed.test/users/admin#likes/1" , "type" : "Like" , "actor" : "https://pixelfed.test/users/admin" , "object" : "https://pixelfed.test/p/admin/1" } } 
 Update ​ 
 Update.Note ​ 
 Click to expand json { "@context" : [ "https://w3id.org/security/v1" , "https://www.w3.org/ns/activitystreams" , { "Hashtag" : "as:Hashtag" , "sensitive" : "as:sensitive" , "schema" : "http://schema.org/" , "pixelfed" : "http://pixelfed.org/ns#" , "commentsEnabled" : { "@id" : "pixelfed:commentsEnabled" , "@type" : "schema:Boolean" }, "capabilities" : { "@id" : "pixelfed:capabilities" , "@container" : "@set" }, "announce" : { "@id" : "pixelfed:canAnnounce" , "@type" : "@id" }, "like" : { "@id" : "pixelfed:canLike" , "@type" : "@id" }, "reply" : { "@id" : "pixelfed:canReply" , "@type" : "@id" }, "toot" : "http://joinmastodon.org/ns#" , "Emoji" : "toot:Emoji" } ], "id" : "https://pixelfed.test/p/dansup/567257798031955417#updates/4269" , "type" : "Update" , "actor" : "https://pixelfed.test/users/dansup" , "published" : "2023-05-26T21:01:10+00:00" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/dansup/followers" , "https://example.net/users/pixelfed" ], "object" : { "id" : "https://pixelfed.test/p/dansup/567257798031955417" , "type" : "Note" , "summary" : null , "content" : "Don't mind me, just testing post editing on <a class= \" u-url list-slug \" href= \" https://pixelfed.test/@pixelfed@example.net \" rel= \" external nofollow noopener \" target= \" _blank \" >@pixelfed@example.net</a> \ud83d\ude09 <br /> \n <br /> \n Edit: It works!!" , "inReplyTo" : null , "published" : "2023-05-25T01:59:58+00:00" , "url" : "https://pixelfed.test/p/dansup/567257798031955417" , "attributedTo" : "https://pixelfed.test/users/dansup" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" ], "cc" : [ "https://pixelfed.test/users/dansup/followers" , "https://example.net/users/pixelfed" ], "sensitive" : false , "attachment" : [ { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://example.org/m/1.jpg" , "name" : "Night sky" }, { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://example.org/m/2.jpg" , "name" : "Sunrise at dawn" } ], "tag" : [ { "type" : "Mention" , "href" : "https://example.net/users/pixelfed" , "name" : "@pixelfed@example.net" } ], "commentsEnabled" : true , "updated" : "2023-05-26T21:01:10+00:00" , "capabilities" : { "announce" : "https://www.w3.org/ns/activitystreams#Public" , "like" : "https://www.w3.org/ns/activitystreams#Public" , "reply" : "https://www.w3.org/ns/activitystreams#Public" }, "location" : null } } 
 Update.Person ​ 
 Click to expand json { "@context" : [ "https://w3id.org/security/v1" , "https://www.w3.org/ns/activitystreams" , { "pixelfed" : "http://pixelfed.org/ns#" , "manuallyApprovesFollowers" : "as:manuallyApprovesFollowers" , "alsoKnownAs" : { "@id" : "as:alsoKnownAs" , "@type" : "@id" }, "movedTo" : { "@id" : "as:movedTo" , "@type" : "@id" }, "indexable" : "pixelfed:indexable" } ], "id" : "https://pixelfed.test/users/admin#updates/1704185077" , "actor" : "https://pixelfed.test/users/admin" , "type" : "Update" , "object" : { "id" : "https://pixelfed.test/users/admin" , "type" : "Person" , "following" : "https://pixelfed.test/users/admin/following" , "followers" : "https://pixelfed.test/users/admin/followers" , "inbox" : "https://pixelfed.test/users/admin/inbox" , "outbox" : "https://pixelfed.test/users/admin/outbox" , "preferredUsername" : "admin" , "name" : "Admin" , "summary" : "pixelfed.social Admin. Managed by @dansup" , "url" : "https://pixelfed.test/admin" , "manuallyApprovesFollowers" : false , "indexable" : false , "publicKey" : { "id" : "https://pixelfed.test/users/admin#main-key" , "owner" : "https://pixelfed.test/users/admin" , "publicKeyPem" : "-----BEGIN PUBLIC KEY----- \n MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAwrugl5+u144q5Lkpfajl \n tx32cSFxYoA0BpMCEThiq195kpMw3h7kAUIOatI9IpoXb70mQr27l1L7kMXoj3nQ \n Gy1EvIpZ/8tjH6cGxh65Ld+PXI42qyjyHeGRXWpfKqVxiB3ip9gtDQyWSAjVbt33 \n fjJcMXFQXxUeX8eUZ/EJ/6hlK7okfzP55w1UGBfrQETCmf7P2egqM1dCbx7cfZdJ \n 4dcGULEAxwYSTtfmUTih/djT5oE7kif8GIr9pdMuobiHrI6BP/ELwFU9t3nIQhjv \n fYGS/I5qIMeF/hvZDcak3aXXejcAwF8MJSiqDJtWeB2t8+xi8HsfMm5NbSmFv6o5 \n BwIDAQAB \n -----END PUBLIC KEY----- \n " }, "icon" : { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://pixelfed.test/storage/avatars/avatar.png" }, "endpoints" : { "sharedInbox" : "https://pixelfed.test/f/inbox" } } } 
 Extensions ​ 
 Blurhash ​ 
 Pixelfed supports the blurhash algorithm to generate efficient image previews to show as a placeholder while content is loading, or for sensitive statuses.
 Click to expand blurhash example json { "@context" : [ "https://www.w3.org/ns/activitystreams" , { "toot" : "http://joinmastodon.org/ns#" , "blurhash" : "toot:blurhash" } ], "id" : "https://pixelfed.test/p/dansup/618893826647911311" , "type" : "Note" , "content" : "Happy #caturday!" , "attachment" : [ { "type" : "Image" , "mediaType" : "image/jpeg" , "url" : "https://example.org/media/caturday.jpg" , "blurhash" : "UEE:0k_2oexa~pIVtRM{oH%L?bM{9F4nWB~W" , } ] } 
 Capabilities (Comment Controls) ​ 
 Pixelfed supports basic comment controls, allowing users to disable Announce , Like and reply activities. The announce , like and reply attributes will be either NULL or https://www.w3.org/ns/activitystreams#Public to represent basic ACL.
 Click to expand capabilities example json { "@context" : [ "https://www.w3.org/ns/activitystreams" , { "pixelfed" : "http://pixelfed.org/ns#" , "commentsEnabled" : { "@id" : "pixelfed:commentsEnabled" , "@type" : "schema:Boolean" }, "capabilities" : { "@id" : "pixelfed:capabilities" , "@container" : "@set" }, "announce" : { "@id" : "pixelfed:canAnnounce" , "@type" : "@id" }, "like" : { "@id" : "pixelfed:canLike" , "@type" : "@id" }, "reply" : { "@id" : "pixelfed:canReply" , "@type" : "@id" }, } ], "id" : "https://pixelfed.test/p/dansup/618893826647911311" , "type" : "Note" , "content" : "Happy #caturday!" , "capabilities" : { "announce" : "https://www.w3.org/ns/activitystreams#Public" , "like" : "https://www.w3.org/ns/activitystreams#Public" , "reply" : "https://www.w3.org/ns/activitystreams#Public" }, } 
 Content Warnings ​ 
 Pixelfed employs the as:sensitive extension property, similar to Mastodon, for indicating sensitive content in posts. When this property is applied to a post in Pixelfed, any associated media will be concealed by default. Additionally, if the post includes a summary, the main content of the post will be collapsed behind this summary, functioning as a content warning. This feature ensures that sensitive material is not immediately visible to viewers, requiring an action to view it.
 Click to expand content warnings example json { "@context" : [ "https://www.w3.org/ns/activitystreams" , { "sensitive" : "as:sensitive" , } ], "id" : "https://pixelfed.test/p/dansup/618893826647911311" , "type" : "Note" , "summary" : null , "content" : "Happy #caturday!" , "sensitive" : false } 
 Custom Emoji ​ 
 Pixelfed, akin to Mastodon , accommodates custom emojis through the integration of an Emoji type tag. This feature operates similarly to the handling of mentions and hashtags.
 In this system, the custom emoji is recognized as a substring within the natural language elements (such as the name, summary, or content) of a post. This substring, representing the emoji's shortcode, is then dynamically linked to its corresponding visual representation. Specifically, the shortcode name is substituted in the post with the HTML code for an inline image, which is derived from the icon property of the emoji. The icon's URL directly links to the image resource, ensuring that the custom emoji is properly displayed within the content.
 Click to expand custom emoji example json { "@context" : [ "https://www.w3.org/ns/activitystreams" , { "toot" : "http://joinmastodon.org/ns#" , "Emoji" : "toot:Emoji" , } ], "id" : "https://pixelfed.test/p/dansup/647727972628135937" , "type" : "Note" , "content" : "test :pixelfed: custom emoji" , "tag" : [ { "id" : "https://pixelfed.test/emojis/12" , "type" : "Emoji" , "name" : ":pixelfed:" , "updated" : "2022-01-21T02:01:03+00:00" , "icon" : { "type" : "Image" , "mediaType" : "image/png" , "url" : "https://pixelfed.test/storage/emoji/12.png" } } ] } 
 Location (Geo-tagging) ​ 
 Pixelfed supports location geo-tagging statuses by selecting a location from a shared dataset. The location object contains a type attribute which is always Place , a name attribute of the location city, the longitude and latitude attributes describe the geographic location and finally the country attribute is the location country.
 Click to expand location example json { "@context" : [ "https://www.w3.org/ns/activitystreams" , ], "id" : "https://pixelfed.test/p/dansup/75783646421848064" , "type" : "Note" , "summary" : null , "content" : "Menlo Park, aka Pixelfed Park" , "location" : { "type" : "Place" , "name" : "Menlo Park" , "longitude" : "-122.182190" , "latitude" : "37.453830" , "country" : "USA" } } 
 Groups ​ 
 Pixelfed supports federated Groups, allowing users to create and join communities that can interact across different Pixelfed instances and other ActivityPub-compatible platforms. This functionality is enabled by the FEP-400e and FEP-1b12 extensions, which provide the necessary protocols and standards for seamless federation.
 Group Actor ​ 
 Click to expand group actor example json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/groups/687201346065063941" , "inbox" : "https://pixelfed.test/groups/687201346065063941/inbox" , "name" : "Test" , "outbox" : "https://pixelfed.test/groups/687201346065063941/outbox" , "summary" : "Test Group" , "type" : "Group" , "attributedTo" : { "type" : "Person" , "id" : "https://pixelfed.test/users/dansup" }, "preferredUsername" : "gid_687201346065063941" , "publicKey" : { "id" : "https://pixelfed.test/groups/687201346065063941#main-key" , "owner" : "https://pixelfed.test/groups/687201346065063941" , "publicKeyPem" : "-----BEGIN PUBLIC KEY----- \n MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEA8NNVngXISNiZFIAHhDU/ \n ye/2g7bVn045BbR6L0izftITaOas7eg+ZF976ahJ5udojaHpHonaTFp/x9zZltH2 \n 6/cc7/s37tdiIcTFuuGKM2n/zxrSd6sy/URFhwLaQkxTqWYugEmV/+jkdBTLz173 \n yC1b9Gi5UfK8CyYrV5Po1xYYh9ZCB5NFZcvRwllcudWLpp+/5IH5D49O8C9kLqUc \n PgHw3ClHeRb7cN17o9ExKj+RtEn+fNqd1yBBgRXgMM5yC/aPhoZ86TF23/G1r6ia \n PLahR9Tgil+Oqae/SkQrEBEdy+TYICRITbjrsTK2WUhR4JYE2YFm9aiGzyeEhA2K \n AwIDAQAB \n -----END PUBLIC KEY----- \n " }, "url" : "https://pixelfed.test/groups/687201346065063941" } 
 Group Activity ​ 
 Click to expand group activity example json { "@context" : "https://www.w3.org/ns/activitystreams" , "id" : "https://pixelfed.test/groups/687201346065063941/p/721271403909644290" , "type" : "Note" , "summary" : null , "content" : "Hello World!" , "inReplyTo" : null , "published" : "2024-07-23T07:55:03+00:00" , "url" : "https://pixelfed.test/groups/687201346065063941/p/721271403909644290" , "attributedTo" : "https://pixelfed.test/users/dansup" , "to" : [ "https://www.w3.org/ns/activitystreams#Public" , "https://pixelfed.test/groups/687201346065063941/followers" ], "cc" : [], "sensitive" : false , "attachment" : [], "target" : { "type" : "Collection" , "id" : "https://pixelfed.test/groups/687201346065063941/wall" , "attributedTo" : "https://pixelfed.test/groups/687201346065063941" } } 
 Authorized Fetch ​ 
 Pixelfed, like other platforms in the Fediverse including Mastodon, uses digital signatures to ensure secure and authenticated federation requests. This compatibility with Mastodon's Authorized Fetch protocol is a crucial aspect of maintaining a secure and interoperable federated network.
 Click to learn more Here's how Pixelfed signs federation requests to align with Mastodon's Authorized Fetch mechanism:
 HTTP Signatures : Pixelfed employs HTTP Signatures to sign federation requests. This is a standard method used across the Fediverse for authenticating HTTP requests, ensuring that the request is sent by a known and verified entity.
 Digital Signature Creation : When Pixelfed sends a federation request (like a post or an activity), it generates a digital signature using the private key of the sending user or server. This signature is unique to each request and is based on the content of the HTTP request.
 Including Public Key Information : Pixelfed includes information in its federation requests about how to find the public key needed to verify the signature. This is usually a URL pointing to an actor's profile where the public key can be fetched.
 Verification on the Receiving End : When Mastodon, or any other compatible platform in the Fediverse, receives a request from Pixelfed, it uses the provided information to fetch the public key and verify the signature. This process ensures that the request is indeed from the claimed source and has not been tampered with during transmission.
 Timestamps and Replay Prevention : To prevent replay attacks, Pixelfed includes timestamps in its signed requests. Mastodon and other platforms check these timestamps to ensure that the request is recent and not a replay of an old request.
 Compliance with ActivityPub Protocol : Both Pixelfed and Mastodon adhere to the ActivityPub protocol, which standardizes the way federated services communicate. The use of HTTP Signatures for authentication is a part of this protocol.
 Authorized Fetch Compatibility : For Mastodon's Authorized Fetch, when Pixelfed sends a request to Mastodon (like accessing a post or user data), Mastodon checks the signature to authenticate the request. Only if the signature is valid and the request is authorized, Mastodon will fulfill the request, aligning with its privacy and security standards.
 By following these steps, Pixelfed ensures that its federation requests to Mastodon and other Fediverse platforms are secure, authenticated, and in line with the privacy standards set by these platforms. This method effectively maintains user privacy and data integrity across different services in the federated network.
 Previous page Troubleshooting
