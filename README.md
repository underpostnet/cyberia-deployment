<p align="center">
  <img src="https://www.cyberiaonline.com/assets/splash/apple-touch-icon-precomposed.png" alt="CYBERIA online"/>
</p>

<div align="center">

<h1>cyberia deployment</h1>

</div>

**The deployment state of the Cyberia MMO runtime: which exact artifacts and runtime versions are deployed.**

| Path                  | Holds                                                                          |
| --------------------- | ------------------------------------------------------------------------------ |
| `conf/`               | The deploy configuration of `dd-cyberia`, with the deploy `package.json`       |
| `images/`             | The runtime images: `engine-cyberia`, `cyberia-server`, `cyberia-client`       |
| `manifests/`          | The generated Kubernetes manifests                                             |
| `underpost.lock.json` | The exact revision of every other Cyberia repository, and the content artifact |

This repository holds no content. The content — foundation, instances, sagas — lives in
[cyberia-content](https://github.com/underpostnet/cyberia-content), which builds it into a
versioned artifact. `underpost.lock.json` pins the revision of every repository this deployment
ships, and the version and digest of the content artifact. A deploy checks out each repository at
its pinned revision. The image build checks out the pinned revision of `cyberia-content`, packs it,
and fails unless the result matches the lock.

In the [engine](https://github.com/underpostnet/engine), `cyberia release build` writes `conf/`,
`images/` and `manifests/`, and `cyberia release lock` writes `underpost.lock.json`. Never edit
them by hand.

A deploy checks out this repository at the tip of its branch, from this repository or from
`cyberia-deployment-private`: it holds the lock, so it pins no revision of its own. The source
channel changes only that repository. After a deploy from
the private channel, the deploy publishes the same revision here, fast-forward only.

Application assets belong to the engine source tree in `src/client/public`.
Private File Storage keeps large assets for authoring.
