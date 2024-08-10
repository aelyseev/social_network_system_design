# System Design of a Social Network for a [System Design Course](https://balun.courses/courses/system_design)

## Features

### 1. Post publishing

* **Description**: Users should be able to publish posts about their travels.
* **Requirements**
  * ability to upload and display photos.
  * provide a text field for a short description of the travel experience.
  * geotagging to associate posts with specific travel locations.


### 2. Post interaction

* **Description**: Users should be able to engage with posts from other travelers.
* **Requirements**:
  * allow users to like and comment on posts.
  * display the number of likes and comments on each post.

### 3. User Subscriptions

* **Description**: Users should be able to subscribe to other travelers to follow their activity.
* **Requirements**:
  * ability to follow and unfollow other users.
  * display a feed of posts from followed users.

### 4. Location-Based Search

* **Description**: Users should be able to find popular travel destinations and view related posts.

**Requirements**:
search functionality to find destinations by name or region.
display a list of popular locations based on user activity.
allow users to browse posts related to specific locations.

### 5. Traveler Feed
* Description: Users should be able to view a feed of posts from other travelers.
* Requirements:
  * display a chronological feed of posts from all users.
  * option to filter the feed by location, popularity, or time.
  * infinite scrolling for continuous browsing of the feed.

### 6. Security
* Description: Implement user authentication and data protection measures.
* Requirements:
  * a user should be able to register to app
  * all pages except landing page should be protected from guest's views

## Non-functional requirements

* **Scalability**: The platform should be designed to handle a growing number of users and posts. 
  * From 0 up to 10,000,000 active daily users
* **Performance**: Optimize loading times for images and feeds to ensure a smooth user experience.
  * feed pages should load within 1-seconds at worst, .5 seconds at average
* **User Interface**: The design should be intuitive and mobile-friendly to accommodate travelers using the platform on various devices.
  * desktop devices ~ 1920×1080 
  * tablet devices ~ 1280×800
  * mobile devices ~ 720×1160

### Application Audience
* User base: 10,000,000 DAO within the first year after launch, with further growth expected.
* Users behaviour: 
  * 2—3 visited page per day 
  * 1-2 post per week
  * comments 5-6 per week
  * reactions 10-12 per week

### Application Features
* Seasonality in the application: no seasonal changes expected so far. 
* Data storage conditions: all data stores forever
* Limits and restrictions: a user may create not more than 100 posts per day
* Time constraints
  * feed page should be fully loaded within 1 second
  * a post should be visible after 5 seconds
  * location search within a 1 second
* Application Availability
  * No more than a few hours of downtime per year

## Calculations

### RPS (feed view)
```shell
DAU = 10 000 000
RPS = 10 000 000 * 3 / 86 400 ~ 350
```

### RPS (publish post)
```shell
DAU = 10 000 000
RPS = 10 000 000 * 2 / 86 400 / 7 ~ 33
```

### RPS (comments)
```shell
DAU = 10 000 000
RPS = 10 000 000 * 6 / 86 400 / 7 ~ 100
```

### RPS (reactions)
```shell
DAU = 10 000 000
RPS = 10 000 000 * 12 / 86 400 / 7 ~ 200
```

### Post size
```shell
text: ~10kb
photo: ~200kb
photos is post: ~4-6
average post size: 10 + 200 * 6 ~ 1.2mb
```

### Traffic(feed view)
```shell
posts in a feed: ~20-30
traffic = 350 * 30 * 1.2mb = 12 Gb/s
```

### Traffic(publish post)
```shell
traffic = 33 * 1.2mb = 40 Mb/s
```

### Traffic(comments)
```shell
comment size: 100b
traffic = 100 * 100b = 10 Kb/s
```

### Traffic(reactions)
```shell
reaction size: 10b
traffic = 100 * 10b = 1 Kb/s
```

### Connections
```shell
1 000 000
```
