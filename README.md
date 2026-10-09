<p align="center">
  <img src="https://www.cyberiaonline.com/assets/splash/apple-touch-icon-precomposed.png" alt="CYBERIA online"/>
</p>

<div align="center">

<h1>cyberia deployment</h1>

</div>

The deployment state of the Cyberia MMO runtime: artifacts and runtime versions are deployed.

| Path                  | Holds                                                                          |
| --------------------- | ------------------------------------------------------------------------------ |
| `conf/`               | The deploy configuration of `dd-cyberia`, with the deploy `package.json`       |
| `images/`             | The runtime images: `engine-cyberia`, `cyberia-server`, `cyberia-client`       |
| `manifests/`          | The generated Kubernetes manifests                                             |
| `underpost.lock.json` | The exact revision of every other Cyberia repository, and the content artifact |
