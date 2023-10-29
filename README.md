# wp-env-files
WordPress Development Environment files

## Installation

Source: [@wordpress/env | Block Editor Handbook | WordPress Developer Resources](https://developer.wordpress.org/block-editor/reference-guides/packages/packages-env/) 

#### Prerequisites

  - Docker installed
  - [Node.js installed](https://github.com/nvm-sh/nvm)
  - Git installed

Install wp-env by running the following: 

    npm -g i @wordpress/env 

Clone the wp-env-files repo to get the base wp-env.json files and composer.json file. 

## Theme Project 

Create a directory in your workspace for your project.  

From the wp-env repo copy and rename the theme.wp-env.json to your project directory. Rename to .wp-env.json (the dot up front is needed). 

    cp theme.wp-env.json <theme dir>/.wp-env.json 

## Plugin Project 

From the wp-env repo copy and rename the plugin.wp-env.json to your project directory. Rename to .wp-env.json (the dot up front is needed). 

    cp plugin.wp-env.json <plugin dir>/.wp-env.json 

Modify .wp-env.json to fit your needs. 

## Starting the WordPress environment 

Change directories into your theme or plugin directory and run: 

    wp-env start 

Once the command finishes, you can access your development environment at localhost:8888 

Note: the port depends on what was specified in the .wp-env.json file. 

Login with the default username and password. 

Username: admin 

Password: password 

## Configuring WordPress Coding Standards: 

With the environment running, you can now run composer and install PHPCS plus the WordPress Coding Standards.  

Copy the composer.json file from the wp-env repo and paste it into the directory you ran wp-env start in. 

To install the composer files run:  

    wp-env run cli --env-cwd=wp-content/plugins/<project path> composer install 

The WordPress coding standards is now configured for your project. 

## Generating Boilerplate 

WordPress provides a couple different methods to create boilerplate files for creating plugins.  

### Standard Plugin 

We can use the wp-cli scaffold command to generate some boilerplate for a plugin using the following command: 

```
wp-env run cli --env-cwd=wp-content/plugins/<project name> \ 

wp scaffold plugin <plugin slug> \

--dir=<plugin directory> \  

--plugin_name=<plugin name> \  

--plugin_description=<plugin description> \

--plugin_author=<plugin author> \

--plugin_author_uri=<plugin author uri> \

--plugin_uri=<plugin uri>
```

### Gutenberg Block 

Run the following to create the plugin project directory and setup files: 

    npm @wordpress/create-block <plugin name>
