---
sidebar_position: 4
---

# Heroku

For deployment to [Heroku](https://heroku.com/) you need to create an account first.

**Note.** *You need to clone TeleDrive in your local machine first.*

## One-click Deployment

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/mgilangjanuar/teledrive)

**If you want to upgrade your application to the latest version, you can use these following steps:**

## Prerequisite

Get started by build all needed services.

- [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) version 7.59.4 or above

### Environment variables

- Server variables

  | env                    | required | description                                           |
  | ---------------------- | -------- | ----------------------------------------------------- |
  | ENV                    | no       | Hide the logs for production, default: develop        |
  | TG_API_ID              | yes      | Application ID from your Telegram App                 |
  | TG_API_HASH            | yes      | Application hash from Telegram App                    |
  | ADMIN_USERNAME         | yes      | Telegram username of the admin TeleDrive              |
  | DATABASE_URL           | yes      | PostgreSQL connection URI, format: `postgresql://[user]:[password]@[host]:[port][/dbname][?paramspec]` |
  | API_JWT_SECRET         | yes      | Random string for encrypt JWT web token               |
  | FILES_JWT_SECRET       | yes      | Random string for encrypt public files                |

- Web variables

  | env                   | required | description                                                       |
  | --------------------- | -------- | ----------------------------------------------------------------- |
  | REACT_APP_API_URL     | no       | Base URL for the API, default: `''` (empty string)                |
  | REACT_APP_TG_API_ID   | yes      | Application ID from your Telegram App *(for experimental features)* |
  | REACT_APP_TG_API_HASH | yes      | Application hash from Telegram App  *(for experimental features)*   |

### Set up Heroku CLI

- Clone the repository to your local machine and point to the local directory:

  ```shell
  git clone https://github.com/mgilangjanuar/teledrive.git
  cd teledrive
  ```

- Login from Heroku CLI in terminal:

  ```shell
  heroku login
  ```

- Add heroku as a remote repository:

  ```shell
  heroku git:remote -a [YOUR_APP_NAME]
  ```

## Upgrade

Upgrade to the latest version of TeleDrive with this command:

```shell

git pull origin main  # or, staging for the latest updates

git push heroku main  # or staging:main, if you're from staging branch
```
