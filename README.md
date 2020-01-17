🚫 Note: All lines that start with 🚫 are instructions and should be deleted before this is posted to your portfolio. This is intended to be a guideline. Feel free to add your own flare to it.

🚫 The numbers 1️⃣ through 3️⃣ next to each item represent the week that part of the docs needs to be comepleted by.  Make sure to delete the numbers by the end of Labs.

🚫 Each student has a required minimum number of meaningful PRs each week per the rubric.  Contributing to docs does NOT count as a PR to meet your weekly requirements.

# API Documentation

#### Backend deployed at [Heroku](https://student-artco.herokuapp.com/) <br>
#### Backend manual testing playground at [Heroku](https://student-artco.herkuapp.com/graphql) <br>
#### Backend staging at [Heroku](https://student-artco-staging.herokuapp.com/) <br>
#### Backend manual testing playground at [Heroku](https://student-artco-staging.herkuapp.com/graphql) <br>

## Getting started

To get the server running locally:

- Clone this repo
- **yarn install** to install all required dependencies
- **yarn dev** to start the local server
- **yarn test** to test, please run **yarn dev** to start the local server, **yarn knex migrate:latest --env development** to get a development database loaded up on your local machine, and **yarn knex seed:run --env development**, to seed that database with therequired files. You will need to reseed the database every time you run the tests!

### Backend framework goes here

🚫 Why did you choose this framework?

-    Point One
-    Point Two
-    Point Three
-    Point Four

## 2️⃣ Endpoints

#### Organization Routes

| Method | Endpoint                                     | Access Control | Description                               |
| ------ | -------------------------------------------- | -------------- | ----------------------------------------- |
| POST   | `https://student-artco.herkuapp.com/graphql` | all users      | Entry point for all queries and mutations |


#### Data Model
Version: 1.0

##### Query Type

| Fields           | Requires                     | Returns        |
| ---------------- | ---------------------------- | -------------- |
| allSchools       |                              | School array   |
| allArts          |                              | Art array      |
| allCategories    |                              | Category array |
| schoolBySchoolId | Schools table Primary Key    | School         |
| art              | Art table Primary Key        | Art            |
| category         | Categories table Primary Key | Category       |

##### Mutation Type

| Fields    | Parameters                                                                   | Returns |
| --------- | ---------------------------------------------------------------------------- | ------- |
| addSchool | school_name, email, address, city, zip                                       | School  |
| addArt    | category, school_id, price, sold, title, artist_name, description, image_url | Art     |
| updateArt | id, category, price, sold, title, artist_name, description                   | Art     |
| deleteArt | id                                                                           | Art     |
| sendMail  | sendTo, name, subject, fromUser, message                                     | Contact |

##### Object Types

| Type     | Fields                                                                                             |
| -------- | -------------------------------------------------------------------------------------------------- |
| School   | id, school_id, school_name, email, address, city, zipcode, art                                     |
| Art      | id, school_id, price, sold, title, artist_name, description, date_posted, school, category, images |
| Image    | id, image_url, art_id                                                                              |
| Category | id, category                                                                                       |
| Contact  | sendto, name, subject, fromUser, message                                                           |

##### Examples

###### Query

```
query {
  allArts {
    # can return...
    id
    school_id
    price
    sold
    title
    artist_name
    description
    date_posted
    school {
      id
      school_name
      email
      address
      city
      zipcode
    }
    category {
      id
      category
    }
    images {
      id
      image_url
      art_id
    }
  }
}
```

###### Mutation

```
mutation {
  addArt(
    category: 1
    school_id: 1
    price: 50
    title: "Fugue with Confused Execution"
    artist_name: "Myron Medina"
    description: "A damaged, jealous, locket."
    image_url: "https://example.com" # this is generated by Cloudinary
  ) {
    # can return...
    id
    school_id
    price
    sold
    title
    artist_name
    description
    date_posted
    school {
      id
      school_id
      school_name
      email
      address
      city
      zipcode
    }
    category {
      id
      category
    }
    images {
      id
      image_url
      art_id
    }
  }
}
```

## Environment Variables

In order for the app to function correctly, the user must set up their own environment variables.

create a .env file that includes the following:

PORT = Whatever free port you have open will work fine, if 4000 is not available.

DATABASE_URL = This environment variable does not need to be set up locally, but is set by Heroku when enabling the postgres addon.

DB_ENV = This will default to 'development'. If you wish to use testing, please run the script `yarn test` to run the app in the testing environment. This needs to be configured on Heroku to be set to 'production' (no quotes needed when setting the variable).

SGUS = The username for SendGrid, you will need access to student-artco's SendGrid account or have one of your own.

SGPW = The password for SendGrid, you will need access to student-artco's SendGrid account or have one of your own.

## Contributing

When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Please note we have a [code of conduct](./code_of_conduct.md). Please follow it in all your interactions with the project.

### Issue/Bug Request

 **If you are having an issue with the existing project code, please submit a bug report under the following guidelines:**
 - Check first to see if your issue has already been reported.
 - Check to see if the issue has recently been fixed by attempting to reproduce the issue using the latest master branch in the repository.
 - Create a live example of the problem.
 - Submit a detailed bug report including your environment & browser, steps to reproduce the issue, actual and expected outcomes,  where you believe the issue is originating from, and any potential solutions you have considered.

### Feature Requests

We would love to hear from you about new features which would improve this app and further the aims of our project. Please provide as much detail and information as possible to show us why you think your new feature should be implemented.

### Pull Requests

If you have developed a patch, bug fix, or new feature that would improve this app, please submit a pull request. It is best to communicate your ideas with the developers first before investing a great deal of time into a pull request to ensure that it will mesh smoothly with the project.

Remember that this project is licensed under the MIT license, and by submitting a pull request, you agree that your work will be, too.

#### Pull Request Guidelines

- Ensure any install or build dependencies are removed before the end of the layer when doing a build.
- Update the README.md with details of changes to the interface, including new plist variables, exposed ports, useful file locations and container parameters.
- Ensure that your code conforms to our existing code conventions and test coverage.
- Include the relevant issue number, if applicable.
- You may merge the Pull Request in once you have the sign-off of two other developers, or if you do not have permission to do that, you may request the second reviewer to merge it for you.

### Attribution

These contribution guidelines have been adapted from [this good-Contributing.md-template](https://gist.github.com/PurpleBooth/b24679402957c63ec426).

## Documentation

See [Frontend Documentation](🚫link to your frontend readme here) for details on the fronend of our project.
🚫 Add DS iOS and/or Andriod links here if applicable.
