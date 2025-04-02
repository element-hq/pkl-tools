# Release

The release process currently consists of manual steps, in the future we will add a release script in here. To release a pkl package follow the steps below:

- Checkout the `main` branch and `cd` into the package you would like to release.
- Set the version to release in the `PklProject` file, commit the change and push.
- Run `pkl project package` and copy the release name (e.g. `staticcode@1.0.1`).
- Create a new release on GitHub, setting the name and tag to the release name you just copied.
- Attach all of the files in `./out/release@version` to the release and publish it.
- You have made a release 🎉
 