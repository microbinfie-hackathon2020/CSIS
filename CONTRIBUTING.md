# CONTRIBUTING

## Workflows

You can create a workflow in the `.github/workflows` folder.
It needs to be a file with extension `.yml`.
It should be named after the software being tested.
The `name` parameter in the file needs to be named after the software too.

Please fork the repo, create a separate branch in your repo.
Make changes.
When changes are done, create a pull request with the dev branch.

### Basic test ideas

1. See if running the command with `--version` gives a version number and exits with 0
2. See if running the command with `--help` gives a usage with stdout and exits with 0
3. Run the most basic command and compare it with a simple expected value.
4. More ideas can be found in this publication: https://academic.oup.com/gigascience/article/2/1/2047-217X-2-15/2656133

## Documentation

Making the documentation on this page more clear would be very helpful!
