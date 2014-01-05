# Backnische

This project contains the static site for [http://www.backnische.ch](http://www.backnische.ch/) and makes use of the
following tools:

* [Middleman](http://middlemanapp.com/) to generate the static web page.

## Installation

The be able to build and run the website locally, make changes and deploy it to [S3](https://aws.amazon.com/s3/), you
need to have the following software on your computer:

### Git

[Git](http://git-scm.com/) is used as version control system to manage the source code and a GUI GitHub client can be
installed from:

* [GitHub for Mac](http://mac.github.com/)
* [GitHub for Windows](http://windows.github.com/)

Please have a look at the client help page on how to checkout the project locally to your computer.

### Ruby

[Ruby](https://www.ruby-lang.org/) needs to be installed on your Machine. It's already pre installed on a Mac, for
Windows you need:

* [Ruby Windows Installer](http://rubyinstaller.org/)

[Bundler](http://bundler.io/) needs also be present, you can install it on the command line with:

```Bash
$ gem install bundler
```

## Prepare

To install all dependencies, bundle the project:

```Bash
$ bundle
```

## Run

To run the project, start middleman an open your browser at [http://localhost:4567](http://localhost:4567)

```
$ bundle exec middleman
```

## Build

To build the final site:

```Bash
$ bundle exec middleman build
```

The site will be generated to the `build` directory.

## Deploy

To deploy the site, you need to create the file `.s3_sync` with the following content and add your AWS credentials:

```YAML
---
aws_access_key_id: <YOUR_ACCESS_KEY>
aws_secret_access_key: <YOUR_SECRET_ACCESS_KEY>
```

now you can deploy with:

```Bash
$ bundle exec middleman s3_sync
```

## License

This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported License.
To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/3.0/.
