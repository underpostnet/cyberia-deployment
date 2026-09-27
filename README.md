<p align="center">
  <img src="https://www.cyberiaonline.com/assets/splash/apple-touch-icon-precomposed.png" alt="CYBERIA online"/>
</p>

<div align="center">

<h1>cyberia deployment</h1>

</div>

**The deployment state of the Cyberia MMO runtime: which exact artifacts and runtime versions are deployed.**

| Path                | Holds                                                                       |
| ------------------- | --------------------------------------------------------------------------- |
| `conf/`             | The deploy configuration of `dd-cyberia`, with the deploy `package.json`    |
| `images/`           | The runtime images: `engine-cyberia`, `cyberia-server`, `cyberia-client`    |
| `manifests/`        | The generated Kubernetes manifests                                          |
| `content-lock.json` | The deployed content artifact: repository, version, source revision, digest |

This repository holds no content. The content — foundation, instances, sagas — lives in
[cyberia-content](https://github.com/underpostnet/cyberia-content), which builds it into a
versioned artifact. `content-lock.json` names the artifact this deployment ships. The image build
checks out that source revision of `cyberia-content`, packs it, and fails unless the result matches
the lock.

`cyberia instance --publish-build` in the [engine](https://github.com/underpostnet/engine) writes
`conf/`, `images/`, `manifests/` and `content-lock.json`. Never edit them by hand.

Application assets belong to the engine source tree in `src/client/public`.
Private File Storage keeps large assets for authoring.
