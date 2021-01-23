# BuildKit (Daemonless)

This Task builds source into a container image using [Moby BuildKit](https://github.com/moby/buildkit).

This `buildkit-daemonless-image-param` Task is similar to [`buildkit`](../buildkit) but does not need creating `Secret`, `Deployment`, and `Service` resources for setting up the `buildkitd` daemon cluster.

|                  | `buildkit`     | `buildkit-daemonless-image-param`|
|------------------|----------------|----------------------|
|Difficulty        | Hard           | Easy                 |
|Supports Rootless | Yes            | No (BuildKit per se supports, but [Tekton doesn't support](https://github.com/tektoncd/pipeline/issues/852))|
|Cache             | Registry+Local | Registry             |

Note: Edited for Green Light to change image output resource to a param to integrate with build process.

## Parameters

* **DOCKERFILE**: The path to the `Dockerfile` to execute (_default:_  `./Dockerfile`)
* **BUILDKIT_IMAGE**: BuildKit image (_default:_`moby/buildkit:vX.Y.Z@sha256:...`)
* **IMAGE**: Image tag to use

## Workspaces

* **source**: A [Workspace](https://github.com/tektoncd/pipeline/blob/master/docs/workspaces.md) containing the source to build.
