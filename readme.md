Example repository showing how to deploy a Blazor webassembly application to GitHub Pages using GitHub Actions. Full description available here: https://www.davideguida.com/how-to-deploy-blazor-webassembly-on-github-pages-using-github-actions/

Result: https://mizrael.github.io/BlazorOnGitHubPages/

Since this is a User repository, it is not possible to configure Pages to use a different source repository than master. So I had to update my workflow and set `development` as main branch.
Another option might be pushing the artifacts to a separate repository and have Pages configured there.

The deployment is handled by a [GitHub action workflow](https://github.com/mizrael/BlazorOnGitHubPages/blob/development/.github/workflows/gh-pages.yml) that will
- setup .NET Core
- build the application and publish it to the `/build/` folder
- uses [JamesIves/github-pages-deploy-action](https://github.com/JamesIves/github-pages-deploy-action) to deploy the code to the `master` branch

