# Template for New Ruby on Rails Projects with Docker

This is a template for new Ruby on Rails projects configured with Docker.

With Docker, you can isolate your development environment from the rest of your system, allowing you to run your Ruby on Rails project without worrying about dependency issues or version conflicts.

This template also includes basic Git configuration, allowing you to start versioning your code from the beginning.

## How to Use

1. Clone this repository to your local machine. `git clone git@github.com:gilderlan/rails-compose.git my_project_name`.

2. Install [Docker](https://docs.docker.com/get-docker/) on your machine.

3. In the root folder of the project, run the command `docker-compose build` to build the Docker image.

4. Then, run `docker-compose run app rails new . --force --no-deps --database=postgresql` to create a new Rails application.

5. Edit the `config/database.yml` file to connect to the Docker Postgres database.

6. Run `docker-compose run app rake db:create` to create the database. Attention: If you have problems with gem not installed, run `docker-compose build` again.

7. To start the Rails server, run `docker-compose up`.

8. Access `http://localhost:3000` in your browser to see the Rails home page.

## Contributing

If you would like to contribute to this project, please open an issue or submit a pull request.

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more details.
