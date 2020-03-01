# steps to deploy

A note of manual steps required for deployment for a new release.

1. Update the `path-pattern-finder` JAR version number in `pom.xml` to the correct release.

2. Update the version number in `src/main/resources/topleveldocs/README.txt`

3. Run `mvn deploy` to generate a distribution in target/

4. Rename the directory `target/path-pattern-finder-dist-1.0-SNAPSHOT-dist` to `target/path-pattern-finder-X.X` where `X.X` is the correct version.

5. Delete any files with a `.formatted` extension in this directory.

6. Create `zip` and `tar.gz` (with `tar -czvf file.tar.gz directory`) for this directory.

7. Create a new release on [pattern-path-finder-dist](https://github.com/path-pattern-finder/path-pattern-finder-dist/releases) with the version as both tag and release title.

9. Add a changelog and the `zip` and `tar.gz` files, and publish the release.

10. Upload the download links in the `_config.yml` in the [website repository](https://github.com/path-pattern-finder/path-pattern-finder.github.io/blob/master/_config.yml) to the latest versions.

11. Commit version changes in both repositories, and do a merge from `dev` to `master` if necessary.

12. Test the download links on the website (after some minutes for GitHub to recreate the website with `jekyll`).
