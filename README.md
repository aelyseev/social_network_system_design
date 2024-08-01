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
  * provide notification to users when someone comments on their posts.

### 3. User Subscriptions

* **Description**: Users should be able to subscribe to other travelers to follow their activity.
* **Requirements**:
  * ability to follow and unfollow other users.
  * display a feed of posts from followed users.
  * notify users of new posts from those they follow.

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

## Non-functional requirements

* **Scalability**: The platform should be designed to handle a growing number of users and posts.
* **Security**: Implement user authentication and data protection measures.
* **Performance**: Optimize loading times for images and feeds to ensure a smooth user experience.
* **User Interface**: The design should be intuitive and mobile-friendly to accommodate travelers using the platform on various devices.

## Calculations

### Assumptions

```shell
DAO = 500_000
```
Average User activity
```shell
2—3 visited page per day
1—2 post per week
```

### Loading
```shell
DAU = 500 000
RPS = 20
```

### Traffic
```shell
traffic = 20 * 10 kb = 200 kb/s

connections = 50 000
```
