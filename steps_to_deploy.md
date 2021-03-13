# Steps to deploy a new release

A note of manual steps required for deployment for a new release.

1. Issue a new release with `mvn release:prepare` and `mvn release:perform`

2. Perform a pull-request from `dev` branch to `master` to bring both updated code and the tags from Step 1.
 
3. Update the `path-pattern-finder` JAR version number in `pom.xml` to the correct release.

4. Run `mvn deploy` to generate a distribution in target/ (also stored to GitHub Packages)

5. Create a new release on [pattern-path-finder-distribution](https://github.com/path-pattern-finder/path-pattern-finder-distribution/releases) with the version as both tag and release title.

6. Add a changelog and the `zip` and `tar.gz` files, and publish the release.

7. Upload the download links in the `_config.yml` in the [website repository](https://github.com/path-pattern-finder/path-pattern-finder.github.io/blob/master/_config.yml) to the latest versions.

8. Commit version changes in both repositories, and do a merge from `dev` to `master` if necessary.

9. Test the download links on the website (after some minutes for GitHub to recreate the website with `jekyll`).
