#  Laravel Application Deployment with Ansible
The Laravel Application Deployment with Ansible project is designed to automate the deployment of a PHP Laravel application using Ansible. This project simplifies the setup and configuration process, ensuring that the application is correctly deployed and running with minimal manual intervention. Here’s an overview of the project:
## Objective
* To create an Ansible playbook that:

- Clones a Laravel application from a Git repository.

- Installs Composer, a dependency management tool for PHP.

- Installs PHP dependencies using Composer.

- Configures environment variables for the Laravel application.

- Generates an application key for Laravel.

- Starts the Laravel development server.

 ### Key Components
Ansible Playbook:

main.yaml: The core playbook that defines all the tasks required for deployment. It automates cloning the repository, setting up Composer, installing dependencies, configuring environment variables, and starting the application.

- Git Repository:
The playbook clones the Laravel application from a specified Git repository. The default repository URL is https://github.com/hngprojects/hng_boilerplate_php_laravel_web.git, and it checks out the devops branch.

- Composer:
Composer is a tool for managing PHP dependencies. The playbook ensures Composer is installed and then uses it to install the Laravel application's PHP dependencies.

- Environment Configuration:
The .env file is crucial for configuring the Laravel application. The playbook copies the .env.example file to .env and sets necessary environment variables such as database connection details and Redis configuration.

- Application Key:
Laravel requires an application key for encryption. The playbook generates this key using Laravel's built-in command.

- Application Server:
The Laravel development server is started on port 3000. This server is used for development and testing. Ensure this port is available and not used by other services.

#### How It Works
- Repository Cloning:
 The playbook clones the Laravel application repository to the /opt/stage_5b directory on the target server and checks out the devops branch.

- Composer Installation:
Downloads and installs Composer if it’s not already installed on the server.

- PHP Dependency Installation:
Runs composer install to set up all necessary PHP libraries and dependencies.

- Environment Setup:
Copies the example environment configuration file and updates it with correct settings for the database and Redis.

- Application Key Generation:
Executes php artisan key:generate to generate a unique application key for encryption.

- Application Start:
Starts the Laravel development server on port 3000.

Starts the Laravel development server on port 3000.
