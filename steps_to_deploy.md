# steps to deploy

A note of manual steps required for deployment for a new release.

1. Issue a new release with `mvn release:prepare` and `mvn release:perform`

2. Perform a pull-request from `dev` branch to `master` to bring both updated code and the tags from Step 1.
 
3. Update the `path-pattern-finder` JAR version number in `pom.xml` to the correct release.

4. Update the version number in `src/main/resources/topleveldocs/README.txt`

5. Run `mvn deploy` to generate a distribution in target/

6. Rename the directory `target/path-pattern-finder-dist-1.0-SNAPSHOT-dist` to `target/path-pattern-finder-X.X` where `X.X` is the correct version.

7. Create `zip` and ``tar.gz` (with ` tar -czvf file.tar.gz directory`) for this directory.

8. Create a new release on [pattern-path-finder-dist](https://github.com/path-pattern-finder/path-pattern-finder-dist/releases) with the version as both tag and release title.

9. Add a changelog and the `zip` and ``tar.gz` files, and publish the release.

10. Upload the download links in the `_config.yml` in the [website repository](https://github.com/path-pattern-finder/path-pattern-finder.github.io/blob/master/_config.yml) to the latest versions.

11. Commit version changes in both repositories, and do a merge from `dev` to `master` if necessary.

12. Test the download links on the website (after some minutes for GitHub to recreate the website with `jekyll`).