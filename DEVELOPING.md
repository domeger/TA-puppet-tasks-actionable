## Developing addon builders

In order to load this module properly into the Splunk Add-On builder for development, the following needs to happen:

- Checkout the branch you want to work on
- tar.gz the directory
- Go to the splunk addon builder
- Delete a previous version of the add-on if it exists
- Import this version

```
$ git checkout -b 'my working branch'
$ tar -C .. --exclude=".git" --exclude="tmpdir" -czvf tmpdir/TA-puppet-tasks-actionable.tar.gz TA-puppet-tasks-actionable
```

To add your finished work back to the repo:
- Export the build from the Splunk Add-On tool
- Move the downloaded tar.gz to tmpdir
- Expand the export the export in tmpdir
- sync the local repo with the tmpdir contents
- proceed with git commits as needed, etc

```
$ cd tmpdir
$ tar xzvf TA-puppet-tasks-actionable_2_0_1_export.tgz
$ cd ..
$ rsync -vr tmpdir/TA-puppet-tasks-actionable_2_0_1_export/* ./
```
