# README for lrfg
  
  `lrfg` is a Latest Release Files Generator script for use in
  conjunction with GitHub. It's a proof-of-concept implementation of a
  solution to the problem of how to provide a link directly to a release
  asset in a repository's latest release in the case where releases are
  tagged with version numbers.
  
  As implemented, `lrfg` uses GitHub's REST API where needed to do the
  following:
  1. Download info about the latest release of a specified repository
     belonging to a specified user.
  2. Download the zip file from the latest release of the repository,
     renaming it `<repo>-release.zip` in the process, which removes the
     version number in the filename.
  3. Unzip and modify the content of the zip file as desired.
  4. Zip and tar the modified content to create new release files.
  5. Upload the new release files to the latest release, resulting in
     two new assets: `<repo>-release.zip` and `<repo>-release.tar.gz`

  See `Notes` in the comments of file `lrfg` regarding adjustments and
  token required for use.

  In use over several releases, each release will have release files
  with the same filenames. As a consequence, the latest release zip file,
  for example, may be downloaded directly using the link:
  `https://github.com/<user>/<repo>/releases/latest/download/<repo>-release.zip`
