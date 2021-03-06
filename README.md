# Shifting Power API

## About

Shifting Power serves as a platform for learning about bicycle mechanics. There are 14 videos produced by Bikes Not Bombs' youth programs that give viewers a comprehensive overview of how their bike is put together. The videos are hosted on YouTube and this API organizes them into categories based on how they work together.

Each video will have one or more tags, linking it to a smaller system within the bike and it's related parts. For example, the video titled "Pedals and Cranks" has the tag "drivetrain", which links it with other videos that are related to the drivetrain, like the "Chains" video. These tags are not able to be manipulated by the client and are set by an administrator.

Ratings however, give full CRUD functionality to a client and are owned by both a user and a video.

## Deployed Sites and GitHub Repositories

- [Client GitHub Repository](https://github.com/derekbmcintire/shifting-power-client)
- [Deployed Client](https://derekbmcintire.github.io/shifting-power-client/)
- [API GitHub](https://github.com/derekbmcintire/shifting-power-api)
- [Deployed API](https://shifting-power.herokuapp.com/)

## Technologies Used

This API was built using Ruby on Rails with a PostgreSQL database.

## Endpoints

### Videos
| Verb | URL | Controller#Action |
|------|-----|-------------------|
|GET   |/videos|videos#index   |
|GET   |/videos/:id   |videos#show   |

#### GET/videos Response:
```json
{
  "videos": [
    {
      "id": 1,
      "title": "Pedals and Cranks",
      "url": "https://www.youtube.com/embed/vHc4dTbo9r0",
      "tags": [
        8
      ],
      "ratings": [
        2,
        17
      ]
    },
    {
    "id": 2,
    "title": "Front Derailleur",
    "url": "https://www.youtube.com/embed/rt-DkIuwMf8",
    "tags": [
      8,
      9
    ],
    "ratings": [
      3,
      18
    ]
    }
  ]
}
```

#### GET/videos/:id Response:
```json
{
  "id": 1,
  "title": "Pedals and Cranks",
  "url": "https://www.youtube.com/embed/vHc4dTbo9r0",
  "tags": [
    8
  ],
  "ratings": [
    2,
    17
  ]
}
```

### Userratings
| Verb | URL | Controller#Action |
|------|-----|-------------------|
|GET   |/userratings|userratings#index   |
|POST   |/userratings   |userratings#create   |
|PUT   |/userratings/:id   |userratings#update   |
|DELETE   |/userratings/:id   |userratings#destroy   |

#### GET/userratings Response:
```json
{
  "userratings": [
    {
      "id": 2,
      "rating": 5,
      "user_id": 1,
      "video_id": 1
    },
    {
      "id": 3,
      "rating": 5,
      "user_id": 1,
      "video_id": 2
    }
  ]
}
```

#### POST/userratings Response:
```json
{
  "userrating": {
    "id": 2,
    "rating": 5,
    "user_id": 1,
    "video_id": 1
  }
}
```

#### PUT/userratings Response:
```json
{
  "userrating": {
    "id": 2,
    "rating": 5,
    "user_id": 1,
    "video_id": 1
  }
}
```

#### DELETE/userratings Response:
```
HTTP/1.1 204 No Content
```

## Future Versions

#### Future goals for Shifting Power include:
- Building an admin view that would allow an admin user to perform CRUD actions on videos and tags.
- The option to change langauge to Spanish. These videos were produced in both English and Spanish, and I would like this app to be more accessable to users who speak languages other than English.
- Add more videos/resources. A third party API could be integrated to give a user access to even more videos and resources related to the bike part they have clicked on or searched for.

## Planning and Process

This application was both challenging and exciting to build. It was my first time using a real front end framework and working with both the advantages and limitations that come along with that. I spent my planning time building user stories, wireframes and mapping out the database, and most of the decisions I had to make were around limiting and managing the scope of the project. I feel like there is a lot of potential for this to grow, but I focused on creating an MVP that would give users an idea of how this app could work in the real world.

Working with Ember, I did face some tough challenges, especially with the rating feature, but relied on my class notes and the many resources available to me to push through and create what I envisioned.


## User Stories

- A user can register as a user, log in, log out and change password.
- A user can see a list of videos.
- A user can watch a video.
- A user can click on an image of a bicycle and see videos related to that part.
- A user can rate a video.
- A user can update their rating of a video.
- A user can delete their rating of a video.

## ERD

![ERD](https://c1.staticflickr.com/5/4710/39772216531_212e2bb867_c.jpg)
