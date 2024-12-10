# Artifact Download Action with File Permission Preservation

This composite action, based on [`actions/download-artifact`](https://github.com/actions/download-artifact) and
extracting the artifact's content from a tarball, will preserve file attributes like **file permissions**. This
essential capability is not implemented by GitHub until now (requested on [05.12.2019](https://github.com/actions/upload-artifact/issues/38))
and still delayed and/or refused? to be implemented in the future. According to GitHub, the internal API doesn't allow
the implementation of such a feature, but this actions is demonstrating a working solution.

See [pyTooling/upload-artifact](https://github.com/pyTooling/upload-artifact) for the matching upload action.


## Usage

tbd


### Input Parameters

tbd

### Output Parameters

tbd
## Fixed behavior compared to `actions/download-artifact`

1. **Do preserve file permissions**  
   The artifact's content is collected in a tarball, which allows preserving file attributes like file permissions.
2. **Don't remove common prefix from files**  
   `actions/upload-artifact` removes the common prefix from all files before storing in an artifact. This is not a
   well-defined behavior. Slightly changing the list of collected files might drastically change the directory structure
   of the artifact.  
   This action defines a root directory from where the content of the tarball is constructed. This is independent of the
   list of provided file patterns.


## Dependencies

* [actions/download-artifact@v4](https://github.com/actions/download-artifact)

## Contributors

* [Patrick Lehmann](https://GitHub.com/Paebbels) (Maintainer)
* [Sven Köhler](https://GitHub.com/skoehler)
* [and more...](https://GitHub.com/pyTooling/upload-artifact/graphs/contributors)

### Credits

**This action was inspired by and is based on:**
 * [actions/upload-artifact#38 - upload-artifact does not retain artifact permissions (08. Sep. 2024)](https://github.com/actions/upload-artifact/issues/38#issuecomment-2336484584)
 * [Gist: 
rcdailey/download-tar-action.yml](https://gist.github.com/rcdailey/cd3437bb2c63647126aa5740824b2a4f)


## License

This GitHub Composite Action (source code) licensed under [The MIT License](LICENSE.md).

---

SPDX-License-Identifier: MIT
