10 KB Club
==========

This is the source code of [10kbclub.com][website].

[website]: https://10kbclub.com/


Contents
--------

* [Suggest New Website](#suggest-new-website)
* [Development Setup](#development-setup)
* [Commit Guidelines](#commit-guidelines)
* [Additional Details](#additional-details)
* [License](#license)
* [Support](#support)


Suggest New Website
-------------------

Read the [Club Rules][rules] first. If the new website satisfies the
club rules, then [create a new issue][new issue] and provide the URL of
the website.

[rules]: https://10kbclub.com/#club-rules
[new issue]: https://github.com/susam/10kbclub/issues/new


Development Setup
-----------------

To build and develop this project locally, perform the following steps:

 1. Install Node.

    On macOS, enter the following command if you have
    [Homebrew](https://brew.sh):

    ```sh
    brew install node
    ```

    On Debian, Ubuntu, or another Debian-based Linux system, enter the
    following command:

    ```
    sudo apt-get install nodejs npm chromium time
    ```

 2. Clone this repository:

    ```sh
    git clone https://github.com/susam/10kbclub.git
    ```

 3. Initialize the repository with NPM `node_modules`:

    ```sh
    cd 10kbclub
    npm install
    ```

 4. Enter the following command to generate a `metrics.json` file with
    metrics data for each URL specified in [`js/urls.json`]:

    ```sh
    node src/refresh.js
    ```

 5. Enter the following command to render the home page using the data
    in `metrics.json`:

    ```sh
    node src/render.js
    ```

 6. Enter the following command to fetch a single URL and print its
    metrics:

    ```sh
    node src/metrics.js https://www.example.com/
    ```

    This script also accepts multiple URL arguments like this:

    ```sh
    node src/metrics.js https://www.example.com/ https://www.example.org/
    ```

 7. Now open `index.html` using a web browser to see the output.


Commit Guidelines
-----------------

The following guidelines are followed in the commits made manually:

 1. The following command should pass without errors:

    ```sh
    make render
    ```

 2. Commit messages are written as per the guidelines in this document:
    [Writing Good Commit Messages][commit-conventions].

[commit-conventions]: https://github.com/erlang/otp/wiki/Writing-good-commit-messages


Additional Details
------------------

This section contains some additional details that might be useful in
understanding this project.

 1. The project repository at https://github.com/susam/10kbclub is
    automatically published as https://10kbclub.com/ using [GitHub
    Pages][gh-pages].

 2. The build job to publish the website runs automatically once every
    Saturday as well as on every push via GitHub Actions. See
    [`live.yml`] for the GitHub Actions workflow. See
    https://github.com/susam/10kbclub/actions for the previous
    executions of the workflow.

 3. The links to discussion threads in [`js/urls.json`] are not
    exhaustive. Only the 5 earliest discussion threads that have
    100 points or more have been picked from each forum.

[`live.yml`]: .github/workflows/live.yml
[`js/urls.json`]: js/urls.json
[gh-pages]: https://pages.github.com/
[actions]: https://github.com/susam/10kbclub/actions


License
-------

This is free and open source software. You can use, copy, modify,
merge, publish, distribute, sublicense, and/or sell copies of it,
under the terms of the MIT License. See [LICENSE.md][L] for details.

This software is provided "AS IS", WITHOUT WARRANTY OF ANY KIND,
express or implied. See [LICENSE.md][L] for details.

[L]: LICENSE.md


Support
-------

To report bugs, suggest improvements, or ask questions,
[create issues][ISSUES].

[ISSUES]: https://github.com/susam/10kbclub/issues
