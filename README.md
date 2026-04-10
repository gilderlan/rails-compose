# Docker template to create new Rails projects

This is a template for new Ruby on Rails projects configured with Docker.

With Docker, you can isolate your development environment from the rest of your system, allowing you to run your Ruby on Rails project without worrying about dependency issues or version conflicts.

**Versions:** Ruby 3.4.2 · Rails 8.0 · PostgreSQL 17

## How to Use

1. Clone this repository to your local machine. `git clone git@github.com:gilderlan/rails-compose.git my_project_name`.

2. Install [Docker](https://docs.docker.com/get-docker/) on your machine.

3. Create a `.env` file in the root folder with the following variables:

   ```env
   PUBLIC_PORT=3000
   APP_NAME=my_project_name
   ```

4. In the root folder of the project, run the command `docker compose build` to build the Docker image.

5. Then, run `docker compose run app rails new . --force --no-deps --skip-docker --database=postgresql` to create a new Rails application.

6. Copy the template `database.yml` to your new app's config folder:

   ```bash
   cp config/database.yml.template config/database.yml
   ```

   > The `database.yml` is already configured to connect to the Docker Postgres service using the `APP_NAME` variable from your `.env`.

7. Run `docker compose run app rake db:create` to create the database. If you have problems with gem not installed, run `docker compose build` and try again.

8. To start the Rails server, run `docker compose up`.

9. Access `http://localhost:3000` in your browser to see the Rails home page.

## Contributing

If you would like to contribute to this project, please open an issue or submit a pull request.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more details.
